<!-- TITLE: [Japanese] ÐΞVp2p Wire Protocol -->



Ethereum / Whisper 等を実行するノード間 p2p 通信は、
既存 ÐΞV 技術つまり [RLP](http://wikijs.ethereum.wiki/RLP) 標準規格を利用したプロトコル（
つまりある種の wire protocol ）によって統治する設計です。
当項の目的はそのプロトコル全体像の把握です。

### Low-Level

ÐΞVp2p ノードは、 transport protocol (TCP) を使用して RLPx 暗号化認証をうけたメッセージを送ることで、通信します。
peer はどのTCPポート上でも自由に通信可能ですが、通常 30303 番を利用します。
TCP は、connection-oriented の媒体を提供するのに対し、ÐΞVp2p ノードは、パケット単位で通信します。
RLPx はパケット送受信の設備を提供します。RLPx に関して詳しくは [プロトコル仕様](https://github.com/ethereum/devp2p/tree/master/rlpx.md) をご覧下さい。 

ÐΞVp2p ノードは、RLPx discovery protocol DHT を介して peer を発見します。また、peer 接続の初期化は、クライアント特有の RPC API へ端点の peer を供給することによっても可能です。

### Payload Contents

コネクションに対して、RLP 符号化のされた様々な payload「乗客」の type があります。
この ''type'' はいつも RLP の最初の項目で決定され、integer として解釈されます。

ÐΞVp2p は、基礎となる wire protocol 上に構築された任意のサブプロトコル ( _capabilities_ として知られたもの) をサポートする目的で設計されます。各サブプロトコルは、必要に応じ、message-ID 空間 の大きさ として与えられます（そのようなプロトコルはすべて、いくつ message-ID を必要とするのかを静的に特定しなければなりません。）
コネクションをし、`Hello` message を受信する間、双方の peer は、どのサブプロトコルを共有するのかについて同等の情報を保持し、
message-ID 空間 の合成の上で、合意形成を得ることができます。

message-ID は、0x10からはじまるもの (0x00-0x10 は ÐΞVp2p messages 用に予約されています) のコンパクト符号化とし、
アルファベット順に並んだ各共有サブプロトコル（同じ名前かつ同じバージョンのもの）に付与されます。
共有されないサブプロトコルは無視されます。もし、複数のバージョンが同じサブプロトコルとして共有されれば、数値の大きい方が勝ち、他は無視されます。


### P2P

**Hello**
`0x00` [`p2pVersion`: `P`, `clientId`: `B`, [[`cap1`: `B_3`, `capVersion1`: `P`], [`cap2`: `B_3`, `capVersion2`: `P`], `...`], `listenPort`: `P`, `nodeId`: `B_64`] 

コネクション上で最初に送られるパケットで、双方から一度だけ送信されます。Hello が受信されるまで、ほかのメッセージは一切送信されないでしょう。
* `p2pVersion` : P2P プロトコルの版の指定。現在は 1 です。
* `clientId` : クライアントソフトウェアの個体番号。人が読みやすいように string としています。 (e.g. "Ethereum(++)/1.0.0").
* `cap` : peer の capability (装備) の名前を特定する length 3 の ASCII string 。現在サポートするものは、`eth`, `shh` です。
* `capVersion` : peer の capability (装備) のバージョンを特定する正の integer です。現在サポートするバージョンは、`eth` の 34 および、 `shh` の 1 です。
* `listenPort` : クライアントが listen (待機) するポートを指定。（現在の接続の接点の中から選びます）もし 0 であれば、クライアントは listen (待機) していないことを表します。
* `nodeId` : ノード個体認証の 512-bit のハッシュ値。ノードを識別します。

**Disconnect**
`0x01` [`reason`: `P`] 

peer に対し、disconnection が執行されることを知らせます。; 受信されれば、直ちに peer は disconnect するのがよいでしょう。送信のとき、行儀のよいホストは、つながっている複数の peer に対して、disconnect するための相手の機会 (read: wait 2 seconds) を与えてから、自身を disconnect するものです。
* `reason` は、オプションの integer で、disconnect の理由を次の中から一つ選びます:
  * `0x00` Disconnect requested;
  * `0x01` TCP sub-system error;
  * `0x02` Breach of protocol, e.g. a malformed message, bad RLP, incorrect magic number &c.;
  * `0x03` Useless peer;
  * `0x04` Too many peers;
  * `0x05` Already connected;
  * `0x06` Incompatible P2P protocol version;
  * `0x07` Null node identity received - this is automatically invalid;
  * `0x08` Client quitting;
  * `0x09` Unexpected identity (i.e. a different identity to a previous connection/what a trusted peer told us).
  * `0x0a` Identity is the same as this node (i.e. connected to itself);
  * `0x0b` Timeout on receiving a message (i.e. nothing received since sending last ping);
  * `0x10` Some other reason specific to a subprotocol.

**Ping**
`0x02` [] 

Requests an immediate reply of `Pong` from the peer.

**Pong**
`0x03` [] 

Reply to peer's `Ping` packet.

**NotImplemented (was GetPeers)**
`0x04`

**NotImplemented (was Peers)**
`0x05`

### Node identity and reputation

あるひとつの ÐΞVp2p node の個体認証は、あるひとつの secp256k1 public key です。　

Node は自由に、与えられた複数の ID に対する評価レートを保存し、それに応じたパフォーマンスを与えることができます。
Node は、man-in-the-middle 攻撃のポテンシャルを図るために、node ID をトラッキングしているかもしれません。
クライアントは自由に、新しい node を書き記したり、node の評判を決定する手段として、node ID を使ったりすることが可能です。

### Session Management

コネクション時、すべてのクライアント（つまり、コネクションの双方）は、`Hello` メッセージを送信しなければなりません。
`Hello` メッセージ受信するときは、ネットワークとの親和性とバージョンを検証し、セッションがアクティブとなり、任意の P2P メッセージが送信されます。

いつ何時でも、Disconnect メッセージは送信されます。