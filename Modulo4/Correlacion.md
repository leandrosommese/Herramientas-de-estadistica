# Test de correlación

Un test de correlación es una técnica estadística que se utiliza para medir el grado de relación entre dos variables cuantitativas. El test de correlación permite determinar si existe una asociación entre dos variables y la fuerza de esta asociación.

Existen diferentes tipos de test de correlación, y el tipo de test que se utiliza depende de la naturaleza de las variables y del tipo de relación que se espera encontrar. Algunos de los test de correlación más comunes son:

1. Coeficiente de correlación de Pearson: Es un test paramétrico que se utiliza para medir la relación lineal entre dos variables continuas. El coeficiente de correlación de Pearson toma valores entre -1 y 1, donde -1 indica una correlación negativa perfecta, 0 indica ausencia de correlación, y 1 indica una correlación positiva perfecta.

2. Coeficiente de correlación de Spearman: Es un test no paramétrico que se utiliza para medir la relación monótona entre dos variables continuas o discretas ordinales. El coeficiente de correlación de Spearman toma valores entre -1 y 1, donde -1 indica una correlación negativa perfecta, 0 indica ausencia de correlación, y 1 indica una correlación positiva perfecta.

3. Coeficiente de correlación de Kendall: Es un test no paramétrico que se utiliza para medir la relación de concordancia entre dos variables discretas ordinales. El coeficiente de correlación de Kendall toma valores entre -1 y 1, donde -1 indica una correlación negativa perfecta, 0 indica ausencia de correlación, y 1 indica una correlación positiva perfecta.

Es importante tener en cuenta que un coeficiente de correlación no implica causalidad entre las variables. Es decir, la correlación no indica necesariamente que una variable cause la otra, sino simplemente que hay una relación entre ellas. Por lo tanto, es importante tener en cuenta otros factores y realizar análisis más detallados para determinar la naturaleza de la relación entre las variables.


## Comparación datos discretos 

La comparación de tablas de contingencia implica la evaluación de si hay diferencias significativas entre las distribuciones de frecuencia observadas en dos o más grupos. Aquí te presento algunos métodos comunes para comparar tablas de contingencia:

    Prueba de chi-cuadrado (χ²): Es una prueba estadística que se utiliza para evaluar la asociación entre dos variables categóricas. La prueba de chi-cuadrado compara la frecuencia observada en cada celda de la tabla de contingencia con la frecuencia esperada si no hubiera ninguna relación entre las variables. Si la diferencia entre la frecuencia observada y la esperada es grande, se concluye que hay una relación significativa entre las variables.

    Prueba exacta de Fisher: Es una prueba estadística que se utiliza cuando los datos son escasos o las celdas de la tabla de contingencia tienen un tamaño pequeño. La prueba de Fisher calcula la probabilidad exacta de observar una tabla de contingencia con los datos observados, asumiendo que no hay asociación entre las variables. Si la probabilidad es muy baja, se concluye que hay una asociación significativa entre las variables.

    Prueba de proporciones de dos muestras: Es una prueba estadística que se utiliza para comparar la proporción de una variable categórica en dos muestras independientes. La prueba compara la proporción observada en cada grupo con la proporción esperada si no hubiera diferencia entre los grupos. Si la diferencia entre las proporciones es grande, se concluye que hay una diferencia significativa entre los grupos.

    Análisis de correspondencia: Es una técnica de análisis multivariado que se utiliza para explorar la asociación entre dos o más variables categóricas. El análisis de correspondencia visualiza la relación entre las variables en un espacio de baja dimensión y se puede utilizar para detectar patrones y relaciones complejas entre las variables.


[contingencia con scipy](https://docs.scipy.org/doc/scipy/reference/stats.contingency.html)