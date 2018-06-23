<!-- TITLE: [Spanish]Proof of Stake FAQ -->



## Que es la Prueba de Participación

**Prueba de participación (PoS) es una categoría de algoritmos de consenso para blockchains públicas que dependen del interés económico de un validador en la red**. En las blockchains públicas basadas en prueba de trabajo (PoW) (por ejemplo, Bitcoin y la implementación actual de Ethereum), el algoritmo recompensa a los participantes que resuelven encriptaciones criptográficas para validar transacciones y crear nuevos bloques (es decir, minería). En las blockchains públicas basadas en PoS (por ejemplo, la próxima implementación de Casper de Ethereum), un grupo de validadores se turnan para proponer y votar el siguiente bloque, y el peso del voto de cada validador (es decir, la validación) depende del tamaño de su depósito. Las ventajas significativas de PoS incluyen **seguridad, menor riesgo de centralización y eficiencia energética**.

 En general, un algoritmo de prueba de participación se ve de la siguiente manera. La cadena de bloques realiza un seguimiento de un conjunto de validadores, y cualquiera que tenga la criptomoneda base de la cadena de bloques (en el caso de Ethereum, el Ether "Ξ") puede convertirse en un validador al enviar un tipo especial de transacción que **bloquea su Ether en un depósito**. El proceso de crear y aceptar nuevos bloques se realiza a través de un algoritmo de consenso en el que pueden participar todos los validadores actuales.

 Hay muchos tipos de algoritmos de consenso y muchas formas de asignar recompensas a los validadores que participan en el algoritmo de consenso, por lo que hay muchos "_sabores_" de prueba de participación. Desde una perspectiva algorítmica, hay dos tipos principales: prueba de participación basada en la blockchain y prueba de participación al estilo [BFT](https://en.wikipedia.org/wiki/Byzantine_fault_tolerance).

 En la **prueba de participación basada en blockchain**, el algoritmo selecciona pseudoaleatoriamente un validador durante cada intervalo de tiempo (por ejemplo, cada período de 10 segundos puede ser un intervalo de tiempo) y asigna ese validador al derecho de crear un solo bloque, y este bloque debe apuntar a un bloque anterior (normalmente el bloque al final de la cadena que anteriormente era más larga), y con el tiempo la mayoría de los bloques convergen en una sola cadena en constante crecimiento.

 En la **prueba de participación al estilo BFT**, a los validadores se les asigna **aleatoriamente** el derecho de proponer bloques, pero acordar qué bloque es canónico se realiza a través de un proceso de múltiples rondas donde cada validador envía un "voto" para un bloque específico durante cada ronda, y al final del proceso, todos los validadores (honestos y en línea) acuerdan permanentemente si un bloque determinado es parte de la cadena o no. Tenga en cuenta que los bloques aún pueden estar encadenados juntos; la diferencia clave es que el consenso en un bloque puede venir dentro de un bloque, y no depende de la longitud o el tamaño de la cadena después de él.

# ¿Cuáles son los beneficios de la prueba de participación en lugar de la prueba de trabajo?

 Vea [filosofía de diseño para la prueba de participación](https://medium.com/@VitalikButerin/a-proof-of-stake-design-philosophy-506585978d51) para obtener un argumento más extenso.

En resumen:

**· No es necesario consumir grandes cantidades de electricidad** para asegurar una cadena de bloques (por ejemplo, se estima que tanto Bitcoin como Ethereum queman más de $ 1 millón en costos de electricidad y hardware por día como parte de su mecanismo de consenso).



**·** Debido a la falta de alto consumo de electricidad, **no hay la necesidad de emitir tantas monedas nuevas** para motivar a los participantes a seguir participando en la red. En teoría, incluso es posible tener una emisión neta negativa, en la que una parte de las tarifas de transacción se "quema" y, por lo tanto, el suministro disminuye con el tiempo.

**·** La prueba de participación abre la puerta a una gama más amplia de técnicas que utilizan el diseño de mecanismos teóricos de juegos para **desalentar mejor a los grupos centralizados** de formarse y, si se forman, actuar de maneras que son perjudiciales para la red (por ejemplo, [interesados en la minería](https://www.cs.cornell.edu/~ie53/publications/btcProcFC.pdf) en prueba de trabajo).

**· Reducción de los riesgos de centralización**, ya que las economías de escala son mucho menos problemáticas. $ 10 millones de monedas le darán ganancias exactamente 10 veces más altas que $ 1 millón de monedas, sin ganancias adicionales desproporcionadas, porque en el nivel más alto puede permitirse un mejor equipo de producción en masa.

**·** La capacidad de utilizar sanciones económicas para **hacer que varias formas de ataques del 51% sean mucho más costosas** que la prueba de trabajo, parafraseando a Vlad Zamfir, "es como si tu granja de ASIC se hubiera quemado si participas en un ataque del 51%".


# ¿Cómo encaja la prueba de participación en la investigación tradicional de tolerancia a fallas bizantina?

 Hay varios resultados fundamentales de la investigación de tolerancia a fallas bizantinas que se aplican a todos los algoritmos de consenso, incluidos algoritmos de consenso tradicionales como PBFT, pero también cualquier prueba de algoritmo de participación y, con el modelado matemático adecuado, prueba de trabajo.

Los resultados clave incluyen:

**· [Teorema CAP](https://en.wikipedia.org/wiki/CAP_theorem)** - "en los casos en que se produce una partición de red, debe elegir la coherencia o la disponibilidad, no puede tener ambas". El argumento intuitivo es simple: si la red se divide a la mitad, y en una mitad envío una transacción "envíe mis 10 monedas a A" y en la otra envíe una transacción "envíe mis 10 monedas a B", entonces o bien el sistema no está disponible, ya que una o ambas transacciones no se procesarán o se volverá inconsistente, ya que la mitad de la red verá la primera transacción completada y la otra mitad verá la segunda transacción completada. Tenga en cuenta que el teorema CAP no tiene nada que ver con la escalabilidad; se aplica por igual a sistemas fragmentados y no fragmentados.


**· [Imposibilidad de FLP](http://the-paper-trail.org/blog/a-brief-tour-of-flp-impossibility/)** - en una configuración asíncrona (es decir, no hay límites garantizados en la latencia de la red, incluso entre nodos que funcionan correctamente), no es posible crear un algoritmo que garantice alcanzar el consenso en cualquier cantidad de tiempo finita específica, incluso si un nodo defectuoso / deshonesto está presente. Tenga en cuenta que esto NO descarta los [algoritmos de "Las Vegas"](https://en.wikipedia.org/wiki/Las_Vegas_algorithm) que tienen cierta probabilidad en cada ronda de lograr el consenso y, por lo tanto, lograrán el consenso en T segundos, con una probabilidad exponencialmente cercana a 1 a medida que T crece; esta es, de hecho, la "puerta de escape" que usan muchos algoritmos de consenso exitosos.






**· Límites en la tolerancia a fallas** - del [documento DLS](http://groups.csail.mit.edu/tds/papers/Lynch/jacm88.pdf) tenemos: (i) los protocolos que se ejecutan en un modelo de red parcialmente síncrona (es decir, hay un límite en la latencia de la red pero no sabemos con anticipación qué es) pueden tolerar hasta 1 / 3 fallas arbitrarias (es decir, "bizantinas"), (ii) protocolos determinísticos en un modelo asincrónico (es decir, sin límites en la latencia de la red) no pueden tolerar fallas (aunque su documento no menciona que los [algoritmos aleatorios](https://link.springer.com/chapter/10.1007%2F978-3-540-77444-0_7) pueden con hasta 1/3 tolerancia a fallas), (iii) protocolos en un modelo síncrono (es decir, latencia de red garantizada menor que la conocida d) pueden, sorprendentemente, tolerar hasta 100% de tolerancia a fallas, aunque existen restricciones sobre lo que puede suceder cuando más de o igual a la mitad de los nodos son defectuosos. Tenga en cuenta que el modelo "autentificado bizantino" es el que vale la pena considerar, no el "bizantino"; la parte "autentificada" significa esencialmente que podemos usar la criptografía de clave pública en nuestros algoritmos, que en los tiempos modernos está muy bien investigada y es muy barata.

 La prueba del trabajo ha sido [analizada rigurosamente por Andrew Miller y otros](https://socrates1024.s3.amazonaws.com/consensus.pdf), y encaja en la imagen como un algoritmo que depende de un modelo de red síncrona. Podemos modelar la red como si estuviera compuesta de un número casi infinito de nodos, con cada nodo representando una unidad muy pequeña de potencia de cálculo y con una probabilidad muy pequeña de poder crear un bloque en un período determinado. En este modelo, el protocolo tiene un 50% de tolerancia a fallas asumiendo latencia de red cero, ~ 46% (Ethereum) y ~ 49.5% (Bitcoin) tolerancia a fallas bajo condiciones observadas realmente, pero baja al 33% si la latencia de red es igual al bloque tiempo, y se reduce a cero a medida que la latencia de la red se aproxima al infinito.

 La prueba del consenso de participación se ajusta más directamente al molde de consenso tolerante a errores bizantino, ya que todos los validadores tienen identidades conocidas (direcciones estables de Ethereum) y la red realiza un seguimiento del tamaño total del conjunto de validadores. Hay dos líneas generales de prueba de investigación de participación, una que mira modelos de red síncrona y otra que mira modelos de red parcialmente asíncronos. Los algoritmos de prueba de cadena "en cadena" casi siempre se basan en modelos de red síncrona, y su seguridad puede ser formalmente probada dentro de estos modelos de manera similar a como se puede probar la seguridad de los [algoritmos de prueba de trabajo](http://nakamotoinstitute.org/static/docs/anonymous-byzantine-consensus.pdf). También existe una línea de investigación que conecta el consenso tolerante a fallas bizantino tradicional en redes parcialmente sincrónicas para probar la participación, pero es más complejo de explicar; se tratará con más detalle en secciones posteriores.

 Los algoritmos de prueba de trabajo y la prueba en cadena de algoritmos de participación eligen la disponibilidad sobre la coherencia, pero los algoritmos de consenso del estilo BFT se inclinan más por la consistencia; [Tendermint](https://github.com/tendermint/tendermint) elige la consistencia explícitamente, y Casper utiliza un modelo híbrido que prefiere la disponibilidad pero que proporciona la mayor consistencia posible y hace que las aplicaciones en cadena y los clientes sean conscientes de cuán sólida es la garantía de consistencia en un momento dado.

 Tenga en cuenta que el descubrimiento de Ittay Eyal y Emin Gun Sirer [(minería interesada)](https://bitcoinmagazine.com/articles/selfish-mining-a-25-attack-against-the-bitcoin-network-1383578440/), que establece límites de 25% y 33% en la compatibilidad de incentivo de la minería Bitcoin según el modelo de red (es decir, la minería solo es compatible con incentivos si las colusiones mayores al 25% o 33% son imposible) no tiene NADA que ver con los resultados de la investigación tradicional de algoritmos de consenso, que no toca la compatibilidad de incentivos.



# ¿Cuál es el problema de "ninguna participación" y cómo puede solucionarse?


 En muchos algoritmos tempranos (todos basados en cadena) de prueba de participación, incluyendo Peercoin, solo hay recompensas por producir bloques y no hay penalizaciones. Esto tiene la desafortunada consecuencia de que, en el caso de que haya múltiples cadenas competidoras, es un incentivo para los validadores tratar de hacer bloques en la parte superior de cada cadena a la vez, solo para estar seguros:

![](https://raw.githubusercontent.com/vbuterin/diagrams/master/possec.png)


 En prueba de trabajo, hacerlo requeriría dividir el poder de computación a la mitad, y entonces no sería lucrativo:

![](https://github.com/vbuterin/diagrams/raw/master/powsec.png?raw=true)


 El resultado es que si todos los actores son estrictamente económicamente racionales, incluso si no hay atacantes, una cadena de bloques nunca alcanzará el consenso. Si hay un atacante, entonces el atacante solo necesita dominar nodos altruistas (que participarían exclusivamente en la cadena original), y no nodos racionales (quién jugaría tanto en la cadena original como en la del atacante), en contraste con la prueba de trabajo , donde el atacante debe dominar tanto a los altruistas como a los nodos racionales (o al menos amenazar de forma creíble con: ver [ataques P + épsilon](https://blog.ethereum.org/2015/01/28/p-epsilon-attack/)).


 Algunos argumentan que las partes interesadas tienen un incentivo para actuar correctamente y solo apostar en la cadena más larga para "preservar el valor de su inversión", sin embargo, esto ignora que este incentivo sufre una [tragedia de los problemas comunes](https://en.wikipedia.org/wiki/Tragedy_of_the_commons): cada actor individual puede tener solo un 1% de posibilidades de ser "pivotal" (es decir, estar en una situación en la que si participan en un ataque tiene éxito y si no participan falla), por lo que el soborno necesario para convencerlos personalmente de unirse a un ataque sería solo el 1% del tamaño de su depósito; por lo tanto, el soborno combinado requerido sería solo 0.5-1% de la suma total de todos los depósitos. Además, este argumento implica que cualquier situación de cero posibilidad de falla no es un equilibrio estable, ya que si la probabilidad de falla es cero, entonces todos tienen un 0% de posibilidades de ser cruciales.

 Esto se puede resolver a través de dos estrategias. La primera, descrito en términos generales bajo el nombre "Slasher" [aquí](https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm/) y desarrollado por Iddo Bentov [aquí](https://arxiv.org/pdf/1406.5694.pdf), implica penalizar a los validadores si crean bloques simultáneamente en cadenas múltiples, mediante la inclusión de pruebas de mala conducta (es decir, dos encabezados de bloque con signo conflictivo) en el blockchain como un punto posterior en el tiempo en el cual el depósito del validador malhecho se deduce apropiadamente. Esto cambia la estructura de incentivos por lo tanto:


![](https://github.com/vbuterin/diagrams/raw/master/slasher1sec.png?raw=true)






 Tenga en cuenta que para que este algoritmo funcione, el conjunto de validadores debe determinarse con anticipación. De lo contrario, si un validador tiene el 1% de la apuesta, entonces si hay dos ramas A y B, el 0.99% de las veces el validador solo podrá apostar en A y no en B, el 0.99% del tiempo el validador ser elegible para apostar en B y no en A, y solo el 0.01% del tiempo el validador será elegible para apostar en ambos. Por lo tanto, el validador puede con un 99% de eficacia probabilísticamente hacer una apuesta doble: apostar en A si es posible, apostar en B si es posible, y solo si la elección entre ambos es apuesta abierta en la cadena más larga. Esto solo se puede evitar si la selección del validador es la misma para cada bloque en ambas ramas, lo que requiere que los validadores se seleccionen a la vez antes de que la horquilla tenga lugar.

 Esto tiene sus propios defectos, incluyendo requerir que los nodos estén frecuentemente en línea para obtener una vista segura de la cadena de bloques, y abrir riesgos de colusión del validador de rango medio (es decir, situaciones donde, por ejemplo, 25 de 30 validadores consecutivos se reúnen y acuerdan antes de tiempo para implementar un ataque del 51% en los 19 bloques anteriores), pero si estos riesgos se consideran aceptables, entonces funciona bien.

 La segunda estrategia es simplemente castigar a los validadores por crear bloques en la cadena _equivocada_. Es decir, si hay dos cadenas competidoras, A y B, entonces si un validador crea un bloque en B, obtiene una recompensa de + R en B, pero el encabezado del bloque se puede incluir en A (en Casper esto se llama "_dunkle_") y en A, el validador sufre una penalización de -F (posiblemente F = R). Esto cambia el cálculo económico así:


![](https://github.com/vbuterin/diagrams/raw/master/slasher2sec.png?raw=true)


 La intuición aquí es que podemos replicar la economía de la prueba del trabajo dentro de la prueba de participación. En prueba de trabajo, también existe una penalización por crear un bloque en la cadena incorrecta, pero esta penalización está implícita en el entorno externo: los mineros tienen que gastar electricidad adicional y obtener o alquilar hardware adicional. Aquí, simplemente hacemos las penalizaciones explícitas. Este mecanismo tiene la desventaja de imponer un riesgo ligeramente mayor a los validadores (aunque el efecto debe suavizarse a lo largo del tiempo), pero tiene la ventaja de que no requiere que los validadores se conozcan con anticipación.

# Eso muestra cómo los algoritmos basados en blockchains resuelven nada en la participación. ¿Ahora cómo funcionan los algoritmos de prueba de estilo BFT?

 Los algoritmos de prueba de participación de tipo BFT (parcialmente síncrono) permiten a los validadores "votar" en bloques enviando uno o más tipos de mensajes firmados, y especifican dos tipos de reglas:

**· Condiciones de finalización**: reglas que determinan cuándo un hash dado se puede considerar finalizado.

**· Condiciones de recorte**: reglas que determinan cuándo se puede considerar que un validador determinado más allá de toda duda razonable, de haberse portado mal (por ejemplo, votar por múltiples bloques conflictivos al mismo tiempo). Si un validador activa una de estas reglas, se borrará todo su depósito.

 





 
 Para ilustrar las diferentes formas que pueden adoptar las condiciones de recorte, daremos dos ejemplos de condiciones de corte (de aquí en adelante, "2/3 de todos los validadores" es una abreviatura de "2/3 de todos los validadores ponderados por monedas depositadas", y asimismo para otros fracciones y porcentajes). En estos ejemplos, "PREPARACIÓN" y "COMPROMISO" deben entenderse simplemente como una referencia a dos tipos de mensajes que los validadores pueden enviar.

1. Si MESSAGES contiene mensajes de la forma ["COMMIT", HASH1, view] y ["COMMIT", HASH2, view] para la misma vista pero HASH1 y HASH2 diferentes firmados por el mismo validador, entonces ese validador se reduce.

2. Si MESSAGES contiene un mensaje de la forma ["COMMIT", HASH, view1], A MENOS ver view1 = -1 o también existen mensajes de la forma ["COMMIT", HASH, view1, view2] para alguna view2 específica, donde view2 <view1, firmado por 2/3 de todos los validadores, luego el validador que hizo que COMMIT sea recortado.

Hay dos deseos importantes para un conjunto adecuado de condiciones de corte:

**· Seguridad responsable**: si HASH1 y HASH2 están en conflicto (es decir, HASH1 y HASH2 son diferentes, y ninguno es un descendiente del otro) finalizados, entonces al menos 1/3 de todos los validadores deben haber violado alguna condición de corte.


**· Vida plausible**: a menos que 1/3 de todos los validadores hayan violado alguna condición de corte, existe un conjunto de mensajes que pueden producir 2/3 de validadores que finalicen algún valor.

 Si tenemos un conjunto de condiciones de recortes que satisfagan ambas propiedades, podemos incentivar a los participantes a enviar mensajes y comenzar a beneficiarse de la finalidad económica.


# ¿Qué es "la finalidad económica" en general?

 La finalidad económica es la idea de que una vez se finaliza un bloque, o más, generalmente una vez que se han firmado suficientes mensajes de ciertos tipos, entonces la única forma que en cualquier punto en el futuro la historia contendrá un bloque conflictivo, es si un gran número de la gente está dispuesta a quemar grandes cantidades de dinero. Si un nodo ve que se cumple esta condición para un bloque determinado, entonces tiene una seguridad muy fuerte desde el punto de vista económico de que ese bloque siempre será parte de la historia canónica en la que todos estén de acuerdo.

Hay dos "sabores" de finalidad económica:

1. Un bloque puede ser finalizado económicamente si un número suficiente de validadores han firmado declaraciones criptoeconómicas de la forma "Acepto perder X en todas las historias donde el bloque B no está incluido". Esto le da a los clientes la seguridad de que (i) B es parte de la cadena canónica, o (ii) los validadores perdieron una gran cantidad de dinero con el fin de engañarlos para que piensen que este es el caso.

2. Un bloque puede finalizarse económicamente si un número suficiente de validadores han firmado mensajes que expresan soporte para el bloque B, y existe una prueba matemática de que si algunos B '! = B también se finalizan bajo la misma definición, los validadores pierden una gran cantidad de dinero . Si los clientes ven esto, y también validan la cadena, y la validez más la finalidad es una condición suficiente para la precedencia en la regla de elección de la bifurcación canónica, entonces tienen la seguridad de que (i) B es parte de la cadena canónica o (ii) los validadores perdieron una gran cantidad de dinero al hacer una cadena en conflicto que también se finalizó.


 Los dos enfoques de la finalidad heredan de las dos soluciones el problema de nada en juego: la finalidad penalizando la incorrección y la finalidad penalizando la equivocación. El principal beneficio del primer enfoque es que es más amigable con los clientes ligeros y es más fácil de razonar, y los principales beneficios del segundo enfoque son que (i) es más fácil ver que los validadores honestos no serán castigados, y (ii) los factores de duelo son más favorables para los validadores honestos.

 Casper sigue la segunda opción, aunque es posible que se agregue un mecanismo en la cadena donde los validadores pueden optar voluntariamente por firmar mensajes de finalización de la primera opción, lo que permite clientes ligeros mucho más eficientes.


# Entonces, ¿cómo se relaciona esto con la teoría de tolerancia a fallas bizantina?

 La teoría tradicional de la tolerancia a fallas bizantinas plantea una seguridad y un deseo similares, excepto con algunas diferencias. En primer lugar, la teoría tradicional de la tolerancia a fallas bizantinas simplemente requiere que la seguridad se logre si 2/3 de los validadores son honestos. Este es un modelo estrictamente más fácil para trabajar; la tradicional tolerancia a fallas intenta probar "si el mecanismo M tiene una falla de seguridad, entonces al menos 1/3 de los nodos son defectuosos", mientras que nuestro modelo intenta probar "si el mecanismo M tiene un fallo de seguridad, entonces al menos 1/3 de los nodos son defectuosos, y usted sabe cuáles, incluso si estuvo fuera de línea en el momento en que ocurrió la falla ". Desde la perspectiva de la vida real, nuestro modelo es el más fácil, ya que no exigimos una prueba de que la red llegará a un consenso, solo exigimos una prueba de que no se paralice.


 Afortunadamente, podemos demostrar que el requisito de responsabilidad adicional no es particularmente difícil; de hecho, con la "armadura de protocolo" correcta, podemos convertir cualquier algoritmo bizantino tolerante a fallos parcialmente sincrónico o asíncrono tradicional en un algoritmo responsable. La prueba de esto básicamente se reduce al hecho de que las fallas se pueden categorizar exhaustivamente en unas pocas clases, y cada una de estas clases es responsable (es decir, si cometes ese tipo de falla puedes quedarte atrapado, así podemos hacer una reducción de latencia) o indistinguible de la latencia (tenga en cuenta que incluso el error de enviar mensajes demasiado pronto es indistinguible de la latencia, ya que se puede modelar acelerando los relojes de todos y asignando mensajes que no se enviaron demasiado pronto).


# ¿Qué es "subjetividad débil"?

 Es importante tener en cuenta que el mecanismo de uso de depósitos para garantizar que haya "algo en juego" conduce a un cambio en el modelo de seguridad. Supongamos que los depósitos están bloqueados durante cuatro meses y luego pueden retirarse. Supongamos que ocurre un intento de ataque del 51% que revierte 10 días de transacciones. Los bloques creados por los atacantes pueden simplemente importarse a la cadena principal como prueba de malversación (o "dunkles") y los validadores pueden ser castigados. Sin embargo, supongamos que tal ataque ocurre después de seis meses. Entonces, a pesar de que los bloques ciertamente pueden ser reimportados, en ese momento los validadores malvados podrán retirar sus depósitos en la cadena principal, y por lo tanto no pueden ser castigados.

 Para resolver este problema, presentamos un "límite de reversión": una regla que los nodos simplemente deben rechazar revertir más atrás en el tiempo que la longitud del depósito (es decir, en nuestro ejemplo, cuatro meses) y adicionalmente necesitamos nodos para iniciar sesión en al menos una vez cada longitud de depósito para tener una vista segura de la cadena. Tenga en cuenta que esta regla es diferente de cualquier otra regla de consenso en el protocolo, ya que significa que los nodos pueden llegar a conclusiones diferentes dependiendo de cuándo vieron ciertos mensajes. El tiempo que un nodo vio un mensaje dado puede ser diferente entre diferentes nodos; por lo tanto, consideramos que esta regla es "subjetiva" (alternativamente, alguien bien versado en la teoría de tolerancia a fallas Bizantina puede verla como una especie de suposición de sincronía).

 Sin embargo, la "subjetividad" aquí es muy débil: para que un nodo llegue a la cadena "incorrecta", debe recibir el mensaje original cuatro meses más tarde de lo que de otro modo tendría. Esto solo es posible en dos casos:

1. Cuando un nodo se conecta a la blockchain por primera vez.
2. Si un nodo ha estado fuera de línea por más de cuatro meses.

 Podemos resolver (1) al responsabilizar al usuario de autenticar el último estado fuera de banda. Pueden hacer esto preguntando a sus amigos, exploradores de bloques, empresas con las que interactúan, etc., por un hash de bloque reciente en la cadena que ven como el canónico. En la práctica, dicho hash de bloques simplemente puede venir como parte del software que utilizan para verificar la cadena de bloques; un atacante que puede corromper el punto de control en el software, puede decirse, que corrompe fácilmente el software mismo, y ninguna cantidad de verificación criptoeconómica pura puede resolver ese problema. (2) agrega realmente un requisito de seguridad adicional para los nodos, aunque tenga en cuenta una vez más, la posibilidad de falsificaciones y vulnerabilidades de seguridad, y el requisito de mantenerse al día para conocerlas e instalar las actualizaciones de software necesarias, existe en la prueba de trabajo también.

 Tenga en cuenta que todo esto es un problema solo en el caso muy limitado en el que la mayoría de las partes interesadas previas de algún momento se confabulan para atacar la red y crear una cadena alternativa; la mayoría de las veces esperamos que solo haya una cadena canónica para elegir.

# ¿Podemos tratar de automatizar la autenticación social para reducir la carga de los usuarios?

 Un enfoque es convertirlo en un flujo de trabajo natural del usuario: una solicitud de pago estilo [BIP 70](https://github.com/bitcoin/bips/blob/master/bip-0070.mediawiki) podría incluir un hash de bloqueo reciente, y el software del cliente de usuario se aseguraría de que estén en la misma cadena que el proveedor antes de aprobar un pago (o si eso importa, cualquier interacción en cadena). La otra es usar el [tiempo hash universal](https://www.youtube.com/watch?v=phXohYF0xGo) de Jeff Coleman. Si se usa UHT, entonces una cadena de ataque exitosa tendría que generarse en secreto al mismo tiempo que se estaba construyendo la cadena legítima, lo que requeriría que la mayoría de los validadores se confabularan secretamente por ese tiempo.


# ¿Puede uno penalizar económicamente la censura en la prueba de participación?

 A diferencia de revertir, la censura es mucho más difícil de probar. El blockchain en sí mismo no puede distinguir directamente entre "el usuario A intentó enviar la transacción X pero fue censurado injustamente", "el usuario A intentó enviar la transacción X pero nunca ingresó porque la tarifa de transacción fue insuficiente" y "el usuario A nunca lo intentó" para enviar la transacción X en absoluto ". Sin embargo, hay una serie de técnicas que se pueden utilizar para mitigar los problemas de censura.

 El primero es la resistencia a la censura al detener el problema. En la versión más débil de este esquema, el protocolo está diseñado para ser Turing-completo de tal manera que un validador ni siquiera puede decir si una transacción dada dará lugar o no a una acción no deseada sin gastar una gran cantidad de poder de procesamiento ejecutando la transacción y, por lo tanto, se abre a ataques de denegación de servicio.
Esto es lo que evita el [soft fork de DAO](http://hackingdistributed.com/2016/07/05/eth-is-more-resilient-to-censorship/).

 En la versión más fuerte del esquema, las transacciones pueden desencadenar efectos garantizados en algún momento, en el futuro cercano a mediano plazo. Por lo tanto, un usuario podría enviar múltiples transacciones que interactúan entre sí y con la información de terceros prevista para conducir a algún evento futuro, pero los validadores no pueden decir que esto sucederá hasta que las transacciones ya estén incluidas (y finalizadas económicamente) y es demasiado tarde para detenerlos; incluso si se excluyen todas las transacciones futuras, el evento en el que los validadores desean detenerse, todavía tendrá lugar. Tenga en cuenta que en este esquema, los validadores podrían tratar de evitar todas las transacciones, o quizás todas las transacciones que no vienen empaquetadas con alguna prueba formal de que no conducen a nada no deseado, pero esto implicaría prohibir una clase muy amplia de transacciones al punto de romper esencialmente todo el sistema, lo que causaría que los validadores pierdan valor, a medida que el precio de la criptomoneda en el que se denominan sus depósitos caería. 

 El segundo, descrito por [Adam Back aquí](https://www.reddit.com/r/Bitcoin/comments/4j7pfj/adam_backs_clever_mechanism_to_prevent_miners/d34t9xa/), es exigir que las transacciones se [cifren en tiempo real](https://www.gwern.net/Self-decrypting-files). Por lo tanto, los validadores incluirán las transacciones sin conocer el contenido, y solo más tarde podrían revelarse los contenidos automáticamente, y en ese punto una vez más sería demasiado tarde para eliminar las transacciones. Sin embargo, si los validadores fueran lo suficientemente maliciosos, simplemente podrían aceptar incluir transacciones que vienen con una prueba criptográfica (por ejemplo, ZK-SNARK) de lo que es la versión descifrada; esto obligaría a los usuarios a descargar nuevo software de cliente, pero un adversario podría proporcionar convenientemente tal software de cliente para descargarlo fácilmente, y en un modelo teórico de juego los usuarios tendrían el incentivo para seguir el juego.

 Quizás lo mejor que se puede decir en un contexto de prueba de participación es que los usuarios también pueden instalar una actualización de software que incluye un hard-fork que elimina los validadores maliciosos y esto no es mucho más difícil que instalar una actualización de software para realizar sus transacciones "amigable con la censura". Por lo tanto, en general este esquema también es moderadamente efectivo, aunque a costa de ralentizar la interacción con el blockchain hacia abajo (tenga en cuenta que el esquema debe ser obligatorio para ser efectivo; de lo contrario, los validadores maliciosos podrían filtrar las transacciones cifradas mucho más fácilmente sin filtrar las transacciones no encriptadas más rápidas).

 Una tercera alternativa es incluir la detección de censura en la regla de elección de la horquilla. La idea es simple Los nodos miran la red en busca de transacciones, y si ven una transacción que tiene una tarifa suficientemente alta por un período de tiempo suficiente, entonces asignan una "calificación" menor a las cadenas de bloques que no incluyen esta transacción. Si todos los nodos siguen esta estrategia, eventualmente una cadena minoritaria se fusionaría automáticamente, lo que incluye las transacciones, y todos los nodos honestos en línea la seguirían. La principal debilidad de tal esquema es que los nodos fuera de línea seguirían la rama mayoritaria, y si la censura es temporal y se vuelven a iniciar después de que la censura termina, terminarían en una rama diferente de los nodos en línea. Por lo tanto, este esquema debería considerarse, mas como una herramienta para facilitar la coordinación automática de emergencias en un hard-fork que como algo que desempeñaría un papel activo en la elección diaria del tenedor.






# ¿Cómo funciona la selección del validador y qué es la rectificación de la participacion (“_stake grinding_”)?

 En cualquier algoritmo de prueba de participación basado en blockchain, existe la necesidad de algún mecanismo que seleccione aleatoriamente qué validador del conjunto de validadores activo actualmente puede hacer el siguiente bloque. Por ejemplo, si el conjunto de validadores activo actualmente consiste en Alicia con 40 ethers, Bob con 30 ethers, Charlie con 20 ethers y David con 10 ethers, entonces usted quiere que haya un 40% de posibilidades de que Alice sea el siguiente creador de bloques, 30% de probabilidad de que Bob lo sea, etc. (en la práctica, usted quiere seleccionar aleatoriamente no solo un validador, sino una secuencia infinita de validadores, de modo que si Alice no aparece hay alguien que puede reemplazarla después de un tiempo , pero esto no cambia el problema fundamental). En algoritmos no basados en la cadena, la aleatoriedad también suele ser necesaria por diferentes motivos.

"_Rectificación de participación_" es una clase de ataque en la que un validador realiza algún cálculo o realiza algún otro paso para intentar influir en la aleatoriedad a su favor. Por ejemplo:

1. En [Peercoin](https://bitcointalk.org/index.php?topic=131901.0), un validador podría "rectificar" a través de muchas combinaciones de parámetros y encontrar parámetros favorables que aumentarían la probabilidad de que sus monedas generen un bloque válido.

2. En una implementación ahora difunta, la aleatoriedad para el bloque N + 1 dependía de la firma del bloque N. Esto permitió a un validador producir repetidamente nuevas firmas hasta que encontraron una que les permitiera obtener el siguiente bloque, con lo que tomaron el control del sistema para siempre.

3. En NXT, la aleatoriedad para el bloque N + 1 depende del validador que crea el bloque N. Esto permite que un validador manipule la aleatoriedad simplemente omitiendo la oportunidad de crear un bloque. Esto conlleva un costo de oportunidad igual a la recompensa del bloque, pero a veces la nueva semilla aleatoria daría al validador un número de bloques superior a la media en las siguientes docenas de bloques. Vea [aquí](https://vitalik.ca/files/randomness.html) para un análisis más detallado.

 (1) y (2) son fáciles de resolver; el enfoque general es exigir a los validadores que depositen sus monedas con suficiente antelación, y que no utilicen información que pueda manipularse fácilmente, como datos fuente de la aleatoriedad. Hay varias estrategias principales para resolver problemas como (3). La primera es usar esquemas basados en [_secret sharing_](https://en.wikipedia.org/wiki/Secret_sharing) o [_deterministic threshold signatures_](https://eprint.iacr.org/2002/081.pdf) y tener validadores, que generen en colaboración el valor aleatorio. Estos esquemas son robustos contra toda manipulación, a menos que, la mayoría de los validadores estén en colusión (en algunos casos, dependiendo de la implementación, entre el 33-50% de los validadores pueden interferir en la operación, lo que lleva al protocolo a una suposición de liveness del 67%).

 El segundo es utilizar esquemas criptoeconómicos donde los validadores se comprometen con la información (es decir, publicar sha3 (x)) con mucha antelación, y luego deben publicar x en el bloque; x luego se agrega al grupo de aleatoriedad. Hay dos vectores de ataque teóricos contra esto:

1. Manipular x en tiempo de compromiso. Esto no es práctico porque el resultado de la aleatoriedad tomaría en cuenta los valores de muchos actores, y si incluso uno de ellos es honesto, el resultado será una distribución uniforme. Una distribución uniforme XORed junto con arbitrariamente muchas distribuciones arbitrariamente sesgadas todavía da una distribución uniforme.


2. Evita de forma selectiva la publicación de bloques. Sin embargo, este ataque cuesta una recompensa de bloque del costo de oportunidad, y debido a que el esquema impide que alguien vea validadores futuros, excepto el siguiente, casi nunca proporciona más de un bloque de recompensa por valor de ingresos. La única excepción es el caso en el que, si un validador se salta, el siguiente validador en la línea Y el primer hijo de ese validador será el mismo validador; Si estas situaciones son una grave preocupación, entonces podemos castigar omitir más a través de una penalización de omisión explícita.

 El tercero es usar el ["_majority beacon_" de Iddo Bentov's](https://arxiv.org/pdf/1406.5694.pdf), que genera un número aleatorio tomando la mayoría de bit de los N números aleatorios previos generados a través de otro modelo (es decir, el primer bit del resultado es 1 si la mayoría de los los primeros bits en los números fuente son 1 y de lo contrario es 0, el segundo bit del resultado es 1 si la mayoría de los segundos bits en los números fuente es 1 y de lo contrario es 0, etc.). Esto proporciona un costo de explotación de ~ C * sqrt (N) donde C es el costo de explotación de los modelos subyacentes. Por lo tanto, en general, existen muchas soluciones conocidas para la mezcla de participación; el problema es más parecido al [criptoanálisis diferencial](https://en.wikipedia.org/wiki/Differential_cryptanalysis) que al [problema de detención](https://en.wikipedia.org/wiki/Halting_problem), una molestia que la prueba de los diseñadores de participación finalmente entendió y ahora sabe cómo superar, no una falla fundamental e ineludible.

# ¿Cuál sería el equivalente a un ataque del 51% contra Casper?

 La forma más básica de "ataque del 51%" es una **reversión de finalidad** simple: los validadores que ya finalizaron el bloque A luego finalizan algún bloque competidor A ', rompiendo así la garantía de finalidad de la cadena de bloques. En este caso, ahora existen dos historias finalizadas incompatibles, que crean una división de la cadena de bloques, que los nodos completos estarían dispuestos a aceptar, por lo que corresponde a la comunidad coordinarse fuera de banda para centrarse en una de las ramas e ignorar los demás).

 Esta coordinación podría tener lugar en las redes sociales, a través de canales privados entre los proveedores de exploradores de bloques, las empresas y los intercambios, diversos formularios de discusión en línea, y similares. El principio según el cual se tomaría la decisión es "el que primero se finalizó es el real". Otra alternativa es confiar en el "consenso del mercado": ambas ramas se negociarían brevemente en bolsas durante un período de tiempo muy corto, hasta que los efectos de la red hagan que una rama sea mucho más valiosa con los demás. En este caso, el principio de "la primera cadena finalizada gana" sería un punto _Schelling_ para lo que elegiría el mercado. Es muy posible que una combinación de ambos enfoques se use en la práctica.

 Una vez que hay consenso sobre qué cadena es real, los usuarios (es decir, validadores y operadores de nodos completos y ligeros) podrían insertar manualmente el hash de bloques ganador en su software cliente a través de una opción especial en la interfaz, y sus nodos ignorarían todas las otras cadenas. No importa qué cadena gane, existe evidencia que puede utilizarse inmediatamente para destruir al menos 1/3 de los depósitos de los validadores.


 Otro tipo de ataque es la **_negación de la vida_**: en vez de tratar de revertir bloques, un grupo de > = 34% de los validadores podría simplemente negarse a finalizar más bloques. En este caso, los bloques nunca finalizarían. Casper usa una cadena híbrida / consenso de estilo BFT, por lo que la cadena de bloques aún crecerá, pero tendría un nivel de seguridad mucho más bajo. Si no se finalizan los bloques durante un largo período de tiempo (por ejemplo, 1 día), entonces hay varias opciones:




1. El protocolo puede incluir una función automática para rotar el conjunto de validadores. Los bloques en el nuevo conjunto de validadores finalizarían, pero los clientes obtendrían una indicación, de que los nuevos bloques finalizados son en cierto sentido sospechosos, ya que es muy posible que el viejo conjunto de validadores reanude su funcionamiento y, finalice algunos otros bloques. Los clientes podrían anular manualmente esta advertencia una vez que esté claro que el viejo conjunto de validadores no volverá a estar en línea. Existiría una regla de protocolo que indicara que, en tal caso, todos los validadores antiguos que no intentaron participar en el proceso de consenso tomaron una gran multa a sus depósitos.

2. Una bifurcación fuerte se usa para agregar nuevos validadores y eliminar los saldos de los atacantes.

 En el caso (2), la bifurcación se coordinaría una vez más a través del consenso social y posiblemente a través del consenso del mercado (es decir, la sucursal con el validador viejo y el nuevo establecieron brevemente ambos intercambios en intercambios). En el último caso, existe un fuerte argumento de que el mercado querría elegir la rama donde "los buenos ganan", ya que dicha cadena tiene validadores que han demostrado su buena voluntad (o al menos, su alineación con el interés de los usuarios) y por lo tanto es una cadena más útil para los desarrolladores de aplicaciones.

 Tenga en cuenta que aquí hay un espectro de estrategias de respuesta entre la coordinación social y la automatización del protocolo, y generalmente se considera deseable avanzar lo más posible hacia una resolución automatizada para minimizar el riesgo de ataques simultáneos al 51% y ataques a las capas de redes sociales.(y herramientas de consenso del mercado tales como intercambios). Uno puede imaginar una implementación de (1) donde los nodos aceptan automáticamente un cambio a un nuevo conjunto de validador si no ven un nuevo bloque comprometido por un tiempo suficientemente largo, lo que reduciría la necesidad de coordinación social pero a costa de requerir aquellos nodos que no desean confiar en la coordinación social para mantenerse constantemente en línea. En cualquier caso, se puede diseñar una solución donde los atacantes reciben un gran impacto en sus depósitos.

 Un tipo de ataque más insidioso es un ataque de censura, donde > = 34% de los validadores se niegan a finalizar bloques que contienen ciertos tipos de transacciones que no les gustan, pero de lo contrario la cadena de bloques continúa y los bloques siguen siendo finalizados. Esto podría ir desde un leve ataque de censura que solo censura interferir con algunas aplicaciones específicas (por ejemplo, censurar selectivamente transacciones en algo como Raiden o _lightning network_ es una manera bastante fácil para un grupo de robar dinero) hasta un ataque que bloquea dichas transacciones.

 Hay dos subcasos. El primero es cuando el atacante tiene un 34-67% de la apuesta. Aquí, podemos programar a los validadores para que se nieguen a finalizar o construir en bloques que subjetivamente creen que están censurando claramente las transacciones, lo que convierte este tipo de ataque en un ataque de vida más estándar. El caso más peligroso es cuando el atacante tiene más del 67% de la apuesta. Aquí, el atacante puede bloquear libremente cualquier transacción que desee bloquear y negarse a construir sobre cualquier bloque que contenga tales transacciones.

 Hay dos líneas de defensa. En primer lugar, dado que Ethereum es Turing-completo, es [naturalmente algo resistente a la censura](http://hackingdistributed.com/2016/07/05/eth-is-more-resilient-to-censorship/), ya que las transacciones de censura que tienen un cierto efecto son en cierto modo similares a la solución del problema de detención. Debido a que hay un límite de gas, no es literalmente imposible, aunque las formas "fáciles" de hacerlo abren las vulnerabilidades de ataques de denegación de servicio.



 Esta resistencia [no es perfecta](https://pdaian.com/blog/on-soft-fork-security/), y hay formas de mejorarla. El enfoque más interesante es agregar funciones en el protocolo donde las transacciones pueden programar automáticamente eventos futuros, ya que sería extremadamente difícil prever cuál sería el resultado de la ejecución de eventos programados y los eventos resultantes de esos eventos programados antes de tiempo. Los validadores podrían usar secuencias ofuscadas de eventos programados para depositar su ether y diluir al atacante por debajo del 33%.
 
 En segundo lugar, se puede introducir la noción de una "regla de elección de fork activo", donde parte del proceso para determinar si una cadena dada es válida o no es tratar de interactuar con ella y verificar que no está tratando de censurarla. La forma más efectiva de hacer esto sería que los nodos envíen repetidamente una transacción para programar el depósito de su ether y luego cancelen el depósito en el último momento. Si los nodos detectan la censura, podrían seguir adelante con el depósito, y así unirse temporalmente al grupo de validadores en masa, diluyendo al atacante por debajo del 33%. Si el grupo del validador censura sus intentos de depósito, los nodos que ejecuten esta "regla de elección de fork activa" no reconocerían la cadena como válida; esto colapsaría el ataque de censura en un ataque de negación, en cuyo punto se puede resolver a través de los mismos medios que otros ataques de negación.


# Eso suena como una gran dependencia de la coordinación social fuera del grupo; ¿Eso no es peligroso?
 
 Los ataques contra Casper son extremadamente caros; como veremos más adelante, los ataques contra Casper cuestan tanto, si no más, que el costo de comprar suficiente potencia minera en una cadena de prueba de trabajo para que el 51% permanentemente la ataque una y otra vez hasta el punto de la inutilidad. Por lo tanto, las técnicas de recuperación descritas anteriormente solo se usarán en circunstancias muy extremas; de hecho, los defensores de la prueba de trabajo también generalmente expresan la voluntad de usar la coordinación social en circunstancias similares, por ejemplo, al [cambiar el algoritmo de prueba de trabajo](https://news.bitcoin.com/bitcoin-developers-changing-proof-work-algorithm/). Por lo tanto, ni siquiera está claro que la necesidad de coordinación social en la prueba de participación sea mayor de lo que es en la prueba del trabajo.

 En realidad, esperamos que la cantidad de coordinación social requerida sea cercana a cero, ya que los atacantes se darán cuenta de que no les conviene gastar grandes cantidades de dinero para simplemente desconectar una cadena de bloques durante uno o dos días.

 
# ¿No significa MC => MR que todos los algoritmos de consenso con un nivel de seguridad dado son igualmente eficientes (o en otras palabras, igualmente derrochadores)?

 Este es un argumento que muchos han planteado, tal vez mejor explicado por [Paul Sztorc en este artículo](http://www.truthcoin.info/blog/pow-cheapest/). Básicamente, si crea una forma para que las personas ganen $ 100, entonces la gente estará dispuesta a gastar hasta $ 99.9 (incluido el costo de su propio trabajo) para obtenerla; el costo marginal se acerca al ingreso marginal. Por lo tanto, la teoría dice que cualquier algoritmo con una recompensa de bloque dada será igualmente "inútil" en términos de la cantidad de actividad socialmente improductiva que se lleva a cabo para tratar de obtener la recompensa.


Hay tres defectos con esto:




1. No es suficiente decir simplemente que el costo marginal se acerca al ingreso marginal; uno también debe plantear un mecanismo plausible por el cual alguien pueda realmente gastar ese costo. Por ejemplo, si mañana anuncio que a partir de entonces todos los días daré $ 100 a una lista de diez personas seleccionada aleatoriamente (usando el / dev / urandom de mi computadora portátil como aleatoriedad), entonces simplemente no hay forma de que alguien pueda envíar $ 99 para tratar de llegar a esa aleatoriedad. O no están en la lista de los diez, en cuyo caso no tienen ninguna posibilidad, sin importar lo que hagan, o están en la lista de los diez, en cuyo caso no tienen ninguna forma razonable de manipular mi aleatoriedad para que así estamos atrapados en obtener el valor esperado de $ 10 por día.

2. MC => MR NO implica que el costo total se aproxime a los ingresos totales. Por ejemplo, supongamos que hay un algoritmo que selecciona de manera pseudoaleatoria 1000 validadores de un conjunto muy grande (cada validador obtiene una recompensa de $ 1), usted tiene el 10% de la apuesta, por lo que en promedio obtiene 100 y con un costo de $ 1 puede forzar la aleatoriedad para restablecer (y puede repetir esto una cantidad ilimitada de veces). Debido al [teorema del límite central](https://en.wikipedia.org/wiki/Central_limit_theorem), la desviación estándar de su recompensa es de $ 10 y, en base a [otros resultados](https://math.stackexchange.com/questions/89030/expectation-of-the-maximum-of-gaussian-random-variables) conocidos en matemáticas, el máximo esperado de N muestras aleatorias está ligeramente por debajo de M + S * sqrt (2 * log (N)) donde M es la media y S es la desviación estándar. Por lo tanto, la recompensa por hacer ensayos adicionales (es decir, aumentar N) cae bruscamente, por ej. con 0 nuevos intentos, su recompensa esperada es de $ 100, con un nuevo juicio es de $ 105.5, con dos es de $ 108.5, con tres es de $ 110.3, con cuatro es de $ 111.6, con cinco es de $ 112.6 y con seis es de $ 113.5. Por lo tanto, después de cinco nuevos intentos, deja de valer la pena. Como resultado, un atacante motivado económicamente con un diez por ciento de participación gastará ineficazmente $ 5 para obtener un ingreso adicional de $ 13, aunque el ingreso total es de $ 113. Si los mecanismos explotables solo exponen pequeñas oportunidades, la pérdida económica será pequeña; decididamente NO es el caso de que una sola gota de explotabilidad haga que todo el flujo de residuos económicos a nivel PoW vuelva a precipitarse. Este punto también será muy relevante en nuestra discusión a continuación sobre los costos de bloqueo de capital.

3. La prueba de participación puede asegurarse con recompensas totales mucho más bajas que la prueba de trabajo.


# ¿Qué pasa con los costos de bloqueo de capital?

 Bloquear X ether en un depósito no es gratis; implica un sacrificio de opcionalidad para el titular del ether. En este momento, si tengo 1000 ether, puedo hacer lo que quiera con él; si lo encierro en un depósito, está atascado allí durante meses, y no tengo, por ejemplo, la utilidad del seguro para pagar los gastos imprevistos inesperados. También pierdo algo de libertad para cambiar mis asignaciones de tokens lejos del ether dentro de ese marco de tiempo; Podría simular la venta de ether mediante el cortocircuito de una cantidad equivalente al depósito en un intercambio, pero esto en sí mismo conlleva costos que incluyen los cargos por intercambio y el pago de intereses. Algunos podrían argumentar: ¿no es esta ineficiencia de bloqueo de capital una forma muy indirecta de lograr exactamente el mismo nivel de ineficiencia económica que existe en la prueba de trabajo? La respuesta es no, por las dos razones (2) y (3) anteriores.

 Comencemos con (3) primero. Considere un modelo donde la prueba de los depósitos de la apuesta es a plazo infinito, los ASIC duran para siempre, la tecnología ASIC es fija (es decir, no existe la ley de Moore) y los costos de electricidad son cero. Digamos que la tasa de interés de equilibrio es del 5% por año. En una prueba de cadena de trabajo, puedo tomar $ 1000, convertirlo en un minero, y el minero me pagará $ 50 en recompensas por año para siempre. En una prueba de blockchain de participación, compraría $ 1000 de monedas, las depositaría (es decir, las perdería para siempre) y obtendría $ 50 en recompensas por año para siempre. Hasta ahora, la situación parece completamente simétrica (técnicamente, incluso aquí, en la prueba del caso de estaca, mi destrucción de monedas no es totalmente destructiva socialmente ya que hace que las monedas de los demás valgan más, pero podemos dejar eso de lado por el momento). El costo de un ataque del 51% de "Maginot-line" (es decir, la compra de más hardware que el resto de la red) aumenta en $ 1000 en ambos casos.

Ahora, realicemos los siguientes cambios en nuestro modelo a su vez:

1. La ley de Moore existe, los ASIC se deprecian en un 50% cada 2.772 años (eso es un 25% compuesto por año, escogido para hacer los números más simples). Si quiero mantener el mismo comportamiento de "pagar una vez, obtener dinero para siempre", puedo hacerlo: pondría $ 1000 en un fondo, donde $ 167 irían a un ASIC y los $ 833 restantes se destinarían a inversiones con 5% de interés; los dividendos de $ 41.67 por año serían suficientes para seguir renovando el hardware de ASIC (suponiendo que el desarrollo tecnológico sea completamente continuo, una vez más para simplificar las matemáticas). Las recompensas bajarían a $ 8.33 por año; por lo tanto, el 83.3% de los mineros abandonará hasta que el sistema vuelva a estar en equilibrio conmigo ganando $ 50 por año, por lo que el costo de la línea Maginot de un ataque a PoW con las mismas recompensas disminuye por un factor de 6.

2. La electricidad más el mantenimiento representa 1/3 de los costos de extracción. Estimamos el 1/3 de las estadísticas mineras recientes: uno de los nuevos data centers de Bitfury consume [0.06 joules por gigahash](https://www.coindesk.com/bitfury-details-100-million-georgia-data-center/), o 60 J / TH o 0.000017 kWh / TH, y si suponemos que toda la red Bitcoin tiene eficiencias similares obtenemos 27.9 kWh por segundo dado [1.67 millones de TH / s de potencia total Bitcoin](https://bitcoincharts.com/). La electricidad en China cuesta [$ 0,11 por kWh](https://www.statista.com/statistics/477995/global-prices-of-electricity-by-select-country/), por lo que es de aproximadamente $ 3 por segundo, o $ 260,000 por día. Las recompensas en bloque de Bitcoin más las tarifas son de $ 600 por BTC * 13 BTC por bloque * 144 bloques por día = $ 1.12 millones por día. Por lo tanto, la electricidad en sí misma representaría el 23% de los costos, y podemos realizar un mantenimiento de la estimación de respaldo del sobre al 10% para proporcionar un costo limpio de 1/3 en curso, 2/3 de costos fijos divididos. Esto significa que de su fondo de $ 1000, solo $ 111 irían al ASIC, $ 55 se destinarían a pagar los costos continuos, y $ 833 se destinarían a inversiones en hardware; por lo tanto, el costo de ataque de la línea Maginot es 9 veces menor que en nuestra configuración original.

3. Los depósitos son temporales, no permanentes. Claro, si voluntariamente sigo jugando para siempre, entonces esto no cambia nada. Sin embargo, recupero parte de la opción que tenía antes; Podría dejar de fumar en un tiempo medio (por ejemplo, 4 meses) en cualquier momento. Esto significa que estaría dispuesto a poner más de $ 1000 de ether por la ganancia de $ 50 por año; quizás en equilibrio sería algo así como $ 3000. Por lo tanto, el costo del ataque de línea Maginot en PoS aumenta por un factor de tres, y así en PoS neto da 27 veces más seguridad que PoW por el mismo costo.

 Lo anterior incluye una gran cantidad de modelado simplificado, sin embargo, sirve para mostrar cómo múltiples factores se acumulan fuertemente a favor de PoS de tal manera que PoS obtiene más por su dinero en términos de seguridad. El meta-argumento de por qué este argumento [quizás multifactorial sospechoso se inclina](https://www.lesswrong.com/posts/YgbJq4WrZWXe5GvFY/multiple-factor-explanations-should-not-appear-one-sided) tan fuertemente a favor de PoS es simple: en PoW, estamos trabajando directamente con las leyes de la física. En PoS, podemos diseñar el protocolo de tal manera que tenga las propiedades precisas que queremos; en resumen, podemos optimizar las leyes de la física a nuestro favor. La "trampa secreta" que nos brinda (3) es el cambio en el modelo de seguridad, específicamente la introducción de la subjetividad débil.

 Ahora, podemos hablar sobre la distinción marginal / total. En el caso de los costos de bloqueo de capital, esto es muy importante. Por ejemplo, considere un caso en el que tenga $ 100,000 de éter. Probablemente pretendas mantener una gran parte de ella durante mucho tiempo; por lo tanto, bloquear hasta $ 50,000 del ether debería ser casi gratis. Cerrar $ 80,000 sería un poco más inconveniente, pero $ 20,000 de espacio para respirar todavía le da un gran espacio para maniobrar. Bloquear $ 90,000 es más problemático, $ 99,000 es muy problemático, y encerrar todos los $ 100,000 es absurdo, ya que significa que ni siquiera le quedará un solo bit de ether para pagar las tarifas de transacción básicas. Por lo tanto, sus costos marginales aumentan rápidamente. Podemos mostrar la diferencia entre este estado de cosas y el estado de las cosas en la prueba de trabajo de la siguiente manera:


![](https://camo.githubusercontent.com/c1ec1cca2a20db66b7b57c295328f33b6b7c7bd1/68747470733a2f2f626c6f672e657468657265756d2e6f72672f77702d636f6e74656e742f75706c6f6164732f323031342f30372f6c69717569646974792e706e67)


Por lo tanto, el costo total de la prueba de participación es potencialmente mucho menor que el costo marginal de depositar 1 ETH más en el sistema multiplicado por la cantidad de ether actualmente depositado.

 Tenga en cuenta que este componente del argumento lamentablemente no se traduce completamente en la reducción del "nivel seguro de emisión". Nos ayuda porque muestra que podemos obtener pruebas sustanciales de la participación en la participación incluso si mantenemos la emisión muy baja; sin embargo, también significa que una gran parte de las ganancias simplemente será asumida por los validadores como un excedente económico.


# ¿Los intercambios en prueba de participación plantearán un riesgo de centralización similar para los grupos en prueba de trabajo?

 Desde una perspectiva de centralización, tanto en [Bitcoin](https://blockchain.info/pools) como en [Ethereum](https://etherscan.io/stat/miner?range=7&blocktype=blocks), se necesitan aproximadamente tres grupos para coordinar un ataque del 51% (4 en Bitcoin, 3 en Ethereum en el momento de escribir este documento). En PoS, si asumimos una participación del 30% que incluye todos los intercambios, entonces [tres intercambios](https://etherscan.io/accounts) serían suficientes para hacer un ataque del 51%; si la participación sube al 40%, el número requerido aumenta a ocho. Sin embargo, los intercambios no podrán participar con todo su ether; la razón es que necesitan acomodar retiros.

 Además, se desaconseja la agrupación en PoS porque tiene un requisito de confianza mucho más alto: una prueba del grupo de apuestas puede pretender ser pirateado, destruir los depósitos de los participantes y reclamar una recompensa por ello. Por otro lado, la capacidad de ganar intereses en las monedas sin que uno mismo ejecute un nodo, incluso si se requiere confianza, es algo que muchos pueden encontrar atractivo; en general, el equilibrio de centralización es una pregunta empírica para la cual la respuesta no está clara hasta que el sistema se está ejecutando realmente por un período sustancial de tiempo. Con la fragmentación, esperamos que los incentivos de agrupación se reduzcan aún más, ya que (i) existe aún menos preocupación por la varianza, y (ii) en un modelo fragmentado, la carga de verificación de transacción es proporcional a la cantidad de capital que uno ingresa, y por eso no hay ahorros de infraestructura directos de la puesta en común.

 Un último punto es que la centralización es menos dañina en la prueba de participación que en la prueba de trabajo, ya que hay formas mucho más económicas de recuperarse de los exitosos ataques del 51%; uno no necesita cambiar a un nuevo algoritmo de minería.


# ¿Hay formas económicas para desalentar la centralización?

 Una estrategia sugerida por Vlad Zamfir es destruir parcialmente los depósitos de validadores que se recortan, estableciendo que el porcentaje destruido sea proporcional al porcentaje de otros validadores que se han recortado recientemente. Esto garantiza que los validadores pierdan todos sus depósitos en caso de un ataque real, pero solo una pequeña parte de sus depósitos en el caso de un error puntual. Esto hace que las estrategias de segmentación de baja seguridad sean posibles, y también incentiva específicamente a los validadores a tener sus errores como no, correlacionados (o idealmente, anti-correlacionados) con otros validadores como sea posible; esto implica no estar en el grupo más grande, colocar el nodo en el proveedor de servidor privado virtual más grande e incluso usar implementaciones de software secundario, todo lo cual aumenta la descentralización.


# ¿Se puede usar la prueba de participación en cadenas privadas / de consorcio?

 En general, sí; cualquier prueba de algoritmo de prueba de participación se puede utilizar como un algoritmo de consenso en la configuración de la cadena privada / consorcio. El único cambio es que la forma en que se selecciona el conjunto de validadores sería diferente: comenzaría como un conjunto de usuarios confiables en los que todo el mundo está de acuerdo, y luego le correspondería al grupo de validadores votar para agregar nuevos validadores.