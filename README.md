# Detección de Fraude en Transacciones Inmobiliarias (Spanish)

<p align="center">
  <img width="600" height="500" src="https://github.com/EricPassosScience/Hypothesis_Test_Business/assets/97414922/f75f4b05-c745-4a51-9b87-e7fefc8bbe0d">
</p>

******************************
## Consideraciones Iniciales
Este trabajo se desarrolló en dos partes. La primera parte es el desarrollo del DQR mientras que la segunda se centra en técnicas de detección de fraude en los mismos datos. Estás en la parte 2.
La parte más importante del trabajo está en el archivo python, donde se ubica todo el código y los resultados de los análisis. Sólo verás en este README una contextualización y algunos conceptos importantes. El código en el archivo Python y este README son complementarios, es decir, comprender uno depende de comprender el otro.

******************************* 
## EL IMPACTO DEL FRAUDE EN LA ECONOMÍA
- Una organización típica pierde anualmente el 5% de sus ingresos debido al fraude (Association of Certified Fraud Examiners)
- El coste total del fraude de seguros en EE.UU. se estima en más de 40.000 millones de dólares al año (FBI)
- El fraude le cuesta al Reino Unido £73 mil millones al año (National Fraud Authority)
- Las compañías de tarjetas de crédito “pierden aproximadamente siete centavos por cada cien dólares de transacciones debido al fraude” (Andrew Schrage, Money Crashers Personal Finance).
- El tamaño promedio de la economía informal en los países en desarrollo es del 41%, en los países en transición del 38% y en los países de la OCDE del 18% (Schneider)
********************************
## PRINCIPALES TIPOS DE FRAUDE
Tarjetas de crédito, fraude de seguros, corrupción, fraude electoral, fraude de garantía de productos, fraude de planes de salud, fraude de transacciones en línea y de clics, fraude inmobiliario y financiero, lavado de dinero, evasión fiscal, piratería, etc.
*********************************
## CONCEPTO E INFORMACIÓN SOBRE FRAUDE
Con el tiempo, los estafadores se han vuelto cada vez más profesionales a la hora de encontrar formas de eludir sistemas o procesos y esto ha hecho que la prevención del fraude sea cada vez más compleja y desafiante. Pero antes de hablar de prevención y detección del fraude, debemos definir qué es el fraude.

Según el diccionario, la definición de fraude está relacionada con la distorsión intencional de la verdad o de un hecho, que generalmente busca obtener un beneficio ilícito.

Por un lado, la definición capta la esencia del fraude y cubre las diferentes formas de fraude. Por otro lado, no describe con mucha precisión la naturaleza y las características del fraude y, como tal, no proporciona mucha orientación para discutir los requisitos de un sistema de detección de fraude.

El fraude no es un fenómeno reciente y exclusivo de la sociedad moderna. El fraude es un delito raro, imperceptiblemente oculto, que evoluciona en el tiempo y, a menudo, cuidadosamente organizado, que aparece en muchos tipos de formas. Nota: pronto traeré aquí a GitHub un caso de uso de un modelo para eventos raros, también conocido como “modelo inflado cero”, ¡estad atentos!

Independientemente de la definición o aplicación exacta, sólo una minoría de la población se ve realmente involucrada en casos típicamente relacionados con el fraude, de los cuales, además, sólo un número limitado será realmente detectado como fraude. Esto dificulta aún más la detección de fraude, ya que los casos fraudulentos están cubiertos por otros no fraudulentos, lo que dificulta la construcción de un sistema de detección, ya que hay pocos ejemplos de actividades fraudulentas disponibles y, como usted sabe, para entrenar modelos de Machine Learning, necesitamos muchos ejemplos de hechos históricos.

Otra característica de los defraudadores es la capacidad de permanecer en el anonimato para pasar desapercibidos y de permanecer cubiertos por personas que no son defraudadores. Esto efectivamente hace que el fraude se oculte imperceptiblemente, ya que los estafadores pueden ocultarse planificando cómo cometer el fraude con precisión. Definitivamente tu comportamiento no es impulsivo ni no planificado, ya que si lo fuera, la detección sería mucho más fácil.
********************************
## EL TRIÁNGULO DEL FRAUDE
El fraude no lo cometen sólo los delincuentes. El llamado triángulo del fraude proporciona una explicación más detallada de los motivos que llevan a cometer fraude laboral.

<p align="center">
  <img width="500" height="400" src="https://github.com/EricPassosScience/Fraud_Detector-Real_Estate_Transactions_Part2/assets/97414922/3846abf2-44ce-4ccc-a689-d0d7893c5ee6">
</p>

El triángulo del fraude se origina a partir de una hipótesis formulada por Donald R. Cressey en su libro de 1953 titulado “El dinero de otras personas: un estudio sobre la psicología social de la malversación de fondos”. donald dijo:

“Las personas confiables se convierten en violadores de la confianza cuando se conciben con un problema financiero que no se puede compartir. Son conscientes de que este problema puede resolverse en secreto vulnerando una posición de confianza financiera y son capaces de aplicar su propia conducta ante esta situación, verbalizaciones que les permitan ajustar su concepción de sí mismos como personas confiables, con sus concepciones de sí mismos con los usuarios. de los fondos o bienes encomendados”.

El lenguaje es un poco complejo, ya que se remonta a hace muchas décadas, pero simplifiquemos: lo que Donald quiso decir es que el fraude muchas veces lo comete alguien sin antecedentes penales, pero debido a una situación imprevista, si vale la pena su condición. defraudar sistemas y obtener ganancias. 

Se conocen muchos casos de directivos que defraudaron los sistemas financieros de las empresas para pagar deudas personales, con el pretexto de que devolverían el dinero lo antes posible. Esto no convierte a este tipo de fraude en legal, pero sí dificulta su detección, ya que no existen antecedentes previos de la persona que lo cometió.

Este modelo conceptual y básico del triángulo del fraude explica los factores que en conjunto causan o explican los factores que llevan a un individuo a cometer fraude ocupacional, y proporciona una visión útil del fenómeno del fraude también desde un punto de vista más amplio. El modelo tiene tres patas que juntas instituyen comportamientos fraudulentos:

La motivación es el primer paso y se refiere a la motivación principal para cometer fraude. Un individuo comete fraude porque está bajo presión debido a un problema de naturaleza financiera, social o de otra naturaleza, y no puede resolverse o aliviarse de manera autorizada.

La oportunidad es la segunda etapa del modelo y se refiere a la condición previa para que un individuo cometa fraude. Sólo se pueden cometer actividades fraudulentas cuando existe una oportunidad para que el individuo resuelva o alivie la presión o el problema experimentado de manera no autorizada pero encubierta u oculta. Por lo tanto, la mejor manera de prevenir el fraude suele ser dejar a más de una persona responsable de una actividad determinada.

La racionalización es el mecanismo psicológico que explica por qué los defraudadores no se abstienen de cometer fraude y consideran aceptable su conducta.

Si los tres elementos están presentes, las posibilidades de que se produzca fraude son altas.
*****************************************
## DETECCIÓN DE FRAUDE X PREVENCIÓN DE FRAUDE
Dos componentes que son partes esenciales de casi cualquier estrategia eficaz para combatir el fraude implican la detección y la prevención del fraude.
La detección de fraude se refiere a la capacidad de reconocer o descubrir actividades fraudulentas. La prevención del fraude se refiere a las medidas que se pueden tomar para prevenir o reducir el fraude.

La diferencia entre ambos es clara: el primero es un enfoque reactivo, mientras que el segundo es un enfoque proactivo. Ambas estrategias pueden y probablemente deberían usarse de manera complementaria para perseguir el objetivo compartido de reducir el fraude. 

Sin embargo, las acciones preventivas cambiarán las estrategias de fraude y, en consecuencia, el impacto del poder de detección. La instalación de un sistema de detección hará que los estafadores se adapten y cambien su comportamiento, por lo que el propio sistema de detección acabará socavando su propio poder de detección. Por tanto, la detección y prevención del fraude no son independientes y deben alinearse y considerarse como un todo.

**************************
## SISTEMA DE REGLAS
Depender únicamente de la tecnología para aprobar o desaprobar pedidos ya no es suficiente; también es necesario confiar en análisis humanos sofisticados. Esto se debe a que, si bien los modelos estadísticos son herramientas valiosas en la lucha contra el fraude, también requieren aportes y juicio humanos para crear una solución integral que produzca los mejores resultados. No hay duda de que las herramientas de análisis automático son componentes extremadamente importantes en los programas de reducción del fraude, pero depender únicamente de ellas puede no ser eficiente a largo plazo. La razón es que la tecnología por sí sola no es eficaz para definir o identificar todos los aspectos subjetivos que rodean una transacción fraudulenta.
****************************
## Problema
Una empresa ofrece seguros de propiedad en la ciudad de Nueva York, Estados Unidos. Con el objetivo de calcular el valor del seguro de la mejor manera posible, la empresa nos contrató como Data Scientist, para analizar y detectar fraudes en los datos de transacciones inmobiliarias de toda la ciudad. Los datos son públicos y proporcionados por el portal de datos abiertos de la ciudad de Nueva York.

La empresa necesita una puntuación para cada transacción con el fin de comprobar aquellas con mayor posibilidad de fraude. El Fraud Score debe ser lo más preciso posible y se debe generar uno para cada transacción.

Cabe señalar que no existe información previa sobre si una transacción fue fraudulenta o no.
**********************************
## Fuente de datos:
Para este proyecto (partes 1 y 2), utilizaremos datos reales disponibles públicamente. Se puede acceder a los datos en el portal de datos abiertos de la ciudad de Nueva York. Enlace -> https://data.cityofnewyork.us/Housing-Development/Property-Valuation-and-Assessment-Data/rgy2-tti8

<p align="center">
  <img width="1000" height="200" src="https://github.com/EricPassosScience/Fraud_Detector-Real_Estate_Transactions_Part2/assets/97414922/63353618-1576-4ae6-996c-3aef69518448">
</p>

En el mismo enlace podemos encontrar el diccionario de datos que será fundamental para nuestro análisis.
*****************************
## MODELADO
Existen varias técnicas para el análisis de detección de fraude. Para nuestro problema, utilizamos el enfoque de aprendizaje no supervisado, creando puntuaciones de fraude para cada transacción inmobiliaria.

Las técnicas utilizadas fueron PCA (Análisis de Componentes Principales) en escala Z, y una técnica de Deep Learning no supervisada conocida como Autoencoder. Se generaron dos puntuaciones, una para cada técnica, que se unieron al final.

La salida del PCA, los diez componentes principales, se utilizarán como datos de entrada para el Autoencoder.

En Autoencoder, aunque la precisión del modelo es baja, su tasa de error también lo es, por lo que tenemos un modelo utilizable.
*************************************
## Cálculo de la puntuación final - "Matrix Rank"
La puntuación final se calculará utilizando el “matrix rank”, que es el número de filas distintas de cero en la matriz, cuando se escribe en forma escalada por filas. De manera equivalente, corresponde al número de filas o columnas linealmente independientes de la matriz. La característica de una matriz tiene varias implicaciones con respecto a la independencia lineal y la dimensión de un espacio vectorial.

¿Y qué significa este lineal? Lineal significa que podemos multiplicar por una constante, pero sin potencias ni otras funciones. La constante puede ser cualquier número real (0, 1, cualquier número entero, fracción, negativos, etc.).

¿Y dependientes? Dependencia significa que dependen unos de otros, en otras palabras, podemos sumar algunos (después de multiplicarlos por una constante) para formar otro. Imagina que son vectores (tienen dirección y longitud). ¿Podemos combinar los otros vectores (acercándolos o alejándolos según sea necesario) para obtener el mismo resultado?

<p align="center">
  <img width="600" height="500" src="https://github.com/EricPassosScience/Fraud_Detector-Real_Estate_Transactions_Part2/assets/97414922/d8db02aa-75bb-4786-8e50-4c2074ca7c66">
</p>

Tenga en cuenta que 'a' y 'b' son linealmente independientes: no podemos usar 'a' sola para llegar a donde está 'b', o viceversa. Lo mismo ocurre con "b" y "c", o con "a" y "c". Pero 'a', 'b' y 'c' son juntos linealmente dependientes. Solo pensando en 'a' y 'b': podemos llegar a cualquier parte usando estos dos vectores:

<p align="center">
  <img width="600" height="500" src="https://github.com/EricPassosScience/Fraud_Detector-Real_Estate_Transactions_Part2/assets/97414922/a24acda9-8afb-438b-904e-aff9a14211e4">
</p>

Cuando los vectores son linealmente independientes y cubren un espacio completo, decimos que son una "base" de ese espacio. Por tanto, 'a' y 'b' son bases del plano 2D.
Nota: Espacio es un término general que cubre 1, 2, 3 o dimensiones superiores, pero a menudo lo llamamos plano espacial 2D.
Por tanto, 'a' y 'b' son tan útiles como los ejes x,y. Y lo mismo podría decirse de 2 vectores linealmente independientes cualesquiera en el plano 2D.
El par más básico de vectores linealmente independientes son (1,0) y (0,1) que forman la matriz identidad 2x2:((1 0)¦(0 1)). Básicamente forman los conocidos ejes x, y:

<p align="center">
  <img width="600" height="500" src="https://github.com/EricPassosScience/Fraud_Detector-Real_Estate_Transactions_Part2/assets/97414922/53bcdf3e-d936-4c74-894c-ba73f26ed723">
</p>

Y en 3D:

<p align="center">
  <img width="600" height="500" src="https://github.com/EricPassosScience/Fraud_Detector-Real_Estate_Transactions_Part2/assets/97414922/e2890449-2b52-49b0-9871-f470b4b11a6b">
</p>

Y en 4D:

<p align="center">
  <img width="300" height="250" src="https://github.com/EricPassosScience/Fraud_Detector-Real_Estate_Transactions_Part2/assets/97414922/0a317318-2b95-4461-8280-3066ec5c82f4">
</p>

## Referencias
- Matrix Rank -> https://www.mathsisfun.com/algebra/matrix-rank.html
- En Python, la biblioteca pandas ofrece una función que calcula la "Matriz Rank", puedes consultar la documentación -> https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.rank.html

