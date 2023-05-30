# Modelos estadísticos de evolución molecular

Existen dos tipos principales de métodos de reconstrucción filogenética:

    a) los que utilizan distancias genéticas, siendo los más conocidos el método neighbor-joining y el de mínima evolución;
    b) los basados en caracteres, como los métodos de máxima parsimonia, de máxima verosimilitud y de inferencia Bayesiana. Dentro de los métodos basados en caracteres, MV e IB (a diferencia de MP) son métodos probabilísticos que tratan la inferencia filogenética como un problema estadístico, y utilizan modelos explícitos de evolución molecular para el cálculo de probabilidades.

## Modelos de evolución

La sustitución entre nucleótidos, aminoácidos o codones se modela como un evento aleatorio y los cambios entre los estados se describen mediante una `cadena de Markov` tiempo-continua. La propiedad más importante de las cadenas de Markov es que no tienen memoria, es decir, que la probabilidad de cambio entre nucleótidos sólo depende del nucleótido actual y no de aquéllos nucleótidos que pudo haber en esa posición con anterioridad.

Los modelos tienen dos tipos parámetros principales: las probabilidades de cambio entre estados y las frecuencias de estos nucleótidos en nuestro alineamiento. En los modelos de nucleótidos y codones, los valores de estos parámetros se estiman a partir de los datos observados.

    El modelo de evolución de nucleótidos más sencillo es el conocido como Jukes-Cantor (JC) y asume que cualquier cambio entre nucleótidos tiene la misma probabilidad de ocurrir y que las frecuencias de los cuatro nucleótidos son iguales.

En el caso de los modelos de reemplazamiento de aminoácidos, en cambio, los parámetros generalmente
no se estiman a partir de los datos, sino que vienen previamente fijados.

Además de modelar las probabilidades de cambio entre nucleótidos (o aminoácidos) y sus frecuencias
relativas, con frecuencia se utilizan parámetros adicionales para tener en cuenta el hecho de que distintas partes del alineamiento pueden `evolucionar a tasas distintas`.

Ante la gran variedad de modelos posibles, la pregunta obvia es `¿qué modelo debemos elegir?`

    Cuantos más factores queramos tener en cuenta, más parámetros tendremos que incluir en el modelo. En principio, uno podría estar tentado de elegir siempre el modelo más complejo, pero entonces nos topamos con un problema estadístico. A mayor número de parámetros, mayor será la varianza con la que se estimen, es decir, las estimas serán menos fiables. Por el contrario, un modelo sencillo (con pocos parámetros) permitirá hacer estimas muy estables, pero se ajustará peor a los datos. Por tanto, es necesario encontrar un balance entre el ajuste a nuestros datos y la complejidad del modelo.

### Contraste de modelos

Existen distintos criterios que pueden utilizarse para elegir el modelo que mejor se ajusta a nuestros datos, al mismo tiempo que sopesamos su complejidad. T

Tradicionalmente se han venido utilizando los contrastes basados en la `razón de verosimilitudes` (likelihood ratio test, LRT). Los LRT comparan modelos por pares y requieren que las hipótesis estén anidadas, es decir, que el modelo nulo (aquél con menos parámetros) sea un caso particular del modelo alternativo. Estos contrastes son muy útiles para testar ciertos tipos de hipótesis filogenéticas.

El AIC (criterio de información de Akaike) es una medida de la cantidad de la información que perdemos al explicar los datos observados utilizando un modelo en particular. Por tanto, el modelo que mejor se ajusta a los datos observados es aquél que tiene un valor de AIC menor. A diferencia del LRT, el AIC permite comparar más de dos modelos simultáneamente
y no requiere que estén anidados. 

El AIC se calcula como:

    AIC = 2k − 2 ln L
    
    L es el valor de verosimilitud
    k el número de parámetros del modelo.

En la actualidad es frecuente utilizar conjuntos de datos que combinan varios genes, con el objeto de tener grupos de datos independientes y más caracteres totales con los que reconstruir la historia evolutiva. En estos casos, en lugar de utilizar un único modelo para el conjunto de datos global, se suelen utilizar modelos evolutivos independientes para cada gen, de modo que se puedan tener en cuenta sus distintas propiedades evolutivas.

### **Métodos probabilísticos basados en caracteres**

A diferencia de los métodos basados en distancias, los basados en caracteres tienen en cuenta los cambios que ocurren en cada posición del alineamiento, y hacen por tanto un uso más eficiente de la información.

Su funcionamiento se fundamenta en criterios de optimización: en un primer paso se `generan árboles` utilizando ciertos algoritmos heurísticos, y en un segundo paso estos árboles se `evalúan` utilizando una función objetiva que nos permita elegir el mejor árbol entre todos los generados en el paso anterior.

Las `búsquedas heurísticas` utilizan algoritmos que partiendo de un árbol (por ejemplo, aleatorio o reconstruido con NJ) realizan pequeñas reorganizaciones locales para encontrar árboles más probables. Durante las búsquedas heurísticas, las distintas reorganizaciones se aceptan o rechazan con ayuda del criterio de optimización, y la búsqueda continúa hasta que no se encuentren más mejoras significativas.

### Máxima verosimilitud

    El principio de MV se define como la probabilidad de que un modelo de evolución dado y una historia evolutiva hipotética (el árbol) hayan dado lugar a los datos observados (alineamiento de secuencias).
    
El árbol de MV es aquél que tiene la mayor probabilidad de haber generado los datos observados, y por tanto se prefiere como hipótesis filogenética. El método de MV es eficiente y consistente. Esto significa que `la varianza de las estimas es menor` que en otros métodos (están menos afectadas por el error de muestreo) y que las estimas convergen al valor correcto del parámetro conforme aumentamos el número de caracteres.

Los modelos evolutivos generalmente asumen que el proceso de evolución molecular es reversible. Esto permite que el valor de verosimilitud de un árbol sea independiente de la posición de la raíz. Además, hemos asumido que las posiciones evolucionan de forma independiente en el alineamiento. Esta asunción nos permite calcular la verosimilitud de forma independiente para cada posición del alineamiento y combinar posteriormente estas verosimilitudes en un valor final.

El cálculo de verosimilitud para cada posición se realiza teniendo en cuenta todos los posibles escenarios que han podido dar lugar a los datos observados (para esa posición). Esto implica sumar las
probabilidades de cada combinación única de estados ancestrales (reconstrucciones hipotéticas en los
nodos internos) y longitudes de rama.

Una vez que hemos calculado la verosimilitud para cada posición en el alineamiento, la verosimilitud total del árbol se calcula como la suma de los logaritmos de las verosimilitudes para cada sitio.

    Es importante recordar que una búsqueda heurística nunca nos asegurará que hemos encontrado el mejor árbol, pues durante el proceso de optimización puede quedar atrapada en un máximo local, lo cual nos generará un árbol subóptimo.

### Métodos Bayesianos

La estadística Bayesiana, a diferencia de la estadística clásica, considera los parámetros de un modelo como variables aleatorias con una distribución estadística y no como constantes desconocidas. Puesto que desconocemos los valores de los parámetros del modelo, desde un punto de vista Bayesiano resulta más razonable especificar a priori unas distribuciones para describir los valores que éstos puede tomar.

    La inferencia Bayesiana (IB) de la filogenia se basa en el cálculo de la probabilidad posterior de un árbol, esto es, la probabilidad de que dicho árbol sea correcto dados unos datos y un modelo.

El gráfico se representan en una única dimensión un conjunto de árboles posibles (eje x) en función de su probabilidad posterior (eje y). En la curva, cada punto representa una combinación única de topología y longitudes de rama.

La IB trata de determinar el área bajo esta curva, que corresponde a la probabilidad posterior de cada árbol concreto.

<img src=./inferenciabayesiana.png
     width="100%" 
     height=auto />

El cálculo de la probabilidad posterior implica evaluar todos los posibles árboles y, para cada árbol, investigar todas las posibles combinaciones de longitudes de ramas y parámetros del modelo evolutivo.

En el caso de la IB, utilizamos algoritmos MCMC (o Markov Chain Monte Carlo) para obtener una aproximación de la distribución de la probabilidad posterior. Los MCMC son algoritmos de simulación estocástica que evitan el cálculo directo de las probabilidades posteriores y permiten obtener una muestra de la distribución posterior.

Como ocurre con las búsquedas heurísticas de MV, las cadenas MCMC pueden quedar atrapadas en máximos locales.

La forma más sencilla es observar sus diferencias medias, que en MrBayes conocemos como “average standard deviation of split frequencies”. Una diferencia entre las desviaciones estándar medias menor de 0.01 suele indicarnos que los dos análisis de IB han convergido.

Los métodos de IB tienen una conexión muy fuerte con la MV, ya que la hipótesis preferida es aquélla con la mayor probabilidad posterior, y éste es un valor que se calcula en función de la verosimilitud. Puesto que la IB se basa directamente en la verosimilitud, comparte sus propiedades de eficiencia y
consistencia.

Existen `diferencias` importantes entre MV e IB: la MV trata de encontrar un único árbol (el mejor, el de mayor verosimilitud), mientras que la IB integra un gran número de árboles de probabilidad posterior elevada (con sus topologías y longitudes de rama).

La ventaja de integrar varios árboles es que consideramos la incertidumbre existente en las estimaciones.

El conjunto de árboles obtenidos a partir de las pseudoréplicas se resume en un árbol final que conocemos como árbol de consenso por mayoría. Este árbol incluirá un número (típicamente expresado en %) para cada uno de los nodos del árbol en función del número de veces que se encuentre esta relación en particular en el conjunto de los 1000 árboles de bootstrap. Generalmente se considera que un valor igual o mayor al 70 % es un soporte elevado para las relaciones de parentesco implicadas.

Además de estimar la fiabilidad de los árboles filogenéticos, es posible utilizar test estadísticos para saber si nuestros datos, además de favorecer una hipótesis filogenética concreta (nuestro árbol reconstruido) podrían soportar o rechazar otras hipótesis filogenéticas, como las propuestas en estudios previos.

Este tipo de análisis son muy interesantes, y pueden aplicarse, entre otras cosas, para conocer si nuestros datos de secuencia apoyan o rechazan determinadas relaciones de parentesco derivadas del análisis de datos morfológicos o de otro tipo.

Una posibilidad para comparar hipótesis no anidadas mediante LRT es utilizar el bootstrapping paramétrico, que nos permite determinar la distribución nula del estadístico D. El bootstrapping no paramétrico, también conocido como simulación de Monte Carlo, consiste en generar réplicas de los datos y estimar mediante un método como la MV un conjunto de árboles (con su topología, longitudes de rama y parámetros del modelo) que formarán la distribución nula. En este caso, el LRT será significativo si las diferencia entre las verosimilitudes de los árboles de la distribución nula y la hipótesis alternativa superan el 5 % de los casos

Los test de topologías alternativas más populares son tres. El contraste de Kishino-Hasegawa (KH) permite comparar la diferencia de verosimilitudes entre dos árboles seleccionados a priori. Este contraste estadístico sólo es válido si los árboles se escogen previamente y no se derivan del mismo alineamiento que se utilizará para compararlos posteriormente. El contraste de Shimodaira-Hasegawa (SH) permite comparar un conjunto de árboles seleccionados a posteriori, lo cual nos permite incluir el árbol de MV obtenido a partir de nuestro alineamiento. Sin embargo, el contraste SH es muy conservador y sus resultados son muy dependientes del número de árboles considerados. Existe un tercer tipo de contraste conocido como test aproximadamente no sesgado (AU, del inglés approximately unbiased test) que está menos sesgado que los contrastes desarrollados con anterioridad (KH, SH), y por ello es el más utilizado actualmente. El contraste AU utiliza una aproximación de bootstrap multiescala para controlar el error de tipo I (rechazar inapropiadamente la hipótesis nula).

El procedimiento de bootstrap multiescala consiste en generar pseudoréplicas de bootstrap como en el caso de bootstrapping no paramétrico, pero en este caso las pseudoréplicas son de longitud variable, de modo que ciertas pseudoréplicas serán de longitud mayor y otras de longitud menor que el alineamiento original. Tras contar el número de veces que una hipótesis filogenética es apoyada por las pseudoréplicas, se obtienen valores de bootstrap para cada conjunto de pseudoréplicas de una determinada longitud. El valor de probabilidad del test AU se calcula a partir de las diferencias en estos valores de bootstrap en función
de las longitudes de las pseudoréplicas.


    El bootstrap es un procedimiento estadístico que sirve para aproximar características de la distribución en el muestreo de un estadístico. Para ello se emplea (normalmente) simulación, generando un gran número de muestras mediante algún tipo de remuestreo de la muestra original.

    Su ventaja principal es que no requiere hipótesis sobre el mecanismo generador de los datos (aunque los resultados asintóticos requieren de hipótesis generales). Por lo que son de especial utilidad cuando no se dispone la distribución exacta del estadístico y no es posible o adecuado emplear la distribución asintótica.

**Fuente: Bioinformática con Ñ., (2014) Coordinators and editors: Sebastián, A. and Pascual-García, A., ISBN:978-84-617-1976-X. (https://zenodo.org/communities/bioinfconn/)**