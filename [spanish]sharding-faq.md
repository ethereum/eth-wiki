<!-- TITLE: [Spanish]Sharding FAQ -->



# Introducción

 Actualmente, en todos los protocolos de blockchain, cada nodo almacena todos los estados (saldos de cuenta, código de contrato y almacenamiento, etc.) y procesa todas las transacciones. Esto proporciona mucha seguridad, pero limita en gran medida la escalabilidad: una cadena de bloques no puede procesar más transacciones que las que puede realizar un solo nodo. En gran parte debido a esto, Bitcoin está limitado a 3-7  transacciones por segundo, Ethereum a 7-15, etc. Sin embargo, esto plantea una pregunta: ¿hay formas de crear un nuevo mecanismo, donde solo un pequeño subconjunto de nodos verifica cada transacción? Siempre que haya suficientes nodos que verifiquen cada transacción el sistema todavía es altamente seguro, pero aun siendo este subconjunto de nodos un porcentaje suficientemente pequeño de validadores en total, el sistema puede procesar muchas transacciones en paralelo, ¿no podríamos usar esa técnica para aumentar en gran medida el rendimiento de una blockchain?

# ¿Cuáles son algunas formas triviales pero defectuosas de resolver el problema?

 Hay tres categorías principales de "soluciones fáciles". La primera es renunciar a escalar cadenas de bloques individuales, y en su lugar asumir que los usuarios usarán muchas "altcoins" diferentes. Esto aumenta en gran medida el rendimiento, pero tiene un costo de seguridad: un aumento del factor N en el rendimiento, mediante este método necesariamente viene acompañado de una disminución del factor N en seguridad. Por lo tanto, es discutible que no sea viable para más que pequeños valores de N.

 El segundo es simplemente aumentar el límite de tamaño de bloque. Esto puede funcionar y en algunas situaciones puede ser la receta correcta, ya que los tamaños de bloques pueden estar más restringidos por la política que por consideraciones técnicas realistas. Pero independientemente de las creencias de cada caso individual, este enfoque inevitablemente tiene sus límites: si uno va demasiado lejos, los nodos que se ejecutan en el hardware del consumidor se desconectarán, la red comenzará a depender exclusivamente de un número muy pequeño de supercomputadoras que ejecuten blockchain , lo que puede conducir a un gran riesgo de centralización.

 El tercero es "fusionar la minería", una técnica en la que hay muchas cadenas, pero todas las cadenas comparten la misma potencia minera (o, como prueba de los sistemas de participación, la participación). Actualmente, Namecoin obtiene una gran parte de su seguridad del blockchain de Bitcoin al hacer esto. Si todos los mineros participan, esto teóricamente puede aumentar el rendimiento por un factor de N sin comprometer la seguridad. Sin embargo, esto también tiene el problema de que aumenta la carga computacional y de almacenamiento en cada minero por un factor de N, por lo que, de hecho, esta solución es simplemente una forma furtiva de aumentar el tamaño del bloque.

 Incluso si esto se considera aceptable, aún existe el defecto de que las cadenas no están realmente "unidas"; solo se requiere una pequeña cantidad de incentivo económico para convencer a los mineros de abandonar o comprometer una cadena específica. Esta posibilidad es, de hecho, bastante real, y se han producido [incidentes históricos](https://web.archive.org/web/20170331105910/https://bitcoin.stackexchange.com/questions/3472/what-is-the-story-behind-the-attack-on-coiledcoin) reales de cadenas minadas por fusión, así como desarrolladores que han defendido explícitamente el uso de ataques de minería de fusión como una característica de ["gobernanza"](http://www.truthcoin.info/blog/contracts-oracles-sidechains/), destruyendo cadenas que no son "rentables" a una coalición dada.

 Si solo unos pocos mineros o grupos de mineros participan en la fusión de minería de cada cadena, existe un [riesgo inminente de centralización](https://eprint.iacr.org/2017/791.pdf), mientras que los beneficios de seguridad de la fusión de minería también se reducen en gran medida.


# Parece que hay algún tipo de dilema de escalabilidad en juego. ¿Cuál es este dilema y cómo podemos romperlo?

El dilema afirma que los sistemas de cadena de bloques solo pueden tener como máximo dos de las siguientes tres propiedades:

**· Descentralización** (definida como el sistema que puede ejecutarse en un escenario en el que cada participante solo tiene acceso a recursos O (c), es decir, una computadora portátil común o un VPS pequeño)

**· Escalabilidad** (definida como la capacidad de procesar O (N)> O (c) transacciones)

**· Seguridad** (definida como segura contra atacantes con hasta O (N) recursos)

 En el resto de este documento, continuaremos usando C para referirnos al tamaño de los recursos computacionales (incluyendo computación, ancho de banda y almacenamiento) disponibles para cada nodo, y N para referirnos al tamaño del ecosistema en un sentido abstracto; suponemos que la carga de transacción, el tamaño de estado y el límite de mercado de una criptomoneda son todos proporcionales a N.

# Algunas personas afirman que debido a la ley de Metcalfe, el límite de mercado de una criptomoneda debe ser proporcional a n ^ 2, y no n. ¿Tienen razón?

No.

# ¿Por qué no?

 La ley de Metcalfe afirma que el valor de una red es proporcional al cuadrado del número de usuarios (n ^ 2), porque si una red tiene n usuarios, entonces la red tiene valor para cada usuario, pero luego el valor para cada usuario individual es es proporcional al número de usuarios porque si una red tiene n usuarios que tienen n-1 conexiones potenciales a través de la red de las que se beneficiaría cada usuario individual.

 En la práctica, la [investigación empírica](https://en.wikipedia.org/wiki/Metcalfe%27s_law) sugiere que el valor de una red con n usuarios está cerca de "n ^ 2 proporcionalidad para valores pequeños de n y (n × log n) proporcionalidad para valores grandes de n." Esto tiene sentido porque para valores pequeños , el argumento es cierto, pero una vez que un sistema se hace más grande, los efectos ralentizan el crecimiento. En primer lugar, el crecimiento en la práctica a menudo ocurre en las comunidades, por lo que en una red de escala mediana la red a menudo ya proporciona la mayoría de las conexiones que a cada usuario le importa. Segundo, las conexiones son a menudo sustitutos entre sí, y se podría argumentar que las personas solo obtienen ~ O (log (k)) valor de tener conexiones k, tener 23 marcas de desodorante para elegir es bueno, pero no es mucho mejor que tener 22 elecciones, mientras que la diferencia entre una elección y cero opciones es muy significativa.

 Además, incluso si el valor de una criptomoneda es proporcional a O (k * log (k)) con k usuarios, si aceptamos la explicación anterior como la razón por la cual este es el caso, entonces eso también implica que el volumen de transacción también es O (k * log (k)), ya que el valor log (k) por usuario teóricamente proviene de ese usuario que ejercita conexiones log (k) a través de la red, y el tamaño del estado también debería crecer en muchos casos con O (k * log (k )) ya que hay al menos algunos tipos de estado que son específicos de la relación en lugar de específicos del usuario. Por lo tanto, asumiendo n = O (k * log (k)) y basando todo fuera de n (tamaño del ecosistema) y c (la potencia informática de un solo nodo) es un modelo perfectamente adecuado para nosotros.



# ¿Cuáles son algunas formas moderadamente simples pero solo parciales de resolver el problema de escalabilidad?

 Muchas propuestas de fragmentación (por ejemplo, [esta temprana propuesta de fragmentación de BFT de Loi Luu et al en NUS](https://www.comp.nus.edu.sg/~loiluu/papers/elastico.pdf), la aplicación más reciente de ideas similares en [Zilliqa](https://docs.zilliqa.com/whitepaper.pdf), así como [este enfoque Merklix tree](https://www.deadalnix.me/2016/11/06/using-merklix-tree-to-shard-block-validation/) que se ha sugerido para Bitcoin) intentan solo fragmentar el procesamiento de transacción o solo estado de fragmento, sin tocar el otro. Estos esfuerzos son admirables y pueden conducir a algunas mejoras en la eficiencia, pero se topan con el problema fundamental de que solo resuelven uno de los dos cuellos de botella. Queremos poder procesar más de 10.000 transacciones por segundo sin forzar a cada nodo a ser una supercomputadora o forzar a cada nodo a almacenar un terabyte de datos de estado, y esto requiere una solución integral donde las cargas de trabajo de almacenamiento de estado, procesamiento de transacciones e incluso la descarga y retransmisión de transacciones están distribuidas en todos los nodos.

 Particularmente, tenga en cuenta que esto requiere cambios en el nivel P2P, ya que un modelo de difusión no es escalable, ya que requiere que todos los nodos descarguen y re-difundan O (n) datos (cada transacción que se envía), mientras que nuestro criterio de descentralización asume que cada nodo solo tiene acceso a recursos O (c) de todo tipo.

# ¿Qué hay de los enfoques que no intentan "fragmentar" nada?

 [Bitcoin-NG](http://hackingdistributed.com/2015/10/14/bitcoin-ng/) puede aumentar la escalabilidad de alguna manera mediante un diseño alternativo de blockchain que lo hace mucho más seguro para la red si los nodos están gastando grandes porciones de sus bloques de verificación de tiempo de CPU. En las cadenas de bloques PoW simples, existen altos riesgos de centralización y la seguridad del consenso se debilita si la capacidad se incrementa hasta el punto en que más del 5% del tiempo de CPU de los nodos se utiliza para verificar los bloques; El diseño de Bitcoin-NG alivia este problema. Sin embargo, esto solo puede aumentar la escalabilidad de la capacidad de transacción por un factor constante de quizás 5-50x, y no aumenta la escalabilidad del estado. Dicho esto, los enfoques de estilo Bitcoin-NG no son mutuamente excluyentes con la fragmentación, y los dos ciertamente pueden implementarse al mismo tiempo.

 Las estrategias basadas en canales (Lightning network, Raiden, etc.) pueden escalar la capacidad de transacción por un factor constante pero no pueden escalar el almacenamiento de estado, y también vienen con sus propios conjuntos únicos de compensaciones y limitaciones, particularmente con ataques de denegación de servicio. El escalamiento en cadena a través de fragmentación (más otras técnicas) y escalamiento fuera de la cadena a través de canales son posiblemente necesarios y complementarios.

 Existen enfoques que usan criptografía avanzada, como [Mimblewimble](https://scalingbitcoin.org/papers/mimblewimble.txt) y estrategias basadas en ZK-SNARK, para resolver una parte específica del problema de escalado: la sincronización inicial completa del nodo. En lugar de verificar toda la historia desde la génesis, los nodos podrían verificar una prueba criptográfica en cual el estado actual sigue legítimamente la historia. Estos enfoques resuelven un problema legítimo, aunque vale la pena señalar que uno puede confiar en la criptoeconomía en lugar de en la criptografía pura para resolver el mismo problema de una manera mucho más simple: vea las implementaciones actuales de Ethereum de [sincronización rápida](https://github.com/ethereum/go-ethereum/pull/1889) y [sincronización warp](https://github.com/paritytech/parity). Ninguna de las soluciones hace nada para aliviar el crecimiento del tamaño del estado o los límites del procesamiento de transacciones en línea.


# ¿Cómo encajan Plasma, los "_state channels_" y otras tecnologías de capa 2 en el trilema?

 En el caso de un gran ataque a las subcadenas de Plasma, todos los usuarios de las subcadenas de Plasma tendrían que retirarse a la cadena raíz. Si Plasma tiene O (N) usuarios, entonces esto requerirá O (N) transacciones, y por lo tanto O (N / C) tiempo para procesar todas las extracciones. Si los retrasos en el retiro se fijan en algún D (es decir, la implementación ingenua), entonces tan pronto como N> C * D, no habrá suficiente espacio en el blockchain para procesar todos los retiros a tiempo, y entonces el sistema será inseguro; en este modo, Plasma debería considerarse como una escalabilidad creciente solo por un factor constante (posiblemente grande). Si los retrasos en el retiro son flexibles, entonces se extienden automáticamente si se realizan muchos retiros, esto significa que a medida que N aumenta cada vez más, aumenta el tiempo que un atacante puede forzar el bloqueo de todos los fondos, y así el nivel de "seguridad" del sistema disminuye cada vez más en cierto sentido, ya que la denegación de acceso prolongada puede considerarse una falla de seguridad, aunque una menos leve que la pérdida total de acceso. Sin embargo, esta es una dirección diferente de compensación de otras soluciones, y podría decirse que es una compensación mucho más leve, por lo que las subcadenas de Plasma son, no obstante, una gran mejora en el status-quo. Los canales estatales (State-Channels) tienen propiedades similares, aunque con diferentes compensaciones entre la versatilidad y la velocidad de la finalidad. Otras tecnologías de capa 2 incluyen la verificación de ejecución interactiva fuera de cadena [TrueBit](https://people.cs.uchicago.edu/~teutsch/papers/truebit.pdf) y [Raiden](https://raiden.network/). La [prueba de participación](http://wikijs.ethereum.wiki/Proof-of-Stake-FAQ) con Casper también mejoraría la escala.

# Tamaño del estado, historia, criptoeconomía, ¡oh Dios mío! ¡Defina algunos de estos términos antes de seguir adelante!

**· State**: un conjunto de información que representa el "estado actual" de un sistema; determinar si una transacción es válida o no, así como el efecto de una transacción, en el modelo más simple debería depender únicamente del estado. Los ejemplos de datos de estado incluyen el UTXO establecido en bitcoin, balances + nonces + código + almacenamiento en ethereum, y las entradas de registro de nombre de dominio en Namecoin.

**· History**: una lista ordenada de todas las transacciones que han tenido lugar desde la génesis. En un modelo simple, el estado presente debería ser una función determinista del estado de génesis y la historia.

**· Transaction**: un objeto que entra en el historial. En la práctica, una transacción representa una operación que algún usuario desea realizar y está firmada criptográficamente. En algunos sistemas, las transacciones se denominan blobs, para enfatizar el hecho de que en estos sistemas estos objetos pueden contener datos arbitrarios y no pueden en todos los casos representar un intento de realizar alguna operación en el protocolo.

**· State transition function**: una función que toma un estado, aplica una transacción y emite un nuevo estado. El cálculo involucrado puede implicar la adición y sustracción de saldos de las cuentas especificadas por la transacción, la verificación de las firmas digitales y la ejecución del código de contrato.

**· Merkle tree**: una estructura de árbol hash criptográfico que puede almacenar una gran cantidad de datos, donde autenticar cada dato individual solo toma O (log (n)) espacio y tiempo. Mira [aquí](https://easythereentropy.wordpress.com/2014/06/04/understanding-the-ethereum-trie/) para más detalles. En Ethereum, el conjunto de transacciones de cada bloque, así como el estado, se mantiene en un árbol de Merkle, donde las raíces de los árboles están comprometidas en un bloque.

**· Receipt**: un objeto que representa un efecto de una transacción que no se almacena directamente en el estado, pero que aún se almacena en un árbol de Merkle y se compromete en un encabezado de bloque o en una ubicación especial en el estado para que su existencia pueda posteriormente ser eficientemente probado incluso a un nodo que no tiene todos los datos. Los registros en Ethereum son recibos; en los modelos fragmentados, los recibos se utilizan para facilitar la comunicación asíncrona entre fragmentos.

**· Light client**: una forma de interactuar con un blockchain que solo requiere una cantidad muy pequeña (diremos O (1), aunque O (log (c)) también puede ser exacto en algunos casos) de recursos computacionales, haciendo un seguimiento de solo los encabezados de bloque de la cadena de forma predeterminada y la adquisición de cualquier información necesaria sobre transacciones, estado o recibos al solicitar y verificar las pruebas de Merkle de los datos relevantes en función de las necesidades.

**· State root**: el hash raíz del árbol de Merkle que representa el estado.[<sup>5</sup>](http://wikijs.ethereum.wiki/Sharding-FAQ#ftnt_ref5)


![](https://github.com/vbuterin/diagrams/raw/master/scalability_faq/image02.png)


  _El árbol de estado de Ethereum 1.0 y cómo la raíz del estado se ajusta a la estructura del bloque._

# ¿Cuál es la idea básica detrás de sharding?

 Dividimos el estado y la historia en particiones K = O (n / c) que llamamos "fragmentos". Por ejemplo, un esquema de fragmentación en Ethereum podría poner todas las direcciones que comiencen con 0x00 en un fragmento, todas las direcciones que comiencen con 0x01 en otro fragmento, etc. En la forma más simple de fragmentación, cada fragmento también tiene su propio historial de transacciones, y el efecto de las transacciones en algún fragmento “K” están limitadas al estado del fragmento “K”. Un ejemplo simple sería una cadena de bloques de múltiples activos, donde hay fragmentos “K” y cada fragmento almacena los saldos y procesa las transacciones asociadas con un activo en particular. En las formas más avanzadas de sharding, también se incluye alguna forma de capacidad de comunicación cross-shard, donde las transacciones en un fragmento pueden desencadenar eventos en otros fragmentos.

# ¿Cómo podría ser un diseño básico de una cadena de bloques fragmentada?

 Un enfoque simple es el siguiente. Para simplificar, este diseño realiza un seguimiento de los blobs de datos unicamente; no intenta procesar una función de transición de estado.

 Existen nodos denominados “collators” que aceptan blobs en shard k (dependiendo del protocolo, los collakers eligen qué k o se les asigna aleatoriamente k) y crean intercalaciones. Una intercalación tiene un encabezado de intercalación, un mensaje corto de la forma "Esta es una intercalación de blobs en el fragmento k, la intercalación principal es 0x7f1e74 y la raíz de Merkle de los blobs es 0x3f98ea". Las intercalaciones de cada fragmento forman una cadena al igual que los bloques en una cadena de bloques tradicional.

 Todavía existe una "cadena principal" procesada por todos, pero el papel de esta cadena principal se limita a almacenar encabezados de intercalación para todos los fragmentos. La "cadena canónica" de shard k es la cadena más larga de colaciones válidas en el fragmento k, cuyos encabezados están dentro de la cadena principal canónica.

 Tenga en cuenta que ahora hay varios "niveles" de nodos que pueden existir en dicho sistema:

**· Super-full node**: descarga por completo cada intercalación de cada fragmento, así como la cadena principal, verificando completamente todo.

**· Top-level node**: procesa todos los bloques principales de cadenas, dándoles acceso de "clientes ligeros" a todos los fragmentos.

**· Single-shard node**: actúa como un nodo de nivel superior, pero también descarga por completo y verifica cada colación en un fragmento específico que le interesa más.

**· Litght node**: descarga y verifica los encabezados de bloque de los principales bloques de cadena unicamente; no procesa encabezados ni transacciones de intercalación a menos que necesite leer alguna entrada específica en el estado de un fragmento específico, en cuyo caso descarga la rama Merkle al encabezado de intercalación más reciente para ese fragmento y a partir de ahí descarga la prueba Merkle del valor deseado en el estado.

 También existe un concepto de verificación de windback, donde un cliente ligero puede obtener rápidamente una mayor garantía en tiempo real de la validez de una cadena de intercalación de algún fragmento descargando por completo las intercalaciones más recientes, con el objetivo de determinar la cadena de encabezado de colación más larga para lo cual se verifica que las colaciones N más recientes (por ejemplo, N = 25) sean completamente válidas y estén disponibles.

# ¿Cuáles son los desafíos aquí?

**· Single-shard takeover attaks** (_Ataques de adquisición de un solo fragmento_): ¿qué ocurre si un atacante se hace cargo de la mayoría de los comparadores en un solo fragmento, ya sea para evitar que las intercalaciones obtengan suficientes firmas o, lo que es peor, para enviar intercalaciones que no son válidas?

**· State transition execution** (_Ejecución de transición de estado_): los ataques de toma de control de un solo fragmento generalmente se previenen con esquemas de muestreo aleatorios, pero estos esquemas también dificultan que los coladores calculen las raíces de estado, ya que no pueden tener información de estado actualizada para cada fragmento que podrían ser asignado a, ¿Cómo nos aseguramos de que los clientes ligeros aún puedan obtener información precisa sobre el estado?.

**· Fraud transition execution** (_Detección de fraude_): si se produce una intercalación no válida o un reclamo de estado, ¿cómo se informa de manera confiable a los nodos (incluidos los nodos ligeros) para que puedan detectar el fraude y rechazar la intercalación si es realmente fraudulento?

**· Cross shard communication** (Comunicación de fragmentos cruzados): el diseño anterior no admite comunicación entre fragmentos. ¿Cómo agregamos la comunicación cross-shard de forma segura?

**· The data availability problem** (_El problema de disponibilidad de datos_): como un subconjunto de detección de fraude, ¿qué ocurre con el caso específico en el que faltan datos de una intercalación?.

**· Superquadratic sharding** (_Agrupamiento supercuadrático_): en el caso especial en el que n> c ^ 2, en el diseño simple dado anteriormente habría más de O (c) encabezados de intercalación, por lo que un nodo ordinario no podría procesar incluso solo los bloques de nivel superior. Por lo tanto, se requieren más de dos niveles de indirección entre las transacciones y los encabezados de bloque de nivel superior (es decir, necesitamos "fragmentos de fragmentos"). ¿Cuál es la forma más simple y mejor de hacer esto?.

 Sin embargo, el efecto de una transacción puede depender de eventos que anteriormente tuvieron lugar en otros fragmentos; un ejemplo canónico es la transferencia de dinero, donde se puede mover dinero de shard i a shard j creando primero una transacción de "débito" que destruye monedas en shard i, y luego se crea una transacción de "crédito" que crea monedas en shard j, apuntando a un recibo creado por la transacción de débito como prueba de que el crédito es legítimo.

# Pero, ¿el teorema de CAP no significa que los sistemas distribuidos totalmente seguros son imposibles, y que la fragmentación es inútil?

 El teorema CAP es un resultado que tiene que ver con el consenso distribuido; una declaración simple es: "en los casos en que se lleva a cabo una partición de red, debe elegir consistencia o disponibilidad, no puede tener ambas". El argumento intuitivo es simple: si la red se divide a la mitad, y en una mitad envío una transacción "envíe mis 10 monedas a A" y en la otra envíe una transacción "envíe mis 10 monedas a B", entonces o bien el sistema no está disponible, ya que una o ambas transacciones no se procesarán o se volverá inconsistente, ya que la mitad de la red verá la primera transacción completada y la otra mitad verá la segunda transacción completada. Tenga en cuenta que el teorema CAP no tiene nada que ver con la escalabilidad; se aplica a cualquier situación en la que múltiples nodos deban ponerse de acuerdo sobre un valor, independientemente de la cantidad de datos con los que estén de acuerdo. Todos los sistemas descentralizados existentes han encontrado algún compromiso entre disponibilidad y consistencia; la fragmentación no hace nada fundamentalmente más difícil a este respecto.


# ¿Cuáles son los modelos de seguridad bajo los cuales operamos?

 Existen varios modelos competitivos bajo los cuales se evalúa la seguridad de los diseños de blockchain:

**· Mayoría honesta** (_o supermayoría honesta_): suponemos que existe un conjunto de validadores y hasta un 50% (o 33% o 25%) de esos validadores están controlados por un atacante, y los validadores restantes siguen honestamente el protocolo. Los modelos de mayoría honesta pueden tener adversarios no adaptativos o adaptativos; un adversario es adaptativo si puede elegir rápidamente qué parte del conjunto de validador se "corrompe", y no adaptativa si solo pueden hacer esa elección mucho antes de tiempo.

**· Mayoría descoordinada**: suponemos que todos los validadores son racionales en un sentido teórico de juego (excepto el atacante, que está motivado para hacer que la red falle de alguna manera), pero no más de una fracción (a menudo entre 25% y 50%) capaz de coordinar sus acciones.

**· Elección coordinada**: suponemos que la mayoría o todos los validadores están controlados por el mismo actor o que son totalmente capaces de coordinar la elección económicamente óptima entre ellos. Podemos hablar sobre el costo para la coalición (o el beneficio para la coalición) de lograr algún resultado indeseable.

**· Modelo soborno de atacantes**: tomamos el modelo de mayoría descoordinada, pero en lugar de hacer que el atacante sea uno de los participantes, el atacante se sienta fuera del protocolo y tiene la capacidad de sobornar a los participantes para que cambien su comportamiento. Los atacantes se modelan con un presupuesto, que es el máximo que están dispuestos a pagar, y podemos hablar de su costo, la cantidad que terminan pagando para interrumpir el equilibrio del protocolo.


 La prueba de trabajo de Bitcoin con la solución minera de [Eyal y Sirer](https://arxiv.org/abs/1311.0243) es robusta hasta un 50% bajo la suposición de la mayoría honesta, y hasta ~ 23.21% bajo la suposición de mayoría descoordinada. [Schellingcoin](https://blog.ethereum.org/2014/03/28/schellingcoin-a-minimal-trust-universal-data-feed/) es robusto hasta 50% bajo la mayoría honesta y suposiciones mayoritarias no coordinadas, tiene un costo de ataque ε (es decir, un poco más que cero) en un modelo de elección coordinada, y tiene un requerimiento de presupuesto P + ε y un costo en un soborno modelo debido a los [ataques P + épsilon](https://blog.ethereum.org/2015/01/28/p-epsilon-attack/).

 Los modelos híbridos también existen; por ejemplo, incluso en los modelos de elección coordinada y soborno a los atacantes, es común asumir con honestidad la minoría de que una parte (quizás del 1 al 15%) de los validadores actuará de forma altruista independientemente de los incentivos. También podemos hablar de coaliciones que consisten en entre el 50 y el 99% de los validadores que intentan interrumpir el protocolo o dañar a otros validadores; por ejemplo, en prueba de trabajo, una coalición de 51% puede duplicar sus ingresos al negarse a incluir bloques de todos los demás mineros.

 El modelo de mayoría honesta es discutiblemente muy poco realista y ya ha sido refrenado empíricamente - vea el [fork de minería SPV de Bitcoin](https://www.reddit.com/r/Bitcoin/comments/3c305f/if_you_are_using_any_wallet_other_than_bitcoin/csrsrf9/) para un ejemplo práctico. Esto demuestra demasiado: por ejemplo, un modelo de mayoría honesta implicaría que los mineros honestos están dispuestos a quemar voluntariamente su propio dinero si eso castiga de algún modo a los atacantes. La suposición de mayoría descoordinada puede ser realista; también hay un modelo intermedio donde la mayoría de los nodos es honesto pero tiene un presupuesto, por lo que se apagan si comienzan a perder demasiado dinero.

 En algunos casos se ha criticado al modelo de soborno como adversario, aunque sus defensores argumentan que si se diseña un protocolo con el modelo de soborno de sobornos en mente, entonces debería ser capaz de reducir masivamente el costo del consenso, ya que el 51% de los ataques se vuelven un evento del que se podría recuperar. Evaluaremos la fragmentación en el contexto tanto de la mayoría descoordinada como del soborno de los modelos de atacante. Los modelos de soborno de sobornos son similares a los modelos adversarios de máxima adaptabilidad, excepto que el adversario tiene el poder adicional de poder solicitar información privada de todos los nodos; esta distinción puede ser crucial, por ejemplo, [Algorand](https://people.csail.mit.edu/nickolai/papers/gilad-algorand.pdf) está seguro bajo los modelos de adversarios adaptativos pero no soborna a los modelos de atacantes debido a la forma en que se basa en la información privada para la selección aleatoria.

# ¿Cómo podemos resolver el ataque de adquisición de un solo fragmento en un modelo de mayoría descoordinada?

 En resumen, muestreo aleatorio. A cada fragmento se le asigna una cierta cantidad de coladores (por ejemplo, 150), y los coladores que aprueban bloques en cada fragmento se toman de la muestra para ese fragmento. Las muestras se pueden reorganizar de forma semi-frecuente (por ejemplo, una vez cada 12 horas) o con la máxima frecuencia (es decir, no existe un proceso de muestreo real independiente, los alzadores se seleccionan aleatoriamente para cada fragmento de un conjunto global en cada bloque).

 El muestreo puede ser explícito, como en los protocolos que eligen "comités" de tamaño específico y pedirles que voten sobre la validez y disponibilidad de colaciones específicas, o puede ser implícito, como en el caso de los protocolos de "cadena más larga" donde los nodos asignados pseudoaleatoriamente se basan en intercalaciones específicas y se espera que "verifiquen windback" al menos N antepasados de la intercalación en la que están creando.

 El resultado es que a pesar de que solo unos pocos nodos están verificando y creando bloques en cada fragmento en un momento determinado, el nivel de seguridad no es mucho más bajo, en un modelo de mayoría honesta o descoordinada, de lo que sería si cada nodo estaba verificando y creando bloques. El motivo son las estadísticas simples: si asume una supermayoría honesta de ~ 67% en el conjunto global, y si el tamaño de la muestra es 150, entonces con un 99,999% de probabilidad, la condición de mayoría honesta se cumplirá en la muestra. Si asumes una supermayoría honesta del 75% en el conjunto global, entonces esa probabilidad aumenta a 99.999999998% (mira [aquí](https://en.wikipedia.org/wiki/Binomial_distribution) para detalles del cálculo).

# Por lo tanto, al menos en el entorno de mayoría honesta / descoordinada, tenemos:

**· Descentralización** (cada nodo almacena solo datos O (c), ya que es un cliente ligero en O (c) fragmentos y por lo tanto almacena datos O (1) * O (c) = O (c) de cabeceras de bloque, así como O (c) datos correspondientes a la historia reciente de uno o varios fragmentos a los que está asignado en este momento)

**· Escalabilidad** (con O (c) fragmentos, cada fragmento tiene capacidad O (c), la capacidad máxima es n = O (c ^ 2))

**· Seguridad** (los atacantes necesitan controlar al menos ~ 33% de todo el conjunto de validadores de tamaño O (n) para tener la posibilidad de hacerse cargo de la red).

 En el modelo de soborno para atacantes (o en el modelo del "adversario muy muy adaptable"), las cosas no son tan fáciles, pero lo abordaremos más adelante. Tenga en cuenta que debido a las imperfecciones del muestreo, el umbral de seguridad disminuye del 50% al ~ 30-40%, pero esta es una pérdida de seguridad sorprendentemente baja para lo que puede ser una ganancia de 100-1000x en escalabilidad sin pérdida de descentralización. .

# ¿Cómo se hace este muestreo en prueba de trabajo y en prueba de participación?

 En prueba de participación, es fácil. Ya hay un "conjunto de validador activo" del que se realiza un seguimiento en el estado, y uno puede simplemente tomar muestras de este conjunto directamente. O bien un algoritmo dentro del protocolo se ejecuta y elige 150 validadores para cada fragmento, o cada validador ejecuta de forma independiente un algoritmo que utiliza una fuente común de aleatoriedad para determinar (de forma demostrable) qué fragmento son en un momento dado. Tenga en cuenta que es muy importante que la asignación de muestreo sea "obligatoria"; los validadores no tienen opción de qué fragmento entran. Si los validadores pudieran elegir, los atacantes con una pequeña participación total podrían concentrar su “apuesta” en un fragmento y atacarlo, eliminando así la seguridad del sistema.

 En la prueba de trabajo, es más difícil, ya que con los esquemas de prueba de trabajo "directo" no se puede evitar que los mineros apliquen su trabajo a un fragmento determinado. Es posible utilizar [formularios de prueba de acceso](https://www.microsoft.com/en-us/research/publication/permacoin-repurposing-bitcoin-work-for-data-preservation/) a prueba de trabajo para bloquear mineros individuales a fragmentos individuales, pero es difícil garantizar que los mineros no puedan descargar o generar datos que puedan ser utilizados para otros fragmentos y, por lo tanto, evadirlos. tal mecanismo. El enfoque más conocido es a través de una técnica inventada por Dominic Williams llamada "torres de rompecabezas", donde los mineros realizan primero una prueba de trabajo en una cadena común, que luego los induce a una prueba del grupo de proof of stake, y el conjunto de validadores es muestreado como en el caso del proof of work.

 Una posible ruta intermedia podría verse de la siguiente manera. Los mineros pueden gastar una gran cantidad de trabajo (O (c) -sized) para crear una nueva "identidad criptográfica". El valor preciso de la solución de prueba de trabajo luego elige qué fragmento tienen para hacer su siguiente bloque. Luego pueden gastar una cantidad de trabajo de O para crear un bloque en ese fragmento, y el valor de esa solución de prueba de trabajo determina en qué fragmento pueden trabajar luego, y así sucesivamente [8](http://wikijs.ethereum.wiki/Sharding-FAQ#ftnt_ref8). Tenga en cuenta que todos estos enfoques hacen que la prueba del trabajo sea "con estado" de alguna manera; la necesidad de esto es fundamental.


# ¿Cómo se genera la aleatoriedad para el muestreo aleatorio?

 En primer lugar, es importante tener en cuenta que incluso si la generación de números aleatorios es muy explotable, este no es un defecto fatal para el protocolo; más bien, simplemente significa que hay un incentivo de centralización de medio a alto. La razón es que debido a que la aleatoriedad consiste en escoger muestras bastante grandes, es difícil influir en la aleatoriedad en más de una cierta cantidad.

 La forma más simple de mostrar esto es a través de la [distribución binomial](https://en.wikipedia.org/wiki/Binomial_distribution), como se describió anteriormente; si uno desea evitar que una muestra de tamaño N sea más del 50% corrompida por un atacante, y un atacante tiene un p% del grupo de participación global, la posibilidad de que el atacante logre esa mayoría durante una ronda es:


![](https://github.com/vbuterin/diagrams/raw/master/scalability_faq/image00.gif)


 Aquí hay una tabla de cómo se vería esta probabilidad en la práctica para varios valores de N y p:

<table> <tr>
<td>    </td>
<td> N = 50     </td>
<td> N = 100    </td>
<td> N = 150    </td>
<td> N = 250    </td> </tr>
<tr> <td> p = 0.4    </td>
<td> 0.0978     </td>
<td> 0.0271     </td>
<td> 0.0082     </td>
<td> 0.0009     </td> </tr>
<tr> <td> p = 0.33   </td>
<td> 0.0108     </td>
<td> 0.0004     </td>
<td> 1.83 * 10-5   </td>
<td> 3.98 * 10-8   </td> </tr>
<tr> <td> p = 0.25   </td>
<td> 0.0001     </td>
<td> 6.63 * 10<sup>-8</sup>   </td>
<td> 4.11 * 10<sup>-11</sup>  </td>
<td> 1.81 * 10-17  </td>&lt; </tr>
<tr> <td> p = 0.2    </td>
<td> 2.09 * 10<sup>-6</sup>   </td>
<td> 2.14 * 10<sup>-11</sup>  </td>
<td> 2.50 * 10<sup>-16</sup>  </td>
<td> 3.96 * 10<sup>-26</sup>  </td> </tr>
</table>


 Por lo tanto, para N> = 150, la posibilidad de que cualquier semilla aleatoria determinada conduzca a una muestra que favorezca al atacante es muy pequeña [<sup>11,</sup>](http://wikijs.ethereum.wiki/Sharding-FAQ#ftnt_ref11) [<sup>12</sup>](https://github.com/ethereum/wiki/wiki/Sharding-FAQ#ftnt_ref12). Lo que esto significa desde la perspectiva de la seguridad de la aleatoriedad es que el atacante necesita tener una gran libertad para elegir el orden de los valores aleatorios para romper el proceso de muestreo. La mayoría de las vulnerabilidades en aleatoriedad de prueba de juego no le permiten al atacante simplemente elegir una semilla; en el peor de los casos, le dan al atacante muchas oportunidades de seleccionar la semilla más favorable de entre muchas opciones generadas de manera pseudoaleatoria. Si uno está muy preocupado por esto, uno simplemente puede establecer N a un valor mayor, y agregar una función de derivación de clave moderadamente dura al proceso de cálculo de la aleatoriedad, de modo que se necesitan más de 2<sup>100</sup> pasos computacionales para encontrar una forma de sesgo la aleatoriedad lo suficiente.


 Ahora, veamos el riesgo de que se realicen ataques que intenten influir en la aleatoriedad de forma más marginal, con fines de lucro en lugar de una toma de poder abierta. Por ejemplo, supongamos que hay un algoritmo que selecciona de manera pseudoaleatoria 1000 validadores de un conjunto muy grande (cada validador obtiene una recompensa de $ 1), un atacante tiene un 10% de la apuesta y el ingreso "honesto" promedio del atacante es de 100, y un costo de $ 1 el atacante puede manipular la aleatoriedad para "volver a tirar los dados" (y el atacante puede hacer esto un número ilimitado de veces).

  Debido al teorema del [límite central](https://en.wikipedia.org/wiki/Central_limit_theorem), la desviación estándar del número de muestras, y en base a [otros resultados conocidos en matemáticas](https://math.stackexchange.com/questions/89030/expectation-of-the-maximum-of-gaussian-random-variables), el máximo esperado de N muestras aleatorias está ligeramente por debajo de M + S * sqrt (2 * log (N)) donde M es la media y S es la desviación estándar. Por lo tanto, la recompensa por manipular la aleatoriedad y volver a tirar efectivamente los dados (es decir, aumentar N) cae bruscamente, por ejemplo. con 0 nuevos intentos, la recompensa esperada es de $ 100, con un nuevo juicio es de $ 105.5, con dos es de $ 108.5, con tres es de $ 110.3, con cuatro es de $ 111.6, con cinco es de $ 112.6 y con seis es de $ 113.5. Por lo tanto, después de cinco nuevos intentos, deja de valer la pena. Como resultado, un atacante motivado económicamente con el diez por ciento de la participación (socialmente inútil) gastará $ 5 para obtener un ingreso adicional de $ 13, para un excedente neto de $ 8.

 Sin embargo, este tipo de lógica asume que una sola ronda de volver a tirar los dados es costosa. Muchos antiguos algoritmos de prueba de participación tienen una vulnerabilidad de "stake grinding" donde volver a tirar los dados simplemente significa hacer un cálculo localmente en la computadora; los algoritmos con esta vulnerabilidad son ciertamente inaceptables en un contexto fragmentado. Los algoritmos más nuevos (consulte la sección ["Selección del validador"](http://wikijs.ethereum.wiki/Proof-of-Stake-FAQ) en la prueba de preguntas frecuentes) tienen la propiedad de que volver a lanzar los dados solo se puede hacer renunciando voluntariamente a un punto en el proceso de creación de bloque, lo que implica renunciar a recompensas y tarifas. La mejor manera de mitigar el impacto de los ataques marginales de motivación económica en la selección de muestras es encontrar formas de aumentar este costo. Un método para aumentar el costo por un factor de sqrt (N) de N rondas de votación es el [método de la mayoría de los bits ideado por Iddo Bentov](https://arxiv.org/pdf/1406.5694.pdf).

 Otra forma de generación aleatoria de números que no es explotable por las coaliciones minoritarias es el enfoque determinista del umbral de la firma más investigado y defendido por Dominic Williams. La estrategia aquí es usar una firma de [umbral determinista](https://eprint.iacr.org/2002/081.pdf) para generar la semilla aleatoria a partir de la cual se seleccionan las muestras. Las firmas de umbral deterministas tienen la propiedad de que se garantiza que el valor sea el mismo independientemente de cuál de un conjunto dado de participantes proporcione sus datos al algoritmo, siempre que al menos ⅔ de participantes participen honestamente. Es obvio que este enfoque no es explotable económicamente y es totalmente resistente a todas las formas de “stake-grinding”, pero tiene varias debilidades:

 **· Se basa en una criptografía más compleja** (específicamente, curvas y combinaciones elípticas). Otros enfoques se basan en nada más que la suposición de oráculo aleatorio para algoritmos de hash comunes.

**· Falla cuando muchos validadores están fuera de línea**. Un objetivo deseado para los blockchains públicos es poder sobrevivir a porciones muy grandes de la red que desaparecen simultáneamente, siempre que la mayoría de los nodos restantes sean honestos; los esquemas deterministas de firma de umbral en este punto no pueden proporcionar esta propiedad.


**· No es seguro para un atacante sobornado o para un modelo de mayoría coordinada** donde más del 67% de los validadores se están confabulando. Los otros enfoques descritos en la prueba de participación en las Preguntas Frecuentes anteriores todavía hacen que sea costoso manipular la aleatoriedad, ya que los datos de todos los validadores se mezclan en la semilla y hacer cualquier manipulación requiere una colusión universal o excluir otros validadores.

 Se podría argumentar que el enfoque determinista de umbral de firma funciona mejor en contextos que favorezcan la coherencia y que otros enfoques funcionen mejor en contextos que favorezcan la disponibilidad.

 # ¿Cuáles son las ventajas y desventajas de hacer que el muestreo sea más o menos frecuente?

 La frecuencia de selección afecta a cuán adaptativos pueden ser los adversarios para que el protocolo siga siendo seguro contra ellos; por ejemplo, si crees que un ataque adaptativo (por ejemplo, validadores deshonestos que descubren que son parte de la misma muestra agrupando y coludiendo) puede suceder en 6 horas pero no menos, entonces estarías bien con un tiempo de muestreo de 4 horas pero no 12 horas Este es un argumento a favor de hacer que el muestreo ocurra lo más rápido posible.

 El principal desafío con el muestreo que tiene lugar cada bloque es que la remodelación conlleva una gran cantidad de gastos generales. Específicamente, la verificación de un bloque en un fragmento requiere conocer el estado de ese fragmento, por lo que cada vez que se vuelven a barajar los validadores, los validadores deben descargar todo el estado para el nuevo fragmento en el que se encuentran. Esto requiere un tamaño de estado fuerte. política de control (es decir, garantizar económicamente que el tamaño del estado no crezca demasiado, ya sea eliminando cuentas antiguas, restringiendo la tasa de creación de nuevas cuentas o una combinación de las dos) y un tiempo de reorganización bastante largo para funcionar bien.

 Actualmente, el cliente de Parity puede descargar y verificar una instantánea completa del estado de Ethereum mediante "warp-sync" en ~ 2-8 horas, lo que sugiere que los períodos de reorganización de unos días pero no menos son seguros; quizás esto podría reducirse en cierta medida reduciendo el tamaño del estado a través del [alquiler del almacenamiento](https://ethresear.ch/t/a-simple-and-principled-way-to-compute-rent-fees/1455), pero incluso los períodos de remodelación deberían ser largos, lo que podría hacer que el sistema sea vulnerable a los adversarios adaptativos.

 Sin embargo, hay formas de evitar por completo la compensación, eligiendo al creador de la próxima intercalación en cada fragmento con solo unos minutos de advertencia, pero sin agregar gastos de descarga de estado imposiblemente altos. Esto se hace transfiriendo la responsabilidad del almacenamiento del estado, y posiblemente incluso la ejecución del estado, lejos de los coladores por completo, y en su lugar asignando el rol a cualquiera de los usuarios o un protocolo de verificación interactivo.

# ¿Podemos forzar que se retenga más estado del lado del usuario para que las transacciones puedan validarse sin que los validadores tengan todos los datos de estado?

Ver también: https://ethresear.ch/t/the-stateless-client-concept/172

  Las técnicas aquí tienden a requerir que los usuarios almacenen datos de estado y proporcionen pruebas de Merkle junto con cada transacción que envían. Se enviaría una transacción junto con una prueba de ejecución correcta de Merkle (o "testigo"), y esta prueba permitiría que un nodo que solo tiene la raíz de estado calcule la nueva raíz de estado. Esta prueba de ejecución correcta consistiría en el subconjunto de objetos en el trie que tendría que atravesarse para acceder y verificar la información de estado que la transacción debe verificar; Como las pruebas Merkle tienen un tamaño O (log (n)), la prueba de una transacción que accede a un número constante de objetos también sería de tamaño O (log (n)).


![](https://github.com/vbuterin/diagrams/raw/master/scalability_faq/image03.png)


 _El subconjunto de objetos en un árbol de Merkle que tendría que proporcionarse en una prueba Merkle de una transacción que accede a varios objetos de estado._


 Implementar este esquema en su forma pura tiene dos defectos. Primero, introduce una sobrecarga O (log (n)) (~ 10-30x en la práctica), aunque se podría argumentar que esta sobrecarga O (log (n)) no es tan mala como parece porque asegura que el validador simplemente mantenga los datos de estado en la memoria y, por lo tanto, nunca tenga que ocuparse de la sobrecarga de acceder al disco duro[<sup>9</sup>](http://wikijs.ethereum.wiki/Sharding-FAQ#ftnt_ref9). En segundo lugar, se puede aplicar fácilmente si las direcciones a las que accede una transacción son estáticas, pero es más difícil de aplicar si las direcciones en cuestión son dinámicas, es decir, si la ejecución de la transacción tiene código de la forma read (f (read (x))) donde la dirección de algún estado leído depende del resultado de la ejecución de algún otro estado leído. En este caso, la dirección que el emisor de la transacción cree que la transacción leerá en el momento en que envía la transacción puede diferir de la dirección que realmente se lee cuando la transacción se incluye en un bloque, por lo que la prueba de Merkle puede ser insuficiente[<sup>10</sup>](https://github.com/ethereum/wiki/wiki/Sharding-FAQ#ftnt_ref10).

 Esto se puede resolver con listas de acceso (piense: una lista de cuentas y subconjuntos de intentos de almacenamiento), que especifican estáticamente a qué datos pueden acceder las transacciones, de modo que cuando un minero recibe una transacción con un testigo, pueden determinar que el testigo contiene todas los datos a los que la transacción podría acceder o modificar. Sin embargo, esto perjudica la resistencia a la censura, lo que hace que los ataques sean similares a los posibles intentos de la [bifurcación ligera DAO](http://hackingdistributed.com/2016/07/05/eth-is-more-resilient-to-censorship/).

# ¿Podemos dividir los datos y la ejecución para que podamos obtener la seguridad de una validación de datos rápida sin la sobrecarga de mezclar los nodos que realizan la ejecución del estado?

 Sí. Podemos crear un protocolo donde dividimos los validadores en dos roles: collators y executors. Los colators son responsables de simplemente construir una cadena de intercalaciones y verificar que los datos en las colaciones estén disponibles, pero no necesitan verificar nada dependiente del estado (por ejemplo, si alguien que intenta enviar ETH tiene suficiente dinero). Los ejecutores toman la cadena de intercalaciones acordada por los coladores como se da, y luego ejecutan las transacciones en las intercalaciones secuencialmente y calculan el estado. Si cualquier transacción incluida en una intercalación no es válida, los ejecutores simplemente saltan sobre ella. De esta forma, los validadores que verifican la disponibilidad pueden reorganizarse de manera instantánea y los ejecutores pueden permanecer en un solo fragmento.

 Habría un protocolo de cliente ligero que permite a los clientes ligeros determinar en qué estado se basa en los reclamos firmados por los ejecutores, pero este protocolo NO es un consenso simple de votación mayoritaria. Más bien, el protocolo es un juego interactivo con algunas similitudes con Truebit, donde si hay un gran desacuerdo, el cliente ligero simplemente ejecuta colaciones específicas o porciones de colaciones. Por lo tanto, los clientes ligeros pueden obtener una vista correcta del estado incluso si el 90% de los ejecutores en el fragmento están dañados, lo que hace que sea mucho más seguro permitir que los ejecutores sean reacomodados con poca frecuencia o incluso permanentemente específicos del fragmento.

 Elegir lo que entra en una recopilación requiere conocer el estado de esa intercalación, ya que es la forma más práctica de saber qué pagará en realidad la tarifa de transacción, pero esto puede resolverse separando aún más el rol de los cobradores (quienes acuerdan la historia ) y proponentes (que proponen colaciones individuales) y creando un mercado entre las dos clases de actores; mira [aquí](https://ethresear.ch/t/separating-proposing-and-confirmation-of-collations/1000) para más discusión sobre esto.


# ¿Pueden los SNARKs y STARKs ayudar?

 ¡Sí! Se puede crear un protocolo de segundo nivel en el que se utilice un esquema [SNARK](https://medium.com/@VitalikButerin/zk-snarks-under-the-hood-b33151a013f6), [STARK](https://vitalik.ca/general/2017/11/09/starks_part_1.html) o un esquema de prueba de conocimiento cero para demostrar la raíz de estado de una cadena de fragmentos, y los creadores de pruebas pueden ser recompensados por esto. Dicho esto, en primer lugar, todavía se requieren cadenas de fragmentos para llegar a un acuerdo sobre qué datos se incluyen en las cadenas de fragmentos.

# ¿Cómo podemos facilitar la comunicación entre fragmentos?

  El escenario más fácil de satisfacer es aquel en el que hay muchas aplicaciones que, individualmente, no tienen demasiados usuarios y que solo ocasionalmente y poco, interactúan entre sí; en este caso, las aplicaciones pueden vivir en fragmentos separados y usar comunicación cruzada a través de recibos para comunicarse entre ellos.

 Esto generalmente implica dividir cada transacción en un "débito" y un "crédito". Por ejemplo, supongamos que tenemos una transacción en la que la cuenta A en el fragmento M desea enviar 100 monedas a la cuenta B en el fragmento N. Los pasos serían los siguientes:

1. Envíe una transacción en el fragmento M que (i) deduce el saldo de A por 100 monedas, y (ii) crea un recibo. Un recibo es un objeto que no se guarda directamente en el estado, pero donde se puede verificar el hecho de que se generó el recibo a través de una prueba de Merkle.

2. Espere a que se incluya la primera transacción (a veces es necesario esperar la finalización, esto depende del sistema).

3. Envíe una transacción en el fragmento N que incluye la prueba de Merkle del recibo de (1). Esta transacción también verifica en el estado de shard N para asegurarse de que este recibo "no se haya gastado"; si lo es, entonces aumenta el saldo de B en 100 monedas, y lo guarda en el estado en que se gasta el recibo.

4. Opcionalmente, la transacción en (3) también guarda un recibo, que luego puede usarse para realizar más acciones en el fragmento M que dependen de la operación original que tenga éxito.


![](https://github.com/vbuterin/diagrams/raw/master/scalability_faq/image01.png)

 En formas más complejas de fragmentación, las transacciones pueden, en algunos casos, tener efectos que se extienden a lo largo de varios fragmentos y también pueden pedir datos sincrónicos desde el estado de múltiples fragmentos.


# ¿Cuál es el problema del tren y el hotel?

 El siguiente ejemplo es cortesía de Andrew Miller. Supongamos que un usuario desea comprar un boleto de tren y reservar un hotel, y quiere asegurarse de que la operación sea atómica: o ambas reservas tienen éxito o ninguna de las dos tiene éxito. Si el boleto de tren y las aplicaciones de reserva de hotel están en el mismo fragmento, esto es fácil: cree una transacción que intente hacer ambas reservas y arroje una excepción y revierta todo a menos que ambas reservas tengan éxito. Si los dos están en fragmentos diferentes, sin embargo, esto no es tan fácil; incluso sin preocupaciones de criptoeconomía / descentralización, este es esencialmente el problema de las transacciones de [bases de datos atómicas](https://en.wikipedia.org/wiki/Atomicity_(database_systems)).

 Solo con mensajes asíncronos, la solución más simple es reservar primero el tren, luego reservar el hotel, luego, una vez que ambas reservas logren confirmar ambas; el mecanismo de reserva prevendría que cualquier otra persona reserve (o al menos asegure que haya suficientes lugares disponibles para permitir la confirmación de todas las reservas) durante un período de tiempo. Sin embargo, esto significa que el mecanismo se basa en suposiciones de seguridad adicionales: que los mensajes de fragmentos cruzados de un fragmento pueden incluirse en otro fragmento dentro de un período de tiempo determinado.

 Con las transacciones síncronas “cross-shard”, el problema es más fácil, pero el desafío de crear una solución de fragmentación capaz de realizar transacciones síncronas atómicas cruzadas es en sí mismo decididamente no trivial; ver la presentación de Vlad Zamfir, que habla sobre [bloques de fusión](https://www.youtube.com/watch?v=GNGbd_RbrzE).

 Otra solución consiste en hacer que los contratos se muevan por fragmentos; consulte el esquema de bloqueo de [fragmentos cruzados propuesto](https://ethresear.ch/t/cross-shard-locking-scheme-1/1269), así como [esta propuesta](https://ethresear.ch/t/cross-shard-locking-scheme-1/1269) donde los contratos se pueden "extraer" de un fragmento a otro, permitiendo que dos contratos que normalmente residen en fragmentos diferentes se muevan temporalmente al mismo fragmento en cuyo punto una operación síncrona entre ellos pueden suceder.

# ¿Cuáles son las preocupaciones sobre el sharding a través del muestreo aleatorio en un atacante sobornado o modelo de elección coordinada?

 En un atacante sobornado o un modelo de elección coordinado, el hecho de que los validadores se muestreen al azar no importa: sea cual sea la muestra, el atacante puede sobornar a la gran mayoría de la muestra para que haga lo que le plazca, o el atacante controla una mayoría de la muestra directamente y puede dirigir la muestra para realizar acciones arbitrarias a bajo costo (O (c) costo, para ser precisos).

 En ese punto, el atacante tiene la capacidad de realizar 51% de ataques contra esa muestra. La amenaza se magnifica aún más porque existe el riesgo de un contagio cruzado: si el atacante corrompe el estado de un fragmento, el atacante puede comenzar a enviar cantidades ilimitadas de fondos a otros fragmentos y realizar otras travesuras cruzadas. Con todo, la seguridad en el atacante sobornado o el modelo de elección coordinada no es mucho mejor que la de simplemente crear O (c) altcoins.

# ¿Cómo podemos mejorar esto?

 En el contexto de la ejecución del estado, podemos usar protocolos de verificación interactivos que no son votos mayoritarios de muestra aleatoria, y que pueden dar respuestas correctas incluso si el 90% de los participantes son defectuosos; vea [Truebit](https://people.cs.uchicago.edu/~teutsch/papers/truebit.pdf) para ver un ejemplo de cómo se puede hacer esto. Para la disponibilidad de datos, el problema es más difícil, aunque hay varias estrategias que se pueden usar junto con los votos de la mayoría para resolverlo.

# ¿Cuál es el problema de disponibilidad de datos y cómo podemos usar los códigos de borrado para resolverlo?

Ver https://github.com/ethereum/research/wiki/A-note-on-data-availability-and-erasure-coding

# ¿Podemos eliminar la necesidad de resolver la disponibilidad de datos con algún tipo de esquema de acumulador criptográfico?

 No. Supongamos que existe un esquema en el que existe un objeto S que representa el estado (S podría ser un hash) posiblemente así como información auxiliar ("testigos") en poder de usuarios individuales que pueden demostrar la presencia de objetos de estado existentes (por ej. . S es una raíz de Merkle, los testigos son las ramas, aunque existen otras construcciones como los acumuladores RSA). Existe un protocolo de actualización donde se transmiten algunos datos, y estos datos cambian S para cambiar el contenido del estado, y también pueden cambiar los testigos.

 Supongamos que algún usuario tiene los testigos para un conjunto de N objetos en el estado y M de los objetos se actualizan. Después de recibir la información de actualización, el usuario puede verificar el nuevo estado de todos los N objetos y, por lo tanto, ver qué M se actualizaron. Por lo tanto, la información de actualización codificada al menos ~ M * log (N) bits de información. Por lo tanto, la información de actualización que todos necesitan recibir para implementar el efecto de las transacciones M debe ser necesariamente del tamaño O (M).[14](http://wikijs.ethereum.wiki/Sharding-FAQ#ftnt_ref14)

# Entonces, ¿esto significa que podemos crear bloques de bloques fragmentados donde el costo de hacer que algo malo suceda es proporcional al tamaño de todo el conjunto de validadores?

 Hay un ataque trivial mediante el cual un atacante siempre puede quemar O (c) capital para reducir temporalmente la calidad de un fragmento: envíelo por correo no deseado enviando transacciones con altas tarifas de transacción, forzando a los usuarios legítimos a superar su oferta. Este ataque es inevitable; podría compensar con límites de gas flexibles, e incluso podría intentar esquemas de "transparencia transparente" que intenten reasignar nodos automáticamente a fragmentos basándose en el uso, pero si alguna aplicación particular no es paralelizable, la ley de Amdahl garantiza que no hay nada que puede hacer. El ataque que se abre aquí (recordatorio: solo funciona en el modelo de Zamfir, no es una mayoría honesta / descoordinada) no es sustancialmente peor que el ataque de spam de transacción. Por lo tanto, hemos alcanzado el límite conocido para la seguridad de un solo fragmento, y no hay ningún valor para tratar de ir más allá.

Retrocedamos un poco. ¿Realmente necesitamos algo de esta complejidad si tenemos un mezcla instantánea? ¿No significa la mezcla instantánea básicamente que cada fragmento extrae directamente los validadores del conjunto de validación global para que funcione como una cadena de bloques, por lo que la fragmentación en realidad no introduce ninguna nueva complejidad?

 Mas o menos. Antes que nada, vale la pena señalar que la prueba de trabajo y la simple prueba de participación, incluso sin fragmentación, tienen muy poca seguridad en un modelo de ataque de soborno; un bloque solo se "finaliza" realmente en el sentido económico después del tiempo O (n) (como si solo hubieran pasado unos pocos bloques, entonces el costo económico de reemplazar la cadena es simplemente el costo de comenzar un doble gasto antes del bloque en cuestión). Casper resuelve este problema agregando su mecanismo de finalidad, de modo que el margen de seguridad económica aumenta inmediatamente al máximo. En una cadena fragmentada, si queremos finalidad económica, entonces tenemos que encontrar una cadena de razonamiento de por qué un validador estaría dispuesto a hacer un reclamo muy fuerte en una cadena basada únicamente en una muestra aleatoria, cuando el validador mismo está convencido que el atacante sobornado y los modelos de elección coordinada pueden ser verdaderos, por lo que la muestra aleatoria podría corromperse.

# Mencionaste “transparent-sharding”. Tengo 12 años y ¿qué es esto?

 Básicamente, no exponemos el concepto de "fragmentos" directamente a los desarrolladores, y no asignamos permanentemente objetos de estado a fragmentos específicos. En cambio, el protocolo tiene un proceso continuo de equilibrio de carga incorporado que desplaza objetos entre fragmentos. Si un fragmento se vuelve demasiado grande o consume demasiado gas, se puede dividir por la mitad; si dos fragmentos se vuelven demasiado pequeños y hablan entre sí con mucha frecuencia, pueden combinarse entre sí; si todos los fragmentos se vuelven demasiado pequeños, un fragmento se puede eliminar y su contenido se puede mover a otros fragmentos, etc.

 Imagínense si Donald Trump se da cuenta de que la gente viaja mucho entre Nueva York y Londres, pero hay un océano en el camino, por lo que podría sacar sus tijeras, cortar el océano, unir la costa este de EE. UU. Y Europa occidental y poner el Atlántico al lado del Polo Sur, es algo así.

# ¿Cuáles son algunas ventajas y desventajas de esto?

**·** Los desarrolladores ya no necesitan pensar en los fragmentos.

**·** Existe la posibilidad de que los fragmentos se ajusten manualmente a los cambios en los precios del gas, en lugar de depender de la mecánica del mercado para aumentar los precios del gas en algunos fragmentos más que otros.

**·** Ya no existe una noción de co-ubicación confiable: si dos contratos se colocan en el mismo fragmento para que puedan interactuar entre sí, los cambios de fragmentos pueden terminar separándolos.

**·** Mayor complejidad de protocolo.

 El problema de co-ubicación puede mitigarse introduciendo una noción de "dominios secuenciales", donde los contratos pueden especificar que existen en el mismo dominio secuencial, en cuyo caso siempre será posible la comunicación síncrona entre ellos. En este modelo, un fragmento se puede ver como un conjunto de dominios secuenciales que se validan juntos, y donde los dominios secuenciales se pueden reequilibrar entre los fragmentos si el protocolo determina que es eficiente hacerlo.

# ¿Cómo funcionarían los mensajes síncronos cruzados?

 El proceso se vuelve mucho más fácil si usted ve que el historial de transacciones ya está resuelto, y simplemente está tratando de calcular la función de transición de estado. Hay varios enfoques; un enfoque bastante simple se puede describir de la siguiente manera:

· Una transacción puede especificar un conjunto de fragmentos en los que puede operar.

· Para que la transacción sea efectiva, debe incluirse a la misma altura de bloque en todos estos fragmentos.

· Las transacciones dentro de un bloque se deben poner en orden de su hash (esto asegura un orden canónico de ejecución).


 Un cliente en el fragmento X, si ve una transacción con fragmentos (X, Y), solicita una prueba Merkle del fragmento Y verificando (i) la presencia de esa transacción en el fragmento Y, y (ii) cuál es el estado previo en el fragmento Y es para los bits de datos a los que la transacción deberá acceder. A continuación, ejecuta la transacción y se compromete con el resultado de la ejecución. Tenga en cuenta que este proceso puede ser muy ineficiente si hay muchas transacciones con muchos "emparejamientos de bloques" diferentes en cada bloque; Por esta razón, puede ser óptimo simplemente requerir bloques para especificar fragmentos hermanos, y luego el cálculo se puede hacer de manera más eficiente a nivel de bloque. Esta es la base de cómo dicho esquema podría funcionar; uno podría imaginar diseños más complejos. Sin embargo, al hacer un nuevo diseño, siempre es importante asegurarse de que los ataques de denegación de servicio de bajo costo no puedan ralentizar arbitrariamente el cálculo del estado.

# ¿Qué pasa con los mensajes asíncronos?

 Vlad Zamfir creó un esquema mediante el cual los mensajes asíncronos podrían resolver el problema de "reservar un tren y un hotel". Esto funciona de la siguiente manera. El estado realiza un seguimiento de todas las operaciones que se han realizado recientemente, así como también el gráfico de las operaciones que se desencadenaron con una operación dada (incluidas las operaciones de fragmentos cruzados). Si se revierte una operación, se crea un recibo que puede usarse para revertir cualquier efecto de esa operación en otros fragmentos; esos reveses pueden desencadenar sus propios reveses y demás. El argumento es que si uno polariza el sistema para que los mensajes de reversión se puedan propagar dos veces más rápido que otros tipos de mensajes, una transacción compleja de fragmentos cruzados que finaliza la ejecución en K rondas puede revertirse completamente en otras K rondas.

 Podría decirse que la sobrecarga que este esquema introduciría no ha sido suficientemente estudiada; puede haber escenarios en el peor de los casos que desencadenen vulnerabilidades de ejecución cuadrática. Está claro que si las transacciones tienen efectos que están más aislados entre sí, la sobrecarga de este mecanismo es menor; quizás las ejecuciones aisladas se pueden incentivar a través de reglas favorables de costo de gas. Con todo, esta es una de las direcciones de investigación más prometedoras para la fragmentación avanzada.

# ¿Qué son llamadas garantizadas con cross-shard?

 Uno de los desafíos en la fragmentación es que cuando se realiza una llamada, de manera predeterminada no existe una garantía provista por el protocolo de que las operaciones asincrónicas creadas por esa llamada se realicen dentro de un marco de tiempo particular, o incluso que se realicen; más bien, corresponde a una parte enviar una transacción en el fragmento de destino activando el recibo. Esto está bien para muchas aplicaciones, pero en algunos casos puede ser problemático por varias razones:

· Puede que no haya una sola parte que esté claramente incentivada para activar un recibo dado. Si el envío de una transacción beneficia a muchas partes, entonces podría haber efectos de tragedia de los comunes, donde las partes intentan esperar más hasta que otra persona envíe la transacción, o simplemente decida que el enviar la transacción no vale los honorarios para ellos.

· Los precios del gas en los fragmentos pueden ser volátiles y, en algunos casos, realizar la primera mitad de una operación obliga al usuario a "seguir adelante", pero el usuario puede tener que terminar a un precio de gas mucho más alto. Esto puede ser exacerbado por ataques de DoS y formas relacionadas.

· Algunas aplicaciones dependen de que exista un límite superior en la "latencia" de los mensajes de fragmentos cruzados (por ejemplo, el ejemplo de trenes y hoteles). Al carecer de garantías, tales aplicaciones tendrían que tener márgenes de seguridad ineficientemente grandes.


 Se podría intentar crear un sistema en el que los mensajes asíncronos generados en algún fragmento activen automáticamente los efectos en su fragmento de destino después de cierto número de bloques. Sin embargo, esto requiere que cada cliente de cada fragmento inspeccione activamente todos los demás fragmentos en el proceso de cálculo de la función de transición de estado, que podría decirse que es una fuente de ineficiencia. El enfoque de compromiso más conocido es este: cuando se incluye un recibo del fragmento A en altura height_a en el fragmento B a altura height_b, si la diferencia en alturas de bloque excede MAX_HEIGHT, todos los validadores del fragmento B crearon bloques de height_a + MAX_HEIGHT + 1 hasta height_b - 1 son penalizados, y esta penalización aumenta exponencialmente. Una parte de estas penalizaciones se otorga al validador que finalmente incluye el bloqueo como recompensa. Esto mantiene la función de transición de estado simple, a la vez que incentiva fuertemente el comportamiento correcto.

# Espera, pero ¿qué ocurre si un atacante envía una llamada de fragmentos cruzados desde cada fragmento al fragmento X al mismo tiempo? ¿No sería matemáticamente imposible incluir todas estas llamadas a tiempo?

 Correcto; esto es un problema. Aquí hay una solución propuesta. Para realizar una llamada de fragmentos cruzados desde el fragmento A al fragmento B, el llamante debe precomprar "gas de fragmento B" (esto se realiza a través de una transacción en el fragmento B y se registra en el fragmento B). El gas del fragmento B congelado tiene una tasa de demora rápida: una vez ordenado, pierde 1 / k de su potencia restante en cada bloque. Una transacción en el fragmento A puede enviar el gas congelado del fragmento B junto con el recibo que crea, y se puede usar en el fragmento B de forma gratuita. Los bloques Shard B asignan espacio de gas adicional específicamente para este tipo de transacciones. Tenga en cuenta que debido a las reglas de demora, puede haber como máximo GAS_LIMIT * k valor de gas congelado para un fragmento dado disponible en cualquier momento, que sin duda puede llenarse en k bloques (de hecho, incluso más rápido debido a la demora, pero podemos necesitar este espacio debido a validadores maliciosos). En caso de que demasiados validadores no incluyan los recibos maliciosamente, podemos hacer que las penalizaciones sean más justas al eximir a los validadores que llenan el "espacio de recepción" de sus bloques con tantos recibos como sea posible, empezando por los más antiguos.

 Bajo este mecanismo previo a la compra, un usuario que quiera realizar una operación de cross-shard pre-comprará gas para todos los fragmentos que en la operación entrará, sobre comprando para tener en cuenta la demora. Si la operación crearía un recibo que activa una operación que consume 100000 de gas en el fragmento B, el usuario precompraría 100000 * e (es decir, 271818) de gas congelado de fragmento B. Si esa operación a su vez gastaría 100000 de gas en el fragmento C (es decir, dos niveles de indirección), el usuario necesitaría precomprar 100000 * e ^ 2 (es decir, 738906) de gas congelado en shard-C. Observe cómo una vez confirmadas las compras, el usuario inicia la operación principal, puede estar seguro de que estará aislado de los cambios en el mercado del precio del gas, a menos que los validadores pierdan voluntariamente grandes cantidades de dinero de las sanciones por no inclusión.

# ¿Gas congelado? Esto suena interesante no solo por las operaciones _cross-shard_, sino también por la programación _intra-shard_ confiable

 En efecto; podría comprar un fragmento congelado A gas dentro del fragmento A, y enviar una llamada garantizada de fragmentos cruzados del fragmento A a sí mismo. Aunque tenga en cuenta que este esquema solo admitiría la programación en intervalos de tiempo muy cortos, y la programación no sería exacta para el bloque; solo se garantizará que ocurra dentro de un período de tiempo.

# ¿La programación garantizada, ambos intra-shard y cross-shard, ayuda contra la mayoría de las colisiones que intentan censurar las transacciones?

 Sí. Si un usuario no puede obtener una transacción porque los validadores están filtrando la transacción y no aceptan ningún bloque que la incluya, entonces el usuario podría enviar una serie de mensajes que activan una cadena de mensajes programados garantizados, el último de los cuales reconstruye la transacción dentro del EVM y lo ejecuta. La prevención de tales técnicas de elusión es prácticamente imposible sin cerrar por completo la función de programación garantizada y restringir en gran medida todo el protocolo, por lo que los validadores malintencionados no podrían hacerlo fácilmente.

# ¿Podrían las cadenas de bloques fragmentadas hacer un mejor trabajo al tratar con particiones de red?

 Los esquemas descritos en este documento no ofrecerían ninguna mejora sobre blockchains no fragmentados; de manera realista, cada fragmento terminaría con algunos nodos en ambos lados de la partición. Ha habido llamadas (por ejemplo, [Juan Benet de IPFS](https://www.youtube.com/watch?v=cU-n_m-snxQ)) para construir redes escalables con el objetivo específico de que las redes puedan dividirse en fragmentos según sea necesario y así continuar operando tanto como sea posible en condiciones de partición de red,  pero hay retos criptoeconómicos no triviales para hacer que esto funcione bien.

 Un desafío importante es que si queremos tener un sharding basado en la ubicación para que las particiones geográficas de red limiten mínimamente la cohesión intra-shard (con el efecto secundario de tener muy bajas latencias intra-shard y por lo tanto tiempos de bloque intra-shard muy rápidos), entonces necesitamos una forma en la cual los validadores elijan en qué fragmentos participan. Esto es peligroso, porque permite clases de ataques mucho más grandes en el modelo de mayoría honesta / descoordinada y, por lo tanto, ataques más baratos con mayores factores de duelo en el modelo de Zamfir. El sharding para seguridad de partición geográfica y fragmentación a través de muestreo aleatorio para la eficiencia son dos cosas fundamentalmente diferentes.

 En segundo lugar, sería necesario pensar más en cómo se organizan las aplicaciones. Un modelo probable en una cadena de bloques fragmentada como se describe arriba es que cada "aplicación" esté en algún fragmento (al menos para aplicaciones de pequeña escala); sin embargo, si queremos que las aplicaciones sean resistentes a la partición, significa que todas las aplicaciones deberían ser cruzadas hasta cierto punto.

 Una posible vía para resolver esto es crear una plataforma que ofrezca ambos tipos de fragmentos: algunos fragmentos serían fragmentos "globales" de mayor seguridad que se muestrearían aleatoriamente, y otros fragmentos serían fragmentos "locales" de menor seguridad que podrían tener propiedades tales como tiempos de bloqueo ultrarrápidos y tarifas de transacción más económicas. Los fragmentos de muy baja seguridad podrían incluso utilizarse para la publicación de datos y la mensajería.

# ¿Cuáles son los desafíos únicos de empujar el escalado pasado n = O (c ^ 2)?

 Hay varias consideraciones. En primer lugar, el algoritmo debería convertirse de un algoritmo de dos capas a un algoritmo de n capas apilables; esto es posible, pero es complejo. En segundo lugar, n / c (es decir, la relación entre la carga de cálculo total de la red y la capacidad de un nodo) es un valor que está cerca de dos constantes: primero, si se mide en bloques, un intervalo de tiempo de varias horas, que es un "tiempo máximo de confirmación de seguridad" aceptable, y segundo, la relación entre recompensas y depósitos (un cálculo temprano sugiere un tamaño de depósito de 32 ETH y una recompensa de bloque ETH de 0,05 para Casper). Esto último tiene la consecuencia de que si las recompensas y penalizaciones en un fragmento se escalan para estar en la escala de depósitos del validador, el costo de continuar un ataque contra un fragmento será O (n) en tamaño.

 Ir por encima de c ^ 2 probablemente implique un mayor debilitamiento de los tipos de garantías de seguridad que puede proporcionar un sistema, y permitir a los atacantes atacar fragmentos individuales de ciertas maneras durante largos períodos de tiempo a un costo medio, aunque todavía debería ser posible evitar un estado no válido de ser finalizado y evitar que el estado finalizado sea revertido a menos que los atacantes estén dispuestos a pagar un costo de O (n). Sin embargo, las recompensas son grandes: una cadena de bloques súper cuadráticamente fragmentada podría utilizarse como una herramienta de propósito general para casi todas las aplicaciones descentralizadas, y podría mantener tarifas de transacción que hace que su uso sea prácticamente gratuito.