# Muestreo

**Uno de los objetivos principales de la estadı́stica es extraer conclusiones e información sobre una determinada población.**

Recordemos que por `población` se denomina al conjunto completo de elementos, con alguna caracterı́stica común, objeto de nuestro estudio (personas, objetos, experimentos, etc.). Evidentemente, la forma más directa de cumplir dicho objetivo serı́a estudiar todos y cada uno de los elementos de la población. Sin embargo, en numerosas ocasiones esto no es posible ya que, por ejemplo, el tamaño de la población puede ser demasiado grande e incluso infinito, o porque estudiar los elementos supone la destrucción de estos o, simplemente, porque el coste económico es prohibitivo. En estos casos, es necesario trabajar con un subconjunto de elementos de la población, es decir una muestra. Al proceso de obtener muestras se le denomina `muestreo`.

> La `inferencia estadı́stica` se ocupa de estudiar los métodos necesarios para extraer, o inferir, conclusiones válidas e información sobre una población a partir del estudio experimental de una muestra de dicha población.

Los métodos utilizados en la inferencia estadı́stica dependen de la información previa que se tenga de la población a estudiar. Cuando se conoce la forma de la distribución de probabilidad que sigue la variable aleatoria a estudiar en la población, el problema consiste en determinar los diferentes parámetros de dicha distribución (ej. media y varianza para la distribución normal). Para ello se utilizan los `métodos paramétricos`, consistentes en procedimientos óptimos para encontrar dichos parámetros. Cuando la distribución de la población es desconocida, el problema principal es encontrar la forma y caracterı́sticas de la distribución, lo cual se hace mediante los llamados `métodos no paramétricos`.

## Conceptos básicos

Para poder estudiar correctamente una población mediante la inferencia estadı́stica es fundamental que la muestra esté bien escogida. La clave de un proceso de muestreo es que la muestra sea representativa de la población. Una forma de conseguir esto es haciendo que todos los elementos de la población tengan la misma probabilidad de ser elegidos para la muestra. Diremos en este caso que tenemos un `muestreo aleatorio`. Para realizar estos muestreos aleatorios se utilizan a menudo tablas de números aleatorios.

Para poder conocer la población objeto de nuestro estudio es necesario calcular los parámetros que definen su distribución de probabilidad, por ejemplo, la media µ y la desviación tı́pica σ para una distribución normal, o la probabilidad de éxito p para una distribución binomial. Estas cantidades que definen la distribución de la población son los `parámetros poblacionales`.
El problema se concreta entonces en calcular, o estimar, los parámetros poblacionales. Para ello se toma una muestra aleatoria de la población.

Para poder estimar los parámetros poblacionales se usan las medidas de las variables aleatorias X<sub>i</sub>
que definen la muestra.

### Media muestral

Si tenemos una muestra aleatoria de tamaño *n* representada por las variables aleatorias X<sub>i</sub>, i = 1, 2, . . . , n, se define la media muestral, como

$$
X = \frac{X_{1} + X_{2} + . . . + X_{n}}{n}
$$


**Distribución muestral de la media**

Al ser una combinación lineal de variables aleatorias, la media muestral es asimismo una nueva variable aleatoria y tendrá asociada una distribución de probabilidad. Es decir, consideremos una población de la que se toman diferentes muestras de tamaño *n*, calculando para cada muestra la media *x*. Si tomamos **k** muestras distintas, obtendremos *k* valores, en general diferentes, de medias muestrales x<sub>1</sub> , x<sub>2</sub> , . . . , x<sub>*k*</sub> . Si hacemos que *k* tienda a infinito, los valores x<sub>>i</sub> tendrán una distribución llamada distribución muestral de la media.

## Varianza muestral

**Distribución muestral de la varianza**

Al igual que la media muestral, la varianza muestral es una variable aleatoria. Es decir, los valores que toma dependen de la muestra en particular que se tenga. Tiene por tanto una distribución de probabilidad asociada, llamada distribución muestral de la varianza. Para la media muestral vimos que la media, o esperanza matemática, de su distribución coincidı́a con la media poblacional. Para la varianza muestral sucede lo mismo, el valor esperado de la varianza muestral es la varianza poblacional.