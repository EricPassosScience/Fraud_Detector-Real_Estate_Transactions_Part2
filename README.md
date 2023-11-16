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

