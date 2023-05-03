# Distribuciones continuas de probabilidad

## Distribución continua uniforme

Se dice que una variable aleatoria X sigue una `distribución continua uniforme` cuando su función de densidad f(x) toma valores constantes en el intervalo [a, b]. Es decir, `f (x) = K en ese intervalo` y, por tanto, la probabilidad de que tome un valor en cualquier incremento (de la misma anchura) dentro de ese intervalo es la misma.


<img src=./distribucion_continua_uniforme.png
     width="50%" 
     height=auto />
Función de densidad f(x)
<img src=./distribucion_continua_uniforme2.png
     width="50%" 
     height=auto />
Función de distribución F(x)

## Distribución normal

La distribución continua de probabilidad más importante de toda la estadı́stica es, sin duda alguna, la distribución normal. La importancia de esta distribución se debe a que describe con gran aproximación la distribución de las variables asociadas con muchos fenómenos de la naturaleza.Además, los errores en las medidas también se aproximan con mucha exactitud a la distribución normal. Por otra parte, bajo ciertas condiciones,la distribución normal constituye una buena aproximación a otras distribuciones de probabilidad, como la binomial y la de Poisson. Frecuentemente, a la distribución normal se la denomina también distribución gaussiana.

<img src=./Normal_distribution.png
     width="50%" 
     height=auto />
Función de densidades F(x)

***Definición y propiedades***

Por definición, se dice que una variable aleatoria continua X sigue una distribución normal de media µ y desviación tı́pica σ si su función de densidad es

> f (x) = N (µ, σ) = e <sup>-(x−µ)<sup>2</sup>/2σ<sup>2</sup></sup>/(σ √2π) ; −∞ < x < ∞

La distribución de probabilidad normal tiene forma de campana (llamada campana de Gauss, o curva normal), simétrica (por depender de x a través del término (x−µ)<sup>2</sup> ), centrada en µ y con anchura proporcional a σ (como es lógico esperar del significado de la desviación tı́pica). Evidentemente, el máximo de la función de densidad ocurre para x = µ y, por tanto, media, mediana y moda coinciden en ese punto. La curva tiende asintóticamente a cero al alejarse del valor medio.

***Relación con otras distribuciones***

Existe un teorema básico en estadı́stica que explica porqué la distribución normal es tan frecuente. El
teorema es el siguiente:

`Teorema del lı́mite central`: 

> Si X<sub>1</sub> , X<sub>2</sub>, . . . , X<sub>n</sub> son variables aleatorias independientes con medias µ<sub>i</sub>, desviaciones tı́picas σ<sub>i</sub>, y distribuciones de probabilidad cualesquiera (y no necesariamente la misma), y definimos la variable suma Y = X<sub>1</sub> + X<sub>2</sub> + . . . + X<sub>n</sub>, entonces, cuando n crece, la variable Z tiende hacia una distribución normal estándar N (0, 1).

La aplicación de la distribución normal es entonces muy útil para calcular probabilidades de la distribución
binomial o de Poisson cuando n (ó λ) es grande. Hay que tener en cuenta que al pasar de una variable discreta
X a una continua X' habrá que utilizar la, llamada, corrección de continuidad, que consiste en calcular las
probabilidades como

> P (x<sub>1</sub> ≤ X ≤ x<sub>2</sub> ) = P (x<sub>1</sub> − 0.5 < X' < x<sub>2</sub> + 0.5)

## Distribución χ<sup>2</sup> de Pearson

Sean X<sub>1</sub> , X<sub>2</sub>, . . . , X<sub>n</sub> *n* variables aleatorias normales con media 0 y varianza 1 independientes entre sı́, entonces la variable

χ<sup>2</sup><sub>n</sub> = X<sup>2</sup><sub>1</sub> + X<sup>2</sup><sub>2</sub> + . . . + X<sup>2</sup><sub>n</sub>

recibe el nombre de χ<sup>2</sup> (chi–cuadrado) con *n* grados de libertad.

<img src=./Chi-square_distribution.png
     width="50%" 
     height=auto />
Función de densidades F(x)

Gráficamente, su función de densidad es muy asimétrica (para n = 1 corresponde a elevar al cuadrado una curva normal tipificada), pero se va haciendo más simétrica a medida que n aumenta. En particular, para n ≥ 30 se distribuye como una distribución normal.


## Distribución t de Student

Sean X<sub>1</sub> , X<sub>2</sub>, . . . , X<sub>n</sub> y X, *n + 1* variables aleatorias normales con media 0 y desviación tı́pica σ independientes entre sı́, entonces la variable

$$
t_{n} =  \frac{X}{√\frac{1}{n} \sum_{i=1}^{n}X^2_{i}}
$$

recibe el nombre de t de Student con n grados de libertad.

<img src=./Student_densite.JPG
     width="50%" 
     height=auto />
Función de densidades F(x)

Su forma será campaniforme, siendo más achatada para valores bajos de n. Cuando *n* aumenta f (t) se va haciendo cada vez más apuntada, tendiendo a la curva normal tipificada (N (0, 1)) cuando n → ∞. En general, la curva normal es una buena aproximación de la distribución t cuando n ≥ 30.

Es evidente que, al ser f (t) simétrica respecto a t = 0, la media ha de ser nula. Respecto a la varianza, nótese que es mayor que 1 y depende del número de grados de libertad. Sólo al hacerse n muy grande, σ tiende a 1, y, por tanto, a la distribución normal estándar.

## Distribución F de Fisher

Sean χ<sup>2</sup><sub>n</sub><sub><sub>1</sub></sub> y χ<sup>2</sup><sub>n</sub><sub><sub>2</sub></sub> dos variables χ<sup>2</sup> de Pearson con n<sub>1</sub> y n<sub>2</sub> grados de libertad e independientes entre sı́.
Entonces, la variable aleatoria definida como

$$
F_{n_{1},n_{2}} =  \frac{\frac{X^2_{n_{1}}}{n_{1}}}{\frac{X^2_{n_{2}}}{n_{2}}}
$$

recibe el nombre de F de Fisher con n<sub>1</sub> y n <sub>2</sub> grados de libertad.

<img src=./Fisher_distribution.png
     width="50%" 
     height=auto />
Función de densidades F(x)

La representación gráfica de la distribución F será de la forma representada en la figura y dependerá, lógicamente, de n 1 y n 2 .

La distribución F de Fisher es muy utilizada en el análisis de varianza y, en particular, es usada para comparar las varianzas de dos poblaciones normales.