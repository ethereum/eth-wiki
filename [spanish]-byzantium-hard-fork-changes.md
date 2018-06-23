<!-- TITLE: [Spanish] Byzantium Hard Fork changes -->



# ¿Qué cambios se incluyen en la bifurcación de Byzantium?

Las siguientes actualizaciones están incluidas:
* Incorporación del código de operación 'REVERT', que permite el manejo de errores sin consumir todo el gas [(EIP 140)](https://github.com/ethereum/EIPs/pull/206)
* Los recibos de transacción, ahora incluyen un campo de estado para indicar el éxito o el fracaso [(EIP 658)](https://github.com/ethereum/EIPs/pull/658)
* Incorporación de curva elíptica y multiplicación scalar en alt_bn128 [(EIP 196)](https://github.com/ethereum/EIPs/pull/213) y chequeo de emparejamiento [(EIP 197)](https://github.com/ethereum/EIPs/pull/212), permitiendo ZK-Snarks y otras *"cryptographic mathemagic™"*
* Soporte para la gran exponenciación modular de enteros [(EIP 198)](https://github.com/ethereum/EIPs/pull/198), habilitando  la verificación RSA y otras aplicaciones criptográficas.
* Soporte para valores de retorno de longitud variable [(EIP 211)](https://github.com/ethereum/EIPs/pull/211)
* Incorporación del código de operación 'STATICCALL', permitiendo llamadas que no cambian el estado a otros contratos [(EIP 214)](https://github.com/ethereum/EIPs/pull/214)
* Cambios en la fórmula de ajuste de dificultad para tomar en cuenta los "*uncles*" [(EIP 100)](https://github.com/ethereum/EIPs/issues/100)
* Retraso de la edad de hielo/bomba de dificultad en 1 año, y reducción de la recompensa por bloque minado, de 5 a 3 ethers [(EIP 649)](https://github.com/ethereum/EIPs/pull/669)

Fuente: extracto con las mismas palabras de este [post del blog de Ethereum](https://web.archive.org/web/20180104055521/https://blog.ethereum.org/2017/10/12/byzantium-hf-announcement/).