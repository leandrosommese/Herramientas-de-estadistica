# VARIABLES ALEATORIAS

Con el fin de estudiar estadı́sticamente un cierto experimento aleatorio es imprescindible realizar una descripción numérica de los resultados de dicho experimento. Para ello se define una variable, llamada aleatoria, asignando a cada resultado del experimento aleatorio un cierto valor numérico.

## Descripción de las variables aleatorias

***Concepto de variable aleatoria***

Dado un experimento aleatorio, definimos una variable aleatoria como una función definida sobre el espacio muestral que asigna un número real a cada uno de los puntos, o resultados posibles, de dicho espacio muestral. Una variable aleatoria que toma un número finito o infinito, pero numerable de valores se denomina variable aleatoria discreta. Por el contrario, cuando la variable puede tomar un número infinito no numerable de valores (o todos los valores posibles de un intervalo) se la denomina variable aleatoria continua.

### Variables aleatorias

**Variable aleatoria discreta**

Para describir completamente la variable aleatoria hay que indicar las probabilidades de que tome cada uno de sus valores posibles. De esta forma a cada valor de la variable aleatoria se le asigna como `probabilidad` la probabilidad de que ocurra el subconjunto del espacio muestral asociado con ese valor particular. Para esto se define una función f (x) que indica la probabilidad de cada valor x de la variable aleatoria. Esta es la función de probabilidad, también llamada distribución de probabilidad, de la variable aleatoria discreta X

> f(x) ≡ P(X = x)

En particular, para un valor x<sub>i</sub> de la variable aleatoria: f (x<sub>i</sub>) = P (X = x<sub>i</sub>).

Asimismo, gráficamente se suele representar usando un diagrama de barras donde en abscisas se sitúan los diferentes valores de X y en ordenadas las probabilidades correspondientes.

Otra forma de caracterizar la distribución de una variable aleatoria es mediante la función de distribución F (x), o función de probabilidad acumulativa, definida para cada x como la probabilidad de que la variable aleatoria X tome un valor menor o igual que x.

**Variable aleatoria continua**

Veamos ahora el caso de las variables aleatorias continuas, es decir, aquellas que pueden tomar cualquier valor en un intervalo (a, b), o incluso (−∞, ∞). En este caso, la probabilidad de que la variable X tome un valor determinado dentro de ese intervalo es cero, ya que existen infinitos valores posibles en cualquier intervalo, por pequeño que sea, alrededor del valor en cuestión. Por tanto no se puede definir una función de probabilidad igual que se hacı́a para las variables discretas, dando la probabilidad de cada valor de la variable. Lo que se si puede especificar es la probabilidad de que la variable esté en un cierto intervalo. Para ello se define una función f(x) llamada función de densidad, o distribución de probabilidad.

## Medidas caracterı́sticas de una variable aleatoria

De la misma forma en que se definı́an medidas caracterı́sticas de las distribuciones de frecuencias, se pueden definir también medidas caracterı́sticas para la distribución de una variable aleatoria, dividiéndose éstas en medidas de centralización y medidas de dispersión. Por convenio, estas medidas teóricas se representan por letras griegas para ası́ diferenciarlas de las medidas de las distribuciones de frecuencias, calculadas a partir de una muestra de datos, que se denotaban por letras latinas.

**Media o esperanza matemática**

La principal medida de centralización de la distribución de una variable aleatoria es la media.
La media se obtiene multiplicando cada valor de X por su probabilidad y sumando estos productos
para todos los posibles valores de X (el sumatorio se puede extender desde 1 hasta n ó ∞). Evidentemente, el
significado de la media es que da un valor tı́pico o promedio de la variable aleatoria.

**Varianza y desviación tı́pica**

La media por sı́ sola no proporciona una adecuada descripción de la distribución de la variable aleatoria. Además de conocer en qué valor se centra esa distribución es importante determinar la dispersión o variación de los valores de la variable aleatoria en torno a la media.

## Variable aleatoria bidimensional

A veces es interesante estudiar simultáneamente varios aspectos de un experimento aleatorio. Para ello se define la variable aleatoria bidimensional como una función que asigna un par de números reales a cada uno de los puntos, o resultados posibles, del espacio muestral. En general, denotaremos una variable aleatoria bidimensional de un experimento aleatorio por (X, Y), de forma que tomará valores (x, y) en un espacio bidimensional real. Diremos que una variable bidimensional es discreta cuando las dos variables que la componen lo sean. Asimismo será continua cuando tanto X como Y sean continuas.

***Distribución de probabilidad conjunta y marginal***

Sea una variable aleatoria bidimensional (X, Y )  discreta asociada a un experimento aleatorio. Se define la función de probabilidad conjunta como la función
f (x, y) = P (X = x, Y = y).

***Distribución condicionada e independencia estadística***

Dada una variable aleatoria bidimensional se define la distribución condicionada de X cuando la variable Y toma un valor fijo (Y = y) a la distribución unidimensional de la variable X para los elementos de la población que tienen como valor de Y el valor fijado.

> P (X = x|Y = y) = P (X = x, Y = y)/P (Y = y) = f (x, y)/f 2 (y)

Un concepto fundamental en el estudio de las variables aleatorias bidimensionales es el de `independencia estadı́stica`. Diremos que dos variables X e Y son independientes cuando el conocimiento de los valores que toma una de ellas no aporta información sobre los valores que puede tomar la otra. En este caso es claro que las distribuciones condicionadas son iguales a las distribuciones marginales

>f (x|y) = f 1 (x);f (y|x) = f 2 (y)