---
title: The background of the AccessMonitor' Score
---

<span lang="en">Note: this article was taken from <em lang="es">Libro Blanco de eXaminator</em>, written by Carlos Benavidez, author of Web validators such as Hera, eXaminator and AccessMonitor. The book was published on June 1, 2012.</span>

Everything that is said below about the eXaminator's index applies to AccessMonitor.

(...)

## Fórmulas de cálculo

Un inconveniente de las métricas que miden la tasa de fallo es que nos ponen en aprietos al tratar de resolver las pruebas cuando es difícil o imposible definir el número total de pruebas realizadas. En el test sobre las alternativas textuales no hay problemas porque el total de pruebas es el número de imágenes que hay en una página y el número de errores son las imágenes sin el atributo alt.
Los problemas aparecen, por ejemplo, al intentar calificar los errores de validación porque disponemos del número de errores pero no existe un total de pruebas que nos permita calcular el porcentaje de errores. También tenemos una situación indefinida cuando encontramos atributos HTML obsoletos porque podríamos considerar como total de casos el número de elementos de la página o solamente el número de elementos que tienen asignado atributos mediante HTML.

Para sortear estas dificultades, eXaminator usa distintas fórmulas para resolver los resultados. Estas fórmulas definen 4 tipos de test que explico en detalle más adelante. El criterio para seleccionar el tipo de test a aplicar en cada caso es que debe permitir que la calificación se ajuste a estos juicios de valor:

- Muymal: 1
- Mal: 2 ó 3
- Regular: 4 ó 5 
- Bien: 6 ó 7
- Muy bien: 8 ó 9 
- Excelente: 10

Las calificaciones son empíricas. Están apoyadas por mi experiencia como revisor y desarrollador de herramientas de evaluación pero existe un componente subjetivo en las decisiones y también una pizca de arbitrariedad. La escala anterior sirve como guía para determinar las calificaciones pero decidir si un error merece 3 ó 5 es siempre discutible. De todos modos, aquí, la tiranía del desarrollador es tan comprensible e inevitable como la de cualquier profesor al tomar exámenes.
Número de errores
La repetición de los errores es un dato importante que se debe tener en cuenta en las calificaciones. Un único error se puede deber a una equivocación o un desliz pero varios errores del mismo tipo indican claramente un concepto equivocado o un gran descuido en el desarrollo. Además, las barreras de accesibilidad aumentan en proporción directa al número de errores.
Cuando existe un total de pruebas bien definido, como es el caso de las imágenes y el atributo alt, se utiliza la tasa de fallo para que la calificación resulte menor cuanto mayor es la cantidad de errores detectados. Para los errores de validación, por ejemplo, se aplica otra fórmula que también disminuye la nota a medida que aumenta el número de errores pero en este caso la escala de disminución es fija, no relacionada a ningún porcentaje.
A veces se deben considerar varios factores para elegir la fórmula más adecuada. Por ejemplo, en el caso de los elementos HTML obsoletos sería posible calcular el porcentaje tomando como total el número de atributos HTML usados. El problema es que, a mayor cantidad de atributos HTML -posiblemente en detrimento del uso de propiedades de CSS- mejoraría la calificación. En un caso así, parece más apropiado considerar el número de errores sin apelar a los porcentajes y usar una escala predeterminada para disminuir la nota de acuerdo a la cantidad de errores.
Hay pruebas que sólo pueden tener resultados binarios. Por ejemplo, el error que consiste en usar el elemento meta para refrescar la página sólo puede tener dos resultados: bien o mal. También existen casos en los que la contabilización de los errores, aunque posible, no es significativa. Por ejemplo, el uso del elemento marquee es un error grave porque provoca movimientos en el contenido, es un elemento anticuado, no estándar y -¿por qué no que decirlo?- su uso denota un concepto de diseño bastante estúpido. Por eso, poco importa que se use uno o más veces y simplemente merece ser calificado siempre con la peor nota.
Ponderación de las pruebas
En el cálculo se debe tener en cuenta que no todas las pruebas tienen la misma importancia, de modo que es necesario ponderarlas para que su peso relativo refleje esas diferencias. La Ponderación (P), que puede tener valores entre 0 y 1, es el producto del grado de Confianza (C) y el Valor relativo de la prueba (V):
P=C*V
Libro blanco de eXaminator
15

 Valor
El valor de cada prueba se calcula de acuerdo al nivel del Criterio de Conformidad con que se relaciona la técnica revisada. Si la técnica está relacionada con varios criterios de conformidad, se usa el de mayor nivel (si son dos los criterios relacionados, uno de nivel A y otro de nivel doble A, se utiliza el primero).
• Nivel A: 0.9
• Nivel AA: 0.5
• Nivel AAA: 0.1
Si la técnica se relaciona con más de un Criterio de Conformidad, su valor aumenta 0.1 y disminuye 0.1 cuando es sólo una técnica sugerida y se relaciona con un único Criterio de Conformidad. (De todas las decisiones que se deben tomar al definir el sistema de medición, esta escala es, claramente, la más arbitraria.)
Confianza
Indica la seguridad que se le otorga a la prueba. Como todas las pruebas ofrecen entre una buena y una muy buena seguridad de no fallar (de otro modo serían, lógicamente, descartadas), en una escala de 0 a 1, todas merecerían un valor muy elevado, haciendo que la escala fuera poco significativa.
Para ampliar esa escala basada en un criterio válido, se toman en cuenta los pasos indicados en los procedimientos de revisión de las técnicas relacionadas. Por ejemplo, si el primer enlace de la página tiene como referencia un ancla en la propia página, la técnica G1 [19] parece satisfecha pero, observando los procedimientos de revisión manual, vemos que faltaría verificar si el enlace es siempre visible, si el texto del enlace es correcto y si efectivamente el salto es hacia el contenido principal. Por cada uno de esos pasos que no es posible verificar automáticamente se disminuye 0.1 y la confianza de esa prueba será 0.7. Este criterio no es estricto pero proporciona la estrategia necesaria para resolver con cierta coherencia la confianza de cada prueba.
Tipos de prueba
eXaminator está desarrollado en PHP y usa una matriz para guardar toda la información necesaria sobre cada una de las pruebas. Esto permite agregar, eliminar y modificar cada prueba individualmente con mucha facilidad, de modo que sería posible generar distintos modos de revisión. Voy a explicar el significado de algunas variables definidas en la matriz de datos de cada prueba porque ayudarán a entender las fórmulas que definen los resultados.
Libro blanco de eXaminator 16

 Elemento (E)
Identifica un elemento del lenguaje HTML o un conjunto de estos elementos. Por ejemplo, el elemento Controles de formulario que requieren etiquetas asociadas comprende a los input de tipos text, checkbox, radio, file y password, más los elementos textarea y select. La prueba es aplicable sólo cuando el elemento existe en la página. El elemento all es especial e indica que la prueba resulta siempre aplicable.
Situación (S)
Identifica un elemento del lenguaje HTML o un conjunto de estos elementos que cumplen determinada condición. Siempre se trata de un subconjunto de elemento, excepto cuando elemento es all. Se debe encontrar al menos 1 situación para que la prueba sea aplicable, excepto en las pruebas de tipo falso que se aplica cuando no se encontró ninguna situación en la página.
Nota (N)
Es la calificación de la prueba. En las pruebas de resultado variable, es la calificación inicial a partir de la cual se efectuarán los cálculos posteriores. En otras palabras, es la calificación que se aplica a la primera situación detectada.
Tolerancia (T)
En las pruebas de tipo decreciente indica el umbral de tolerancia a los errores, es decir, el
valor a partir del cual se comenzará a disminuir la nota inicial. Fracción (F)
En las pruebas de tipo decreciente indica la cantidad de errores que disminuyen en un punto la nota inicial. Tolerancia y Fracción son datos exclusivos para las pruebas de tipo decreciente en las cuales cada situación identifica siempre un error.
Pruebas de tipo verdadero/falso
Ambas pruebas consisten en evaluar una condición y, si esa condición se cumple, el Resultado ( R) es el producto de la Nota (N) y la Ponderación (P):
R=N*P
Ambas pruebas son idénticas en todo sentido excepto que la condición se debe evaluar como verdadera en un caso y como falsa en el otro para que la prueba resulte aplicable.
Prueba de tipo proporcional
En esta prueba, la nota inicial disminuye en proporción al cociente entre Situación (S) y Elemento (E).
                             R=N*(1-S/E)*P
Veamos como ejemplo la prueba sobre las alternativas textuales en las imágenes. Aquí, Elemento (E) son las imágenes y Situación (S) son las imágenes sin alt. La prueba es aplicable cuando existen ambos. La Nota (N) es la calificación inicial atribuida a este tipo de errores (en esta prueba la nota es 3 porque se considera que está mal sin importar cuántas imágenes sin alt se encuentren).
Libro blanco de eXaminator 17

 Pero la calificación puede aún ser menor si consideramos la extensión de los errores. Entonces, se calcula la tasa de fallo y luego el porcentaje a sustraer de la nota inicial. Si las imágenes son 8 y hay 4 sin alt, sin tomar en cuenta la ponderación, el cálculo sería:
                    R=3*(1-4/8)=3*(1-0.5)=3*0.5=1.5
La calificación inicial (3) se reduce a la mitad (1.5) porque el error está presente en el 50% de las imágenes encontradas.
Prueba de tipo decreciente
En esta prueba, la nota inicial va disminuyendo a medida que aumenta la cantidad de errores. La Tolerancia (T) indica cuántos errores se permiten antes de comenzar a restar de la nota; superado el umbral de tolerancia, cada Fracción (F) disminuye en 1 punto la nota inicial.
                            R=(N-(S-T)/F)*P
Por ejemplo, cuando existen errores de validación, la nota inicial es 5 y la tolerancia es 10. Es decir, se considera que hasta 10 errores de validación es una situación que se puede calificar como regular (la tolerancia es bastante alta por el efecto de arrastre que tienen algunos errores). Si existen más de 10 errores, la nota comienza a disminuir 1 punto por cada fracción, que en esta prueba también es de 10. Suponiendo que encontramos 40 errores, sin tener en cuenta la ponderación, sería:
                     R=5-(40-10)/10=5-30/10=5-3=2
Entonces, la calificación es 5 cuando existen entre 1 y 10 errores; con 40 errores la nota baja a 2 y así, si se encuentran más de 50 errores de validación la nota sería 1, la mínima.
Promedio
Por último, la puntuación de una página resulta de la división de la sumatoria de las pruebas realizadas por la sumatoria de las respectivas ponderaciones. Esto se puede expresar en una fórmula muy sencilla para quienes saben interpretar las notaciones matemáticas e incomprensible para quienes no. Como pertenezco al último grupo, me abstengo de incluir dicha fórmula que, en realidad, poco agregaría a mis enredadas explicaciones. Prefiero mostrar un ejemplo práctico para explicar el efecto que tienen las ponderaciones sobre la puntuación final.
Tomemos como ejemplo sólo 2 pruebas: la prueba A con ponderación 1 y la prueba B con ponderación 0.1, de modo que la sumatoria de las ponderaciones es 1.1. Si la nota en ambas pruebas es 9, la puntuación final será, lógicamente, 9. El resultado ponderado de la prueba A es 9 (9*1) y el de la prueba B es 0.9 (9*0.1). La sumatoria de las pruebas ponderadas es 9.9 (9+0.9), que al dividirla por la sumatoria de las ponderaciones (1.1) nos da 9 (9.9/1.1).
Ahora bien, supongamos que la prueba A tiene un 2 como nota, de modo que la nota ponderada sería 2 (2*1) y la sumatoria de las pruebas sería 2.9 (2+0.9). En este caso, la puntuación sería 2.6 (2.9/1.1) luego de redonderar el resultado. Pero si es la prueba B la que tiene 2, la sumatoría de las pruebas nos daría 9.2 (9+0.2) y la puntuación sería 8.4 (9.2/1.1).
Libro blanco de eXaminator 18

Con este ejemplo muy sencillo se puede apreciar la importancia de la ponderación de las pruebas. Si promediáramos simplemente las notas 9 y 2, obtendríamos 5.5 pero así estaríamos poniendo en un mismo nivel a las dos pruebas cuando las ponderaciones indican que la prueba A tiene un valor muy alto y es de máxima confianza, mientras que la prueba B es mucho menos significativa. Entonces es lógico que la prueba B tenga un peso mucho menor en la puntuación final. Observen que al promediar A, que tiene una nota de 2, con B, que tiene 9, la puntuación final es 2.6, es decir, el promedio queda muy cerca de 2, que es la nota de la prueba con mayor ponderación.
En términos prácticos, las ponderaciones permiten establecer un necesario balance entre las pruebas e impiden que el resultado de una página dependa de una sola prueba, tal vez inexacta. Para obtener una mala puntuación el balance de las pruebas debe ser claramente desfavorable. Es necesario que se detecten varios errores y, por el contrario, que no se detecten buenas prácticas en la cantidad y con la ponderación suficiente como para compensar esos errores. No se puede achacar a la casualidad una puntuación muy baja así como una puntuación muy alta difícilmente se consiga por un golpe de suerte.
A veces es necesario establecer objetivos de trabajo en un sitio y las puntuaciones resultan un parámetro muy tentador. Tiene su atractivo poder decir, por ejemplo, "en tal fecha, todas las páginas evaluadas deberán alcanzar una puntuación mínima de 7" porque así la meta a alcanzar quedaría claramente definida. El problema es que no se puede usar la puntuación de un modo escolar, considerando que alcanza con 4 ó 6 para aprobar la materia.
Para establecer objetivos precisos es más útil considerar la ausencia de aquellos errores que se pueden verificar con mayor exactitud. El modo estricto de eXaminator es apropiado para estos casos porque, si bien calcula la puntuación de la página, pone mayor énfasis en la importancia de las pruebas y en el informe las muestra agrupadas por niveles de acuerdo a las WCAG 2.0. De este modo es sencillo poner como meta, por ejemplo, eliminar todos los errores de prioridad A y doble A antes de planificar las revisiones manuales de las páginas.
