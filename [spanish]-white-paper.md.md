<!-- TITLE: [Spanish] White Paper.md -->



### Un contrato inteligente de próxima generación y una plataforma de aplicación descentralizada

El desarrollo de Bitcoin de Satoshi Nakamoto en el año 2008[<sup>[1a]</sup>](http://nakamotoinstitute.org/bitcoin/)[<sup>[1b]</sup>](http://www.newyorker.com/magazine/2011/10/10/the-crypto-currency)–2009[<sup>[1c]</sup>](https://en.bitcoin.it/wiki/Category:History)[<sup>[1d]</sup>](https://blockexplorer.com/block/000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f) ha sido aclamado como una evolución radical en el dinero y la moneda, siendo el primer ejemplo de un activo digital que simultáneamente no tiene respaldo o valor intrínseco[<sup>[2]</sup>](https://bitcoinmagazine.com/articles/you-say-bitcoin-has-no-intrinsic-value-twenty-two-reasons-to-think-again-1399454061/) ni un emisor o controlador centralizado. Sin embargo, otra parte del experimento Bitcoin, discutiblemente más importante, es la subyacente tecnología blockchain como una herramienta de consenso distribuido. La atención está rápidamente comenzando a trasladarse a este otro aspecto de Bitcoin. Las aplicaciones alternativas comúnmente citadas de la tecnología blockchain incluyen el uso de activos digitales en blockchain para representar monedas personalizadas e instrumentos financieros(colored coins),[<sup>[3]</sup>](https://docs.google.com/a/buterin.com/document/d/1AnkP_cVZTCMLIzw4DvsW6M8Q2JC0lIzrTLuoWu2z1BE/edit) la posesión de un dispositivo físico subyacente (propiedad inteligente),[<sup>[4]</sup>](https://en.bitcoin.it/wiki/Smart_Property) activos no fungibles tales como nombres de dominio (Namecoin)[<sup>[5]</sup>](http://namecoin.org) , así como aplicaciones más complejas que implican tener activos digitales controlados directamente por un código que implementa reglas arbitrarias conocidas como contratos inteligentes[<sup>[6]</sup>](https://en.bitcoin.it/wiki/Contracts) o incluso organizaciones autónomas descentralizadas basadas en blockchain (DAOs por sus siglas en inglés)[<sup>[7]</sup>](http://bitcoinmagazine.com/7050/bootstrapping-a-decentralized-autonomous-corporation-part-i/)

Lo que Ethereum intenta es proveer un blockchain con un lenguaje de programación integrado Turing completo, completamente desarrollado que puede ser utilizado para crear "contratos" que pueden ser utilizados para codificar funciones de transición de estado arbitrarias, permitiendo a los usuarios crear cualquiera de los sistemas arriba descritos, así como muchos otros que aún no hemos imaginados, simplemente escribiendo la lógica en pocas líneas de código.

### Tabla de contenidos

* [Introducción a Bitcoin y Conceptos existentes](#introduccion-a-bitcoin-y-conceptos-existentes)
    * [Historia](#historia)
    * [Bitcoin como un sistema de transición de estado](#bitcoin-como-un-sistema-de-transición-de-estado)
    * [Minería](#minería)
    * [Árboles Merkle](#arboles-merkle)
    * [Aplicaciones Alternativas de la cadena de bloques](#aplicaciones-alternativas-de-la-cadena-de-bloques)
    * [Scripting](#scripting)

* [Ethereum](#ethereum)
    * [Cuentas Ethereum](#cuentas-ethereum)
    * [Mensajes y transacciones](#mensajes-y-transacciones)
    * [Función de transición del estado de Ethereum](#funcion-de-transicion-de-estado-de-ethereum)
    * [Ejecución de código](#code-execution)
    * [Cadena de bloques y minería](#cadena-de-bloques-y-mineria)

* [Aplicaciones](#aplicaciones)
    * [Sistemas de Moneda](#sistemas-de-monedas)
    * [Derivados financieros](#derivados-financieros)
    * [Sistemas de identidad y reputación](#sistemas-de-identidad-y-reputacion)
    * [Almacenamiento de archivos descentralizado](#almacenamiento-de-archivos-descentralizado)
    * [Organizaciones autónomas descentralizadas](#organizaciones-autonomas-descentralizadas)
    * [Aplicaciones adicionales](#aplicaciones-adicionales)

* [Miscelánea e inquietudes](#miscelanea-e-inquietudes)
    * [Implementación modificada de GHOST](#implementacion-modificada-de-ghost)
    * [Tarifas](#tarifas)
    * [Computación y Turing Completo](computacion-y-completitud-turing)
    * [Moneda y emisión](#moneda-y-emision)
    * [Centralización de minería](#centralizacion-de-mineria)
    * [Escalabilidad](#escalabilidad)

+ [Conclusión](#conclusion)
* [Notas, referencias y lecturas adicionales](#notas-referencias-y-lecturas-adicionales)

## Introducción a Bitcoin y conceptos existentes

### Historia

El concepto de moneda digital descentralizada, así como aplicaciones alternativas como registros propietarios, han estado alrededor por décadas. Los protocolos anónimos de dinero electrónico de los años ochenta y noventa se basaron principalmente en un primitivo criptográfico conocido como Chaumian Blinding.[<sup>[8]</sup>](https://en.wikipedia.org/wiki/Blind_signature)

Chaumian Blinding proporcionó estas nuevas monedas con altos grados de privacidad, pero sus protocolos subyacentes en gran medida no lograron ganar tracción debido a su dependencia de un intermediario centralizado. En 1988, el b-money de Wei Dai[<sup>[10]</sup>](http://www.weidai.com/bmoney.txt) se convirtió en la primer propuesta que introduce la idea de crear dinero a través de la solución de rompecabezas computacionales así como del consenso descentralizado, pero la propuesta era escasa en los detalles sobre cómo podría ser implementado el consenso descentralizado. En 2005, Hal Finney introduce el concepto de prueba de trabajo[<sup>[10]</sup>](http://www.finney.org/~hal/rpow/), un sistema que usa ideas de b-money junto con rompecabezas de dificultad computacional de Adam Back para crear el concepto de criptomoneda, pero una vez más no estuvo a la altura del ideal pues dependía de cómputo de confianza como backend. En 2009, una moneda descentralizada fue por primera vez implementada en la práctica por Satoshi Nakamoto,[<sup>[1c]</sup>](https://en.bitcoin.it/wiki/Category:History)[<sup>[1d]</sup>](https://blockexplorer.com/block/000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f)combinando las bases establecidas para el manejo de posesión mediante de una llave criptográfica pública con un algoritmo de consenso para mantener el registro de quien posee monedas, conocido como "prueba de trabajo".


### Bitcoin como un sistema de transición de estado

![statetransition.png](https://raw.githubusercontent.com/ethereumbuilders/GitBook/master/en/vitalik-diagrams/statetransition.png)

Desde una punto de vista técnico, el libro mayor de una criptomoneda como el Bitcoin puede ser considerado como un sistema de transición de estado, donde hay un "estado" que consiste en el estado de propiedad de todos los bitcoins existentes y una "función de transición de estado" que toma un estado y una transacción y produce como salida un nuevo estado que es el resultado. 

En un sistema bancario estándar, por ejemplo, el estado es un balance, una transacción es una solicitud para mover $X de A a B, y la función de transición de estado reduce el valor de la cuenta de A en $X y aumenta el valor de B cuenta por $X. Si la cuenta de A tiene menos de $ X en primer lugar, la función de transición de estado devuelve un error. Por lo tanto, se puede definir formalmente:

    APLICAR(S,TX) -> S' || ERROR

En el sistema bancario definido arriba:

    APLICAR({ Alice: $50, Bob: $50 }, "envía $20 de Alice a Bob") = { Alice: $30, Bob: $70 }

Pero:

    APLICAR({ Alicia: $50, Bob: $50}, "envía %70 de Alice a Bob") = ERROR

El "estado" en Bitcoin es la colección de todas las monedas (técnicamente, resultados de transación no gastados" o UTXO) que han sido minados y aún no gastados, con cada UTXO teniendo una denominación y un dueño (definido por una dirección de 20 bytes que es esencialmente una llave criptográfica pública<sup>[Note 1]</sup>). 

Una transacción contiene una o más entradas, cada una haciendo referencia a un UTXO existente y a una firma criptográfica producida por la llave privada asociada a la dirección del dueño, y una o más salidas, cada una conteniendo un nuevo UTXO para para agregar al estado.

La función de transición `APLICAR(S,TX) -> S'` puede ser definida aproximadamente de la siguiente manera:
1. Para cada entrada en TX:
    * Si el UTXO referenciado no está en `S`, devuelve un error.
    * Si la firma proporcionada no coincide con el dueño del UTXO, devuelve un error.
2. Si la suma de las denominaciones de todas las entradas UTXO es menor que la suma de las denominaciones de todas las salidas UTXO, devuelve un error.
3. Devuelve `S'` con todas las entradas UTXO eliminadas y todas las salidas UTXO agregadas.

La primera mitad de el primer paso previene que el emisor de la transacción envíe monedas que no existen, la segunda mitad del primer paso previene que el emisor gaste monedas de otras personas, el segundo paso impone la conservación del valor. Para utilizar esto para pago, el protocolo es el siguiente. Supongamos que Alice quiere enviar 11.7 BTC a Bob. En primer lugar, Alice buscará un conjunto de UTXO disponible que posea y que totalizará al menos 11.7 BTC. Siendo realistas, Alice no podrá obtener exactamente 11.7 BTC; digamos que lo menos que puede obtener es 6 + 4 + 2 = 12. Luego crea una transacción con esas tres entradas y dos salidas. La primera salida será 11.7 BTC con la dirección de BOB como su propietario, y la segunda salida será el restante 0.3 BTC "cambio". Si Alice no reclama este cambio enviándolo a una dirección de su propiedad, el minero podrá reclamarlo.

### Minería

![block_picture.jpg](https://raw.githubusercontent.com/ethereumbuilders/GitBook/master/en/vitalik-diagrams/block.png)

Si tenemos acceso a un servicio centralizado confiable, este sistema sería trivial de implementar; podría ser codificado exactamente como se describió, utilizando un disco duro de un servidor centralizado para mantener el registro del estado. Sin embargo, con Bitcoin estamos tratando de construir un sistema de moneda descentralizado, por ello necesitamos combinar el sistema de transición de estado con un sistema de consenso para garantizar que todos estén de acuerdo en el orden de las transacciones. El proceso de consenso descentralizado de Bitcoin requiere los nodos en la red intenten continuamente producir paquetes de transacciones llamados "bloques". La red está destinada a crear un bloque aproximadamente cada diez minutos, cada bloque conteniendo una estampa de tiempo, un [nonce](https://es.bitcoin.it/wiki/Nonce), una referencia a (es decir, hash) del bloque anterior y una lista de todas las transacciones que han tenido lugar desde el anterior bloque. Con el tiempo esto crea una "Cadena de bloques" (Blockchain) persistente y en constante crecimiento que se actualiza continuamente para representar el estado más reciente del libro mayor de Bitcoin.

Los algoritmos para comprobar si un bloque es válido, expresado en este paradigma como sigue:

1. Verifica si el bloque previo referenciado por el bloque existe y es válido.
2. Verifica que la estampa de tiempo del bloque es mayor que la del bloque previo
y menor que 2 horas en el futuro.
3. Verifica que la prueba de trabajo en el bloque sea válida.
4. Sea `S[0]` el estado al final del bloque previo.
5. Suponiendo `TX` como la lista de transacciones del bloque con `n` transacciones. Para todo `i` en `0...n-1`, implica que `S[i+1] = APLICA(S[i+1], TX[i])` Si alguna aplicación devuelve un error, sale y devuelve falso.
6. Devuelve true, y registra `S[n]` como el estado al final de este bloque

Esencialmente, cada transacción en el bloque deberá proveer un estado de transición válido del que era es estado canónico antes de que la transacción fuera ejecutada a algún nuevo estado. Tenga en cuenta que el estado no está codificado en el bloque de ninguna manera; es puramente una abstracción que debe ser recordada por el nodo de validación y sólo puede (de una forma segura) computarse para cualquier bloque comenzando desde el estado de génesis y aplicando secuencialmente cada transacción en el bloque. Además, tenga en cuenta que el orden en el cual el minero incluye las transacciones en el bloque importa; si hay dos transacciones A y B en un bloque de modo que B gasta un UTXO creado por A, entonces el bloque será válido si A entra antes que B, pero no de otra manera.

La condición de validez presente en la lista anterior que no se encuentra en otros sistemas es el requisito de "prueba de trabajo". La condición precisa es que el hash doble SHA254[<sup>[13]</sup>](https://en.wikipedia.org/wiki/SHA-2) de cada bloque, tratado como un número de 256 bits, debe ser menor que un objetivo dinámicamente ajustado, que a partir del momento de escribir esto es aproximadamente 2<sup>187</sup>. 

El propósito de esto es hacer la creación de los bloques computacionalmente "difícil", evitando así que los ataques Sybil rehagan toda la cadena de bloques, a su favor. Debido a que SHA256 está diseñado para ser una función pseudoaleatoria completamente impredecible, el único camino para crear un bloque válido es simplemente prueba y error, repetidamente incrementando el nonce y y viendo si el hash nuevo coincide.

Al momento de escribir esto, para un objetivo de ~2<sup>187</sup>, la red debe realizar un promedio de ~ 2<sup>69</sup> intentos antes de encontrar un bloque válido; en general, el objetivo es re-calibrado por la red cada 2016 bloques, de modo que en promedio, un nodo en la red produce un nuevo bloque cada diez minutos. Con la finalidad de compensar a los mineros por este trabajo computacional, el minero de cada bloque tiene derecho a incluir una transacción que se 12.5 BTC de la nada. Además, si cualquier transacción tiene una denominación total más allá en sus entradas que en sus productos, la diferencia también le corresponde al minero como una "tarifa de transacción". Por cierto, este es también el único mecanismo por el cual se emiten BTC; el estado de génesis no contenía ninguna moneda en absoluto.

En favor de un mejor entendimiento del propósito de minería, examinemos qué sucede en el evento de un atacante malicioso. Debido a que la subyacente criptografía del Bitcoin es segura, el objetivo del atacante será la única parte del sistema Bitcoin que no está protegida criptográficamente de forma directa: el orden de las transacciones. La estrategia del atacante es simple:

1. Enviar 100 BTC a un comerciante a cambio de un producto (preferiblemente un bien digital de entrega rápida)
2. Espera a que el producto sea entregado
3. Produce otra transacción enviando la misma cantidad de 100 BTC a si mismo.
4. Trata de convencer a la red que la transacción a él mismo ocurrió primero.

Una vez que el paso (1) sucede, después de algunos minutos algún minero  incluirá la transacción en el bloque, digamos el bloque número 270,000. Después de una hora, 5 o más bloques han sido añadidos a la cadena después de ese bloque, con cada uno de esos bloque indirectamente apuntando a la transacción, así "confirmando" la transacción.

En este punto el atacante crea otra transacción enviando 100 BTC a sí mismo. Si el atacante simplemente libera al aire la transacción, esta no sería procesada; los minero tratarían de correr `APLICAR(S,TX)` y se percatarían que `TX` utiliza un UTXO que ya no es parte del estado. En vez de esto, el atacante crea un "fork" de la cadena del bloques Bitcoin, comenzando por minar otra versión del bloque 270,000 apuntando al mismo bloque 269,999 como padre pero con la nueva transacción en lugar de la anterior. Puesto que la información del bloque es diferente esto requiere rehacer la prueba de trabajo del bloque de interés. 

Además, la nueva versión del bloque 270,000 del atacante tiene un hash diferente, así que los bloques originales 270,001 al 270,005 no 'apuntan' a este; Así, la cadena original y la nueva cadena del atacante están completamente separadas. La regla es que el bloque con la cadena más larga es el verdadero, y así los mineros legítimos trabajarán en la cadena 270,005 mientras que el atacante sólo está trabajando en la cadena 270,000. Para que el atacante pueda hacer su cadena la más larga, necesitaría tener mayor poder computacional que el resto de la red combinada para poder alcanzarla (por lo tanto, "51% ataque"). Los bloques bitcoin dependen del hash de todos los bloques anteriores. 

Un atacante con inmenso poder computacional puede rehacer la prueba de trabajo (PoW) por una considerada suma de bloques y eventualmente ganar muchos bitcoins, pero como es descrito en la publicación de Satoshi,[<sup>[1a]</sup>](http://nakamotoinstitute.org/bidtcoin/) la recompensa de minar un bloque válido es mucho más mayor a la de quebrantar la red. Pero a la luz de la caida en recompensas de minería, esto último puede no ser verdad.

### Árboles Merkle
![SPV1 in bitcoin](https://raw.githubusercontent.com/ethereumbuilders/GitBook/master/en/vitalik-diagrams/spv1.png)

_01: basta con presentar solo un pequeño número de nodos en un árbol de Merkle para dar una prueba de la validez de la rama._

![SPV2 in bitcoin](https://raw.githubusercontent.com/ethereumbuilders/GitBook/master/en/vitalik-diagrams/spv2.png)

_02: cualquier intento de cambiar cualquier parte del arbol Merkle eventualmente llevará a inconsistencias en algún lugar de la cadena._

Una importante característica de escalabilidad de Bitcoin es que el bloque es guardado en una estructura de datos de varios niveles. El "hash" de un bloque es en realidad solo el hash del encabezado del bloque, un fragmento de datos de aproximadamente 200 bytes que contiene la marca de tiempo, nonce, hash del bloque anterior y el hash raíz de una estructura de datos llamada Árbol Merkle que almacena todas las transacciones en el bloque. Un árbol Merkle es un tipo de árbol binario, compuesto por un conjunto de nodos hoja en la parte inferior del árbol que contiene los datos subyacentes, un conjunto de nodos intermedios donde cada nodo es el hash de sus dos hijos, y finalmente un único nodo raíz, también formado a partir del hash de sus dos hijos, que representa la "parte superior" del árbol. El propósito del árbol de Merkle es permitir que los datos en un bloque se entreguen por partes: un nodo puede descargar sólo el encabezado de un bloque desde una fuente, la pequeña parte del árbol relevante para ellos desde otra fuente, y aún estar seguro que todos los datos son correctos. La razón por la cual esto funciona es que los hash se propagan hacia arriba: si un usuario malicioso intenta intercambiar una transacción falsa en la parte inferior de un árbol de Merkle, este cambio causará un cambio en el nodo anterior y luego un cambio en el nodo anterior, finalmente cambiando la raíz del árbol y por lo tanto, el hash del bloque, haciendo que el protocolo lo registre como un bloque completamente diferente (casi con certeza con una prueba inválida de trabajo).

El protocolo árbol Merkle es discutiblemente esencial para la sostenibilidad en el largo plazo. Un "nodo completo" en la red Bitcoin, uno que guarda y procesa la totalidad de cada bloque, ocupa cerca de 15GB de espacio en la red Bitcoin a partir de abril de 2014, y está creciendo más de un gigabyte por mes. Actualmente, esto es viable para algunas computadoras de escritorio y no para teléfonos, y más adelante en el futuro solo las empresas y los aficionados podrán participar. Un protocolo conocido como "verificación de pago simplificada" (SPV) permite que exista otra clase de nodos, llamados "nodos ligeros", que descargan los encabezados de los bloques, verifican la prueba de trabajo en los encabezados del bloque y luego solo descargan las "ramas". "Asociado con transacciones que son relevantes para ellos- Esto permite que los nodos ligeros determinen con una fuerte garantía de seguridad cuál es el estado de cualquier transacción de Bitcoin, y su saldo actual, mientras se descarga solo una porción muy pequeña de la cadena de bloques completa.

### Aplicaciones alternativas de la cadena de bloques

La idea de tomar la subyacente idea de la cadena de bloques y aplicarla a otros conceptos también tiene una larga historia. En 2005, Nick Szabo presenta el concepto de títulos de propiedad seguros con autorización del propietario,[<sup>[14]</sup>](http://nakamotoinstitute.org/secure-property-titles) un documento que describe como "nuevos avances en la tecnología de bases de datos replicadas" permitirán un sistema basado en cadenas de bloques para almacenar un registro de quién posee qué tierra, creando un marco elaborado que incluye conceptos como homestanding, posesión adversa y el impuesto Gregoriano a la tierra. Sin embargo, lamentablemente no existía un sistema de base de datos replicado eficaz disponible en ese momento, por lo que el protocolo nunca se implementó en la práctica. Sin embargo, después de 2009, una vez que se desarrolló el consenso descentralizado de Bitcoin, rápidamente comenzaron a surgir varias aplicaciones alternativas.