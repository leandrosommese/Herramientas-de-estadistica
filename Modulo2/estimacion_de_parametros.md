# Medidas caracterı́sticas de una distribución

Las medidas resumen permiten comparar nuestra muestra con otras y dar una idea rápida de cómo se distribuyen los datos.

**Todas estas medidas solo pueden definirse para variables cuantitativas.** 

## Medidas de centralización

***Media aritmética***

La media se calcula sencillamente sumando los  distintos valores de x y dividiendo por el número
de datos.

La media representa entonces una especie de centro de gravedad, o centro geométrico, del conjunto de medidas. Una caracterı́stica  importante de la media como medida de tendencia central es que es muy poco robusta, es decir depende mucho de valores particulares de los datos. Si por ejemplo, en una muestra introducimos un nuevo dato con un valor mucho mayor que el resto, la media aumenta  apreciablemente. La media aritmética es por tanto muy dependiente de observaciones extremas.

```python
media = df.mean(axis=0, skipna=True, numeric_only=False)
```

***Mediana***

Se define ésta como una medida central tal que, con los datos ordenados de menor a mayor, el 50 % de los datos son inferiores a su valor y el 50 % de los datos tienen valores superiores.

la mayor ventaja de la media es que se utiliza toda la información de la distribución de frecuencias, en contraste con la mediana, que solo utiliza el orden en que se distribuyen los valores. Podrı́a considerarse, desde este punto de vista, que la media aritmética es una medida más fiable del valor central de los datos. Sin embargo, la media es muy poco robusta, en el sentido de que es muy sensible a valores extremos de la variable. La mediana, por otro lado, es una medida robusta, siendo muy insensible a valores que se desvı́en mucho.

```python
mediana = df.median(axis=0, skipna=True, numeric_only=False)
```

***Moda***

Se define la moda Mo de una muestra como aquel valor de la variable que tiene una frecuencia máxima. En otras palabras, es el valor que más se repite. Hay que indicar que puede suceder que la moda no sea única, es decir que aparezcan varios máximos en la distribución de frecuencias. En ese caso diremos que tenemos una distribución bimodal, trimodal, etc. Evidentemente, en el caso de una variable discreta que no toma valores repetidos, la moda no tiene sentido. Cuando sı́ existen valores repetidos su cálculo es directo ya que puede leerse directamente de la tabla de distribución de frecuencias. En el caso de variables continuas agrupadas en intervalos de clase existirá un intervalo en el que la frecuencia sea máxima, llamado intervalo modal.

```python
moda = mode(axis=0, numeric_only=False, dropna=True)
```
***Percentiles***

Los cuartiles como los tres valores que divididen la muestra en cuatro partes iguales. De la misma manera se definen los percentiles, como aquellos valores Pk (con k = 1, 2, . . . , 99) que dividen la muestra en k partes iguales. Es decir, el percentil Pk deja por debajo de él al k por ciento de la muestra ordenada.

```python
percentil_k = df.quantile(q=k, axis=0, numeric_only=False, interpolation='linear', method='single')
```

## Medidas de dispersión

Para analizar la representatividad de las medidas de centralización se definen las llamadas medidas de dispersión. Estas nos indicarán la variabilidad de los datos en torno a su valor promedio, es decir si se encuentran muy o poco esparcidos en torno a su centro.

***Recorridos***

Una evaluación rápida de la dispersión de los datos se puede realizar calculando el recorrido (también llamado rango), o diferencia entre el valor máximo y mı́nimo que toma la variable estadı́stica. Con el fin de eliminar la excesiva influencia de los valores extremos en el recorrido, se define el recorrido intercuartı́lico como la diferencia entre el trecer y primer cuartil.

RI = Q 3/4 − Q 1/4

```python
rango = df.max()-df.min()
RI = df.quantile(0.75)-df.quantile(0.25)
```

***Desviación media***

Otra manera de estimar la dispersión de los valores de la muestra es comparar cada uno de estos con el valor de una medida de centralización. Una de las medidas de dispersión más usada es la desviación media. Se define ésta como la media aritmética de las diferencias absolutas entre los valores de la variable y la media aritmética de la muestra. Suponiendo que en una muestra de tamaño N los k distintos valores xi de la variable tengan frecuencias absolutas ni.

***Varianza y desviación típica***

Sin lugar a dudas la medida más usada para estimar la dispersión de los datos es la desviación tı́pica. Esta es especialmente aconsejable cuando se usa la media aritmética como medida de tendencia central. Al igual que la desviación media, está basada en un valor promedio de las desviaciones respecto a la media. En este caso, en vez de tomar valores absolutos de las desviaciones, para evitar ası́ que se compensen desviaciones positivas y negativas, se usan los cuadrados de las desviaciones. Esto hace además que los datos con desviaciones grandes influyan mucho en el resultado final.

```python
desviacion_tipica = df.std(axis=None, skipna=True, ddof=1, numeric_only=False)
varianza = df.var(axis=None, skipna=True, ddof=1, numeric_only=False)
```

En cuanto a las propiedades de la desviación tı́pica, es fácil ver que ésta será siempre positiva y sólo tendrá un valor nulo cuando todas las observaciones coincidan con el valor de la media.

La desviación tı́pica no es una medida robusta de la dispersión. El hecho de que se calcule evaluando los cuadrados de las desviaciones hace que sea muy sensible a observaciones extremas, bastante más que la desviación media (dado que aparece un cuadrado). En definitiva, la desviación tı́pica no es una buena medida de dispersión cuando se tiene algún dato muy alejado de la media. El rango intercuartı́lico nos darı́a en ese caso una idea más aproximada de cuál es la dispersión de los datos. El que la desviación tı́pica sea la medida de dispersión más común se debe a su ı́ntima conexión con la distribución normal.

***Coeficientes de variación***

Un problema que plantean las medidas de dispersión vistas es que vienen expresadas en las unidades en que se ha medido la variable. Es decir, son medidas absolutas y con el único dato de su valor no es posible decir si tenemos una dispersión importante o no. Para solucionar esto, se definen unas medidas de dispersión relativas, independientes de la unidades usadas. Estas dispersiones relativas van a permitir además comparar la dispersión entre diferentes muestras (con unidades diferentes). Entre estas medidas hay que destacar el coeficiente de variación de Pearson, definido como el cociente entre la desviación tı́pica y la media aritmética.

CV = s/|x|

```python
CV = df.std()/df.mean()
```

Asimismo, se pueden definir otras medidas de dispersión relativas, como el coeficiente de variación media. Éste es similar al coeficiente de variación de Pearson, pero empleando una desviación media en vez de la media aritmética. Se tienen entonces dos coeficientes de variación media dependiendo de que se calcule respecto a la desviación media respecto a la media aritmética o respecto a la mediana.

***Asimetría y curtosis***

La descripción estadı́stica de una muestra de datos no concluye con el cálculo de su tendencia central y su dispersión. Para dar una descripción completa es necesario estudiar también el grado de simetrı́a de los datos respecto a su medida central y la concentración de los datos alrededor de dicho valor.

**Coeficientes de asimetrı́a:** Se dice que una distribución de medidas es simétrica cuando valores de la variable equidistantes, a uno y otro lado, del valor central tienen la misma frecuencia. Es decir, en este caso tendremos simetrı́a en el histograma alrededor de una vertical trazada por el punto central. En el caso de una distribución perfectamente simétrica los valores de media aritmética, mediana y moda coinciden.

<img src="./asimetria.png" 
     width="100%" 
     height=auto />


En el caso de no tener simetrı́a, diremos que tenemos asimetrı́a a la derecha (o positiva) o a la izquierda (o negativa) dependiendo de que el histograma muestre una cola de medidas hacia valores altos o bajos de la variable respectivamente.

Con el fin de cuantificar el grado de asimetrı́a de una distribución se pueden definir los coeficientes de asimetrı́a.

**Coeficiente de asimetrı́a de Fisher.** Se define como el cociente entre el momento de orden 3 respecto a la media y el cubo de la desviación tı́pica.

Tendrá valores positivos para una asimetrı́a positiva (a la derecha) y negativos cuando la asimetrı́a sea en el otro sentido. Hay que indicar que la división por el cubo de la desviación tı́pica se hace para que el coeficiente sea adimensional y, por lo tanto, comparable entre diferentes muestras.

```python
skewness = df.skew(axis=0, skipna=True, numeric_only=False)
```

**Coeficiente de curtosis**: Además de la simetrı́a, otra caracterı́stica importante de la forma en que se distribuyen los datos de la
muestra es cómo es el agrupamiento en torno al valor central.

<img src="./curtosis.png" 
     width="100%" 
     height=auto />

Los datos se pueden distribuir de forma que tengamos un gran apuntamiento alrededor del valor central, en cuyo caso diremos que  tenemos una distribución leptocúrtica, o en el extremo contrario, el histograma puede ser muy aplanado, lo que corresponde a una distribución platicúrtica. En el caso intermedio, diremos que la distribución es mesocúrtica y el agrupamiento corresponderá al de una distribución llamada normal, o en forma de campana de Gauss.

Esta caracterı́stica del agrupamiento de los datos se denomina curtosis y para cuantificarla se define el coeficiente de curtosis como el cociente entre el momento de cuarto orden respecto a la media y la cuarta potencia de la desviación tı́pica

Este coeficiente adimensional alcanza valores mayores cuanto más puntiaguda es la distribución, teniendo un valor de 0 para la distribución mesocúrtica (o normal), mayor que 0 para la leptocúrtica y menor para la platicúrtica.

```python
kurtosis = df.kurt(axis=0, skipna=True, numeric_only=False)
```

## Variables estadísticas bidimensionales

***Distribuciones marginales***

A veces es interesante analizar cuántas veces se repite un cierto valor de x sin tener en cuenta para nada a los posibles valores de y, o viceversa. A la distribución formada por los diferentes valores de x y sus frecuencias marginales se le llama distribución marginal de x.

***Distribuciones condicionadas***

En muchos casos es importante conocer la distribución de la variable x para todos aquellos pares de datos en los que la variable y toma un cierto valor y j . Es decir, al contrario que en las distribuciones marginales en que no importaba el valor que tomase la otra variable, ahora se fija dicho valor. A este conjunto de valores que puede tomar la variable x para un cierto valor y j de y se le llama distribución de x condicionada a y = y j y las correspondientes frecuencias absolutas se representan por 

> n(x i |y = y j )

cuyo significado es, entonces, el número de veces que aparece repetido el valor xi entre aquellos pares de datos que tienen y = yj.
De la misma forma se puede definir la distribución de y condicionada a x = xi .