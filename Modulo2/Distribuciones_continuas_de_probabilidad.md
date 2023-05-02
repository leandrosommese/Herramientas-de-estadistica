# Distribuciones continuas de probabilidad

En este tema se presentan algunas de las distribuciones continuas de probabilidad más comunes y fre-
cuentemente utilizadas en Fı́sica. También resultan fundamentales a la hora de tomar decisiones en inferencia
estadı́stica y al realizar contrastes de hipótesis, como se estudiará más adelante.
8.1.
Distribución continua uniforme
Se dice que una variable aleatoria X sigue una distribución continua uniforme cuando su función de
densidad f (x) toma valores constantes en el intervalo [a, b]. Es decir, f (x) = K en ese intervalo y, por tanto,
la probabilidad de que tome un valor en cualquier incremento (de la misma anchura) dentro de ese intervalo
es la misma. Para calcular esa constante aplicamos la condición de normalización de la función de densidad
1=
.
∞
f (x) dx =
−∞
.
b
f (x) dx =
a
.
b
a
K dx = K(b − a)
Por lo tanto la función de densidad tiene la forma



 0
1
f (x) =
b−a


 0
⇒
K =
1
.
b − a
x<a
a<x<b
(8.1)
x>b
Podemos además calcular la función de distribución F (x). Cuando x esté en el intervalo [a, b]
F (x) = P (X < x) =
.
x
f (t) dt =
−∞
y, en general,
F (x) =
.
x
a



 0
x<a
x−a
b−a


 1
1
x − a
dt =
,
b − a
b − a
a<x<b
x>b
89
(8.2)90
Distribuciones continuas de probabilidad
Figura 8.1: Función de densidad, f (x), y función de distribución, F (x), para una distribución continua uniforme.
La representación gráfica de la función de densidad y de la función de distribución será como la mostrada
en la Figura 8.1.
La media, o esperanza matemática, de la distribución continua, se puede expresar como
µ =
.
∞
xf (x) dx =
−∞
.
b
x
a
? 2 @ b
dx
1
x
b 2 − a 2
(a + b)(b − a)
=
=
=
b − a
b − a 2 a
2(b − a)
2(b − a)
⇒
a + b
.
2
µ =
(8.3)
Por otra parte, la varianza puede calcularse como
σ 2 =
.
∞
−∞
(x − µ) 2 f (x) dx =
.
a
b
6
x −
a + b
2
7 2
dx
=
b − a
A
6
7 2 B b
1
x 3
a + b 2
a + b
−
x +
x .
b − a 3
2
2
a
Desarrollando se llega a la expresión para la varianza y la desviación tı́pica
σ 2 =
8.2.
(b − a) 2
12
;
b − a
σ = √ .
12
(8.4)
Distribución normal
La distribución continua de probabilidad más importante de toda la estadı́stica es, sin duda alguna, la
distribución normal. La importancia de esta distribución se debe a que describe con gran aproximación la
distribución de las variables asociadas con muchos fenómenos de la naturaleza. En particular, las medidas de
magnitudes fı́sicas suelen distribuirse según una distribución normal. Por ejemplo, la distribución de alturas
de un grupo de población, las medidas de calidad de procesos industriales, o la distribución de temperaturas
de una población, se pueden aproximar por distribuciones normales. Además, los errores en las medidas
también se aproximan con mucha exactitud a la distribución normal. Por otra parte, bajo ciertas condiciones,
la distribución normal constituye una buena aproximación a otras distribuciones de probabilidad, como la
binomial y la de Poisson. Frecuentemente, a la distribución normal se la denomina también distribución
gaussiana.
Estadı́stica Básica para Estudiantes de Ciencias
Febrero 20098.2 Distribución normal
91
Figura 8.2: Función de densidad, f (x), y función de distribución, F (x), para una distribución normal. Se muestran
las representaciones correspondientes a dos valores de la media µ y la desviación tı́pica σ.
8.2.1.
Definición y propiedades
Por definición, se dice que una variable aleatoria continua X sigue una distribución normal de media
µ y desviación tı́pica σ si su función de densidad es
f (x) = N (µ, σ) =
(x−µ)2
1
√ e − 2σ 2
σ 2π
;
−∞ < x < ∞
(8.5)
De esta forma, una vez que se especifican µ y σ la distribución queda determinada completamente. Puede
comprobarse que esta distribución de probabilidad cumple la condición de normalización dada en (6.4), ya
que
.
∞
f (x) dx =
−∞
1
√
σ 2π
.
∞
−∞
e −
(x−µ)2
2σ 2
1
dx = √
2π
.
∞
e −
z 2
2
−∞
1 √
2π = 1,
dz = √
2π
(8.6)
donde se ha hecho el cambio de variable z = (x − µ)/σ (es decir dx = σ dz) y se ha aplicado el siguiente
&
/ ∞
2
valor tabulado de la integral: −∞ e −ax dx = π/a.
Gráficamente (Figura 8.2), la distribución de probabilidad normal tiene forma de campana (llamada
campana de Gauss, o curva normal), simétrica (por depender de x a través del término (x−µ) 2 ), centrada en µ
y con anchura proporcional a σ (como es lógico esperar del significado de la desviación tı́pica). Evidentemente,
el máximo de la función de densidad ocurre para x = µ y, por tanto, media, mediana y moda coinciden en
ese punto. Se puede demostrar que los puntos de inflexión de la curva normal están situados en µ − σ y µ + σ.
La curva tiende asintóticamente a cero al alejarse del valor medio. Además, por (8.6), el área entre la curva
normal y el eje X es la unidad.
La función de distribución normal, útil para el cálculo de probabilidades, vendrá dada por
F (x) = P (X < x) =
Estadı́stica Básica para Estudiantes de Ciencias
1
√
σ 2π
.
x
e −
(t−µ)2
2σ 2
dt.
(8.7)
−∞
Febrero 200992
Distribuciones continuas de probabilidad
Es claro que la probabilidad de que X tome un valor entre x 1 y x 2 puede calcularse por
1
√
σ 2π
P (x 1 < X < x 2 ) =
.
x 2
e −
(x−µ)2
2σ 2
dx.
(8.8)
x 1
Se puede demostrar que, efectivamente, los parámetros µ y σ de la distribución normal coinciden con la
media y la desviación tı́pica de dicha distribución. Para el caso de la media
E(X) =
.
∞
1
√
σ 2π
xf (x) dx =
−∞
.
∞
xe −
1
dx = √
2π
(x−µ)2
2σ 2
−∞
.
∞
(µ + σz)e −
z 2
2
dz,
−∞
donde hemos aplicado el mismo cambio de variables que anteriormente (z = (x−µ)/σ). Separando la integral
en dos términos
.
. ∞
z 2
σ
dz + √
ze − 2 dz =
2π −∞
−∞
C
D ∞
z 2
µ √
σ
= √
2π + √
−e − 2
= µ,
−∞
2π
2π
µ
E(X) = √
2π
∞
e −
z 2
2
como querı́amos demostrar. Para la varianza
.
∞
1
Var(X) =
(x − µ) f (x) dx = √
σ 2π
−∞
2
σ 2
= √
2π
.
∞
z 2 e −
.
∞
−∞
z 2
2
(x − µ) 2 e −
(x−µ)2
2σ 2
dx =
dz,
−∞
donde se ha hecho el mismo cambio de variable. Integrando ahora por partes haciendo u = z, dv = ze −z
−z 2 /2
de forma que: du = dz y v = −e
σ 2
Var(X) = √
2π
8.2.2.
6
2
/2
dz,
, se obtiene
2
− z 2
−ze
.
5 ∞
5
+
5
−∞
∞
2
− z 2
e
−∞
dz
7
√ 1
σ 2 0
= √
0 + 2π = σ 2 .
2π
Distribución normal tipificada
La dificultad de integración de las ecuaciones (8.7) y (8.8) para calcular probabilidades de una distribución
hace que sea sumamente útil presentar las áreas bajo la curva normal en forma tabular. Para no tener que
presentar estas tablas para todos los posibles valores de µ y σ se define la variable normal tipificada Z
a partir de una transformación lineal de la variable original X de la forma
Z =
X − µ
.
σ
(8.9)
Haciendo esta sustitución en la función de densidad de X (f (x)dx = f (z)dz)
f (x) =
(x−µ)2
z 2
1
1
√ e − 2σ 2 ⇒ f (z) = √ e − 2 = N (0, 1).
σ 2π
2π
(8.10)
Por lo tanto, la variable tipificada sigue una distribución normal con media 0 y desviación tı́pica 1, llamada
función de densidad tipificada, o estándar. Es claro que esta distribución no depende de ningún parámetro
y su representación gráfica es una campana simétrica respecto al eje z=0, en el que alcanza el máximo valor.
El problema de calcular la probabilidad de que X se encuentre en un intervalo (x 1 , x 2 ) se puede reducir
entonces a calcular la probabilidad de que Z esté en un intervalo equivalente (z 1 , z 2 )
P (x 1 < X < x 2 ) = P (z 1 < Z < z 2 ),
con
z 1 =
x 1 − µ
σ
y
z 2 =
x 2 − µ
.
σ
Por lo tanto, usando la variable tipificada sólo es necesario trabajar con una tabla de la distribución
Estadı́stica Básica para Estudiantes de Ciencias
Febrero 20098.2 Distribución normal
93
Figura 8.3: Determinación de la probabilidad para la distribución normal tipificada.
normal. En la Tabla IV (Apéndice A) se presentan las probabilidades de que Z tenga un valor mayor que
un z α dado. Se tabulan únicamente los valores de z α ≥ 0. Es lo que se conoce como la áreas de la cola
derecha de la distribución
Ejemplo :
1
P (Z > z α ) = α = √
2π
P (Z > 1.75) = 0.0401
.
∞
e −
z 2
2
dz
z α
Para calcular la probabilidad de que Z esté por debajo de un determinado valor z α se usará, por el
condición de normalización
P (Z < z α ) = 1 − P (Z > z α ) = 1 − α
Ejemplo :
P (Z < 1.75) = 1 − 0.0401 = 0.9599
Asimismo, si z α fuese negativo, por ser la curva simétrica
P (Z > (−z α )) = 1 − P (Z < (−z α )) = 1 − P (Z > z α ) = 1 − α
Ejemplo :
P (Z > −1.75) = 0.9599
y la probabilidad de que Z esté entre dos valores se calcula por
P (z 1 < Z < z 2 ) = P (Z > z 1 ) − P (Z > z 2 )
Ejemplo :
P (−1 < Z < 0.5) = P (Z > −1) − P (Z > 0.5) =
= (1 − P (Z > 1)) − P (Z > 0.5) = 1 − 0.1587 − 0.3085 = 0.5328
como puede comprobarse en las gráficas (Figura 8.3).
En particular, puede calcularse la probabilidad de que Z se encuentre en el intervalo (−1, 1), correspon-
diente a un intervalo (µ − σ, µ + σ) para cualquier distribución normal
P (µ − σ < X < µ + σ) = P (−1 < Z < 1) = P (Z > −1) − P (Z > 1) =
Estadı́stica Básica para Estudiantes de Ciencias
Febrero 200994
Distribuciones continuas de probabilidad
= (1 − P (Z > 1)) − P (Z > 1) = 1 − 2P (Z > 1) = 1 − 2 × 0.1587 = 0.6826
De manera análoga
P (µ − 2σ < X < µ + 2σ) = P (−2 < Z < 2) = 0.9544
P (µ − 3σ < X < µ + 3σ) = P (−3 < Z < 3) = 0.9973
Nótese que estas probabilidades son más precisas que las que daba el teorema de Chebyshev, que indicaba
que las probabilidades eran, como mı́nimo 0.0, 0.75 y 0.89, para 1σ, 2σ y 3σ respectivamente.
8.2.3.
Relación con otras distribuciones
Existe un teorema básico en estadı́stica que explica porqué la distribución normal es tan frecuente. El
teorema es el siguiente:
Teorema del lı́mite central: Si X 1 , X 2 , . . . , X n son variables aleatorias independientes con medias
µ i , desviaciones tı́picas σ i , y distribuciones de probabilidad cualesquiera (y no necesariamente la misma), y
definimos la variable suma Y = X 1 + X 2 + . . . + X n , entonces, cuando n crece, la variable
" n
Y −
µ i
Z = &" n i=1 2
σ
i=1 i
tiende hacia una distribución normal estándar N (0, 1). Es decir, las probabilidades de Y las podremos
&"
"
σ i 2 ). Esto explica por qué una medida de un fenómeno
calcular utilizando la distribución normal N ( µ i ,
natural que está influenciado por un gran número de efectos (con cualquier distribución) ha de de seguir una
distribución normal. Hay que indicar además que, cuando las variables X i siguen distribuciones normales,
no es necesario que n sea grande para que la variable suma siga una distribución normal. Este teorema es
de gran utilidad en temas posteriores.
El teorema del lı́mite central además nos permite relacionar otras distribuciones con la distribución
normal. En particular, el cálculo de probabilidades de la distribución binomial puede efectuarse usando
tablas, pero puede hacerse muy complicado cuando n (número de ensayos) se hace muy grande, superando los
valores tabulados. Para estos casos, la distribución normal supone una buena aproximación a la distribución
binomial. En particular, si X es una variable aleatoria binomial con media µ = np y desviación tı́pica
√
σ = npq, la variable
X − np
Z = √
(8.11)
npq
sigue la distribución normal tipificada (o estándar) cuando n tiende a infinito (teorema de Moivre). Esto es
una consecuencia inmediata del teorema del lı́mite central ya que la variable binomial puede considerarse,
como ya vimos, como la suma de n variables de Bernoulli con media µ = p y varianza σ 2 = pq, de forma que
" n
" n
X − i=1 µ i
X − i=1 p
X − np
Z = &" n
.
= &" n
= √
2
npq
i=1 σ i
i=1 pq
Esta importante propiedad se puede comprobar además empı́ricamente calculando probabilidades binomiales
y normales. Como la distribución binomial se hace más simétrica cuando p es próximo a 0.5, la distribución
tiende más rápidamente a la normal para esos valores de p. Para p próximos a 0 ó 1, habrá que aumentar
mucho n para que la asimetrı́a, clara para un número pequeño de ensayos, desaparezca. Como regla práctica
podemos considerar que la distribución normal es una aproximación aceptable de la distribución binomial
cuando tanto np como nq sean mayor que 5 (n p > 5; n q > 5). Esto quiere decir que si p = 0.5, bastará con
que n = 10 para que la aproximación sea aceptable, pero para p = 0.1, será necesario que el número de
Estadı́stica Básica para Estudiantes de Ciencias
Febrero 20098.3 Distribución χ 2 de Pearson
95
ensayos sea, al menos, 50.
De forma similar existe una relación entre la distribución normal y la de Poisson. En particular, si X es
una variable aleatoria de Poisson con parámetro λ, la variable
Z =
X − λ
√
λ
(8.12)
sigue la distribución normal estándar cuando λ tiende a infinito. Es decir, la distribución de Poisson se puede
√
aproximar a la normal con parámetros µ = λ y σ = λ (Recordemos que λ era la media y la varianza
de la distribución de Poisson). Esta aproximación empieza a ser aceptable para λ > 5. Es también una
consecuencia del teorema del lı́mite central, ya que la variable de Poisson se puede considerar como la suma
de muchas variables de Poisson subdiviendo el intervalo de medida.
La aplicación de la distribución normal es entonces muy útil para calcular probabilidades de la distribución
binomial o de Poisson cuando n (ó λ) es grande. Hay que tener en cuenta que al pasar de una variable discreta
X a una continua X " habrá que utilizar la, llamada, corrección de continuidad, que consiste en calcular las
probabilidades como
P (x 1 ≤ X ≤ x 2 ) = P (x 1 − 0.5 < X " < x 2 + 0.5).
8.3.
Distribución χ 2 de Pearson
Sean X 1 , X 2 , . . . , X n n variables aleatorias normales con media 0 y varianza 1 independientes entre sı́,
entonces la variable
χ 2 n = X 1 2 + X 2 2 + . . . + X n 2
(8.13)
recibe el nombre de χ 2 (chi–cuadrado) con n grados de libertad. La función de densidad asociada es la
distribución χ 2 de Pearson, que se puede expresar como
f (x) =
2
1
x (n/2)−1 e −x/2
2 n/2 Γ(n/2) x> 0
0 x ≤ 0
(8.14)
donde Γ(α) es la función gamma, definida, para cualquier real positivo α, como
Γ(α) =
.
∞
x α−1 e −x dx
con
α > 0.
(8.15)
0
Nótese que la variable χ 2 toma únicamente valores positivos, al ser una suma de cuadrados. Además su
distribución depende únicamente del parámetro n, o número de grados de libertad. Gráficamente, su función
de densidad es muy asimétrica (para n = 1 corresponde a elevar al cuadrado una curva normal tipificada),
pero se va haciendo más simétrica a medida que n aumenta.
En particular, para n ≥ 30, es una buena aproximación suponer que la variable
√
√
una distribución normal con media 2n − 1 y varianza 1 (N ( 2n − 1, 1)).
&
2χ 2 n se distribuye como
Una propiedad importante de la distribución χ 2 es que si χ 2 n 1 y χ 2 n 2 son dos variables χ 2 con grados de
libertad n 1 y n 2 respectivamente, entonces la variable suma χ 2 n = χ 2 n 1 + χ 2 n 2 es una χ 2 con n = n 1 + n 2
grados de libertad. Esto es evidente a partir de la definición dada en (8.13).
La media y la varianza de la distribución χ 2 n están dadas por
µ = n
Estadı́stica Básica para Estudiantes de Ciencias
;
σ 2 = 2n.
(8.16)
Febrero 200996
Distribuciones continuas de probabilidad
Figura 8.4: Distribuciones χ 2 .
Para demostrar estas relaciones partimos de la definición de χ 2 (8.13) y utilizamos la propiedad de la media
y varianza de una suma de variables independientes
µ = E(χ 2 n ) = E
(
σ 2 = Var(χ 2 n ) = Var
n
!
X i 2
i=1
(
n
!
i=1
)
X i 2
n
!
=
i=1
)
=
3 4
E X i 2 ,
n
!
i=1
3 4
Var X i 2 .
Es necesario entonces calcular la media y la varianza de un variable X i 2 . Puesto que X i es normal con media
0 y varianza 1, se cumple
3 4
2
σ X
= E X i 2 − µ 2 X i
i
3 4
1 = E X i 2 − 0
⇒
Para calcular la varianza de X i 2 hacemos
3 4
3 4 4
1
2
− µ 2 X 2 = √
Var X i 2 = σ X
2 = E X i
i
i
2π
2
Integrando por partes con u = x 3 y dv = xe −x
/2
.
∞
⇒
x 4 e −
−∞
x 2
2
3 4
E X i 2 = 1.
3 4 2
dx − E X i 2 .
2
dx (⇒ du = 3x 2 dx, v = −e −x
/2
)
?
@
. ∞
5 ∞
3 4
x 2 5
x 2
1
Var X i 2 = √
−x 3 e − 2 5
3x 2 e − 2 dx − 1 2 =
+
−∞
2π
−∞
3
= √
2π
.
∞
x 2 e −
−∞
Y, por lo tanto,
µ =
n
!
i=1
σ 2 =
n
!
i=1
x 2
2
3 4
dx − 1 = 3E X i 2 − 1 = 2.
n
3 4 !
E X i 2 =
1 = n,
i=1
n
3 4 !
2 = 2n.
Var X i 2 =
i=1
Estas expresiones se pueden también demostrar integrando directamente en la definición de media y varianza
usando (8.14).
Estadı́stica Básica para Estudiantes de Ciencias
Febrero 20098.4 Distribución t de Student
97
Para calcular las probabilidades de que la variable χ 2 tome valores por encima o debajo de un determinado
valor puede usarse la Tabla V (Apéndice A). En ésta se dan las abscisas, denotadas por χ α,n , que dejan
a su derecha un área (o probabilidad) bajo la función de densidad igual a cierto valor α, llamado nivel de
significación. Es decir
P (χ 2 n > χ 2 α,n ) = α
P (χ 2 n < χ 2 α,n ) = 1 − α.
y
La importancia de la distribución χ 2 en estadı́stica se basa en la siguiente propiedad: Sea σ 2 la varianza
de una población normal y s 2 la varianza de una muestra de tamaño n extraı́da al azar de dicha población.
Entonces la variable aleatoria que cambia de muestra a muestra y viene dada por
χ 2 n−1 = (n − 1)
s 2
,
σ 2
(8.17)
obedece a una distribución χ 2 con (n − 1) grados de libertad. Esta propiedad es sumamente importante para
la estimación de la varianza y el contraste de hipótesis sobre la varianza σ 2 .
8.4.
Distribución t de Student
Sean X 1 , X 2 , . . . , X n y X, n + 1 variables aleatorias normales con media 0 y desviación tı́pica σ indepen-
dientes entre sı́, entonces la variable
X
t n = # "
n
1
i=1
n
(8.18)
X i 2
recibe el nombre de t de Student con n grados de libertad. Podemos llegar a una expresión más usual de
la variable t dividiendo numerador y denominador por la desviación tı́pica σ
X
Z
,
t n = # " σ 3 4 = #
2
1 2
n
X i
1
χ
n
n
i=1
n
σ
(8.19)
donde Z es una variable que sigue una distribución normal estándar N (0, 1) y χ 2 n es una χ 2 con n grados de
libertad, siendo ambas independientes.
La función de densidad asociada es la distribución t de Student (introducida por W.S. Gosset), que
se puede expresar como
f (x) = f (t) = √
nβ
1
3 1
n
2 , 2
4
6
t 2
1+
n
7 − n+1
2
;
−∞ < t < ∞
(8.20)
donde β(p, q) es la función beta, definida, para un par de reales p y q positivos, haciendo uso de la función
gamma, como
β(p, q) =
Γ(p)Γ(q)
.
Γ(p + q)
(8.21)
La demostración de que la variable t definida en (8.19) sigue la función de densidad anterior está fuera del
alcance de este libro.
El campo de variabilidad de la variable t de Student será de −∞ a ∞ y su función de densidad depen-
derá únicamente del parámetro n (grados de libertad). Nótese que, al depender f (t) de t a través de t 2 , la
función de densidad será simétrica alrededor de t = 0. Su forma será campaniforme, siendo más achatada
para valores bajos de n.
Cuando n aumenta f (t) se va haciendo cada vez más apuntada, tendiendo a la curva normal tipificada
Estadı́stica Básica para Estudiantes de Ciencias
Febrero 200998
Distribuciones continuas de probabilidad
Figura 8.5: Distribución t de Student.
(N (0, 1)) cuando n → ∞. En general, la curva normal es una buena aproximación de la distribución t cuando
n ≥ 30.
La media y la varianza de la distribución t vienen dadas por
µ =0
σ 2 =
;
n
n − 2
(para n > 2).
(8.22)
Es evidente que, al ser f (t) simétrica respecto a t = 0, la media ha de ser nula. Respecto a la varianza,
nótese que es mayor que 1 y depende del número de grados de libertad. Sólo al hacerse n muy grande, σ
tiende a 1, y, por tanto, a la distribución normal estándar.
Para calcular las áreas debajo de la distribución t se puede usar la Tabla VI (Apéndice A). Al igual
que con la distribución χ 2 , ésta da las abscisas, denotadas por t α,n , que dejan a su derecha un área (o
probabilidad) bajo la función de densidad igual a cierto valor α, llamado nivel de significación. Es decir
P (t n > t α,n ) = α
y
P (t n < t α,n ) = 1 − α.
Para valores de t negativos, al ser la distribución simétrica, se cumple
P (t n > −t α,n ) = 1 − P (t n < −t α,n ) = 1 − P (t n > t α,n ) = 1 − α,
P (t n < −t α,n ) = α,
además de
t α,n = −t 1−α,n ,
relación muy útil para calcular valores de t que dan α > 0.5, que no vienen tabulados en las tablas.
La distribución t de Student es sumamente importante para la estimación y el contraste de hipótesis
sobre la media de una población, como se verá en temas posteriores. Si se tiene una población que sigue
una distribución normal con media µ y desviación tı́pica σ (N (µ, σ)), y se extrae una muestra aleatoria de
tamaño n sobre la que se calcula una media x y una desviación tı́pica s, entonces la variable aleatoria dada
por
t n−1 =
Estadı́stica Básica para Estudiantes de Ciencias
x − µ
√
s/ n
(8.23)
Febrero 20098.5 Distribución F de Fisher
99
Figura 8.6: Distribución t de Student. Simetrı́a y P (t n < −t α,n ) = α y t α,n = −t 1−α,n .
obedece a una distribución t de Student con (n − 1) grados de libertad.
8.5.
Distribución F de Fisher
Sean χ 2 n 1 y χ 2 n 2 dos variables χ 2 de Pearson con n 1 y n 2 grados de libertad e independientes entre sı́.
Entonces, la variable aleatoria definida como
F n 1 ,n 2
χ 2 n 1
n
= 2 1
χ n 2
n 2
(8.24)
recibe el nombre de F de Fisher con n 1 y n 2 grados de libertad.
La función de densidad asociada es la distribución F de Fisher, cuya expresión es la siguiente

3 n 1 +n 2 4 0 n 1 1 n 1 /2


Γ

2
n 2
x (n 1 /2)−1


3 n 4 3 n 4
0
1 (n 1 +n 2 )/2
Γ 2 1 Γ 2 2
f (x) = f n 1 ,n 2 (x) =
n 1
1
+
x

n 2



 0
x> 0
(8.25)
x ≤ 0
Nótese que el campo de variabilidad de la variable F es entre 0 e ∞ (al ser un cociente de cuadrados) y
que su función de densidad depende exclusivamente de los dos parámetros n 1 y n 2 , aunque es importante el
orden en el que se dan estos. En particular, por la definición de F dada en (8.24), se cumple
F n 1 ,n 2 =
1
.
F n 2 ,n 1
(8.26)
La representación gráfica de la distribución F será de la forma representada en la figura y dependerá,
lógicamente, de n 1 y n 2 .
Estadı́stica Básica para Estudiantes de Ciencias
Febrero 2009100
Distribuciones continuas de probabilidad
Figura 8.7: Distribución F de Fisher.
Se puede demostrar que la media y la varianza de la distribución F de Fisher vienen dadas por
µ =
n 2
n 2 − 2
(n 2 > 2)
;
σ 2 =
2n 22 (n 1 + n 2 − 2)
n 1 (n 2 − 4)(n 2 − 2) 2
(n > 4),
(8.27)
y que la media sólo depende de n 2 .
Las áreas bajo la curva de la distribución F se pueden calcular usando la Tabla VII (Apéndice A).
Esta da, en función de n 1 y n 2 , las abscisas, denotadas por F α;n 1 ,n 2 , que dejan a su derecha un área (o
probabilidad) bajo la función de densidad igual a cierto valor α, llamado nivel de significación. Por tanto
P (F n 1 ,n 2 > F α;n 1 ,n 2 ) = α
y
P (F n 1 ,n 2 < F α;n 1 ,n 2 ) = 1 − α
En dicha Tabla se tabulan los valores de F α;n 1 ,n 2 para valores de α próximos a 0. Para α cercano a 1, puede
usarse la propiedad dada en (8.26), de forma que
F 1−α;n 2 ,n 1 =
1
.
F α;n 1 ,n 2
Es importante notar que las distribuciones χ 2 y t son en realidad casos particulares de la distribución F ,
ya que
F 1,n = t 2 n
;
F n,∞ =
χ 2 n
,
n
como puede comprobarse fácilmente (Nótese que χ 21 es una variable que sigue una distribución normal
tipificada).
La distribución F de Fisher es muy utilizada en el análisis de varianza y, en particular, es usada para
comparar las varianzas de dos poblaciones normales. Efectivamente, sea X 1 una variable aletoria normal
N (µ 1 , σ 1 ) y X 2 una variable normal N (µ 2 , σ 2 ), independientes entre sı́. Si de la primera población se extrae
una muestra aleatoria de tamaño n 1 en la cual se mide una desviación tı́pica s 1 , y de la segunda población
se extrae una muestra de tamaño n 2 , con desviación tı́pica s 2 , entonces, por la propiedad (8.17) se pueden
definir las variables χ 2
χ 2 n 1 −1 = (n 1 − 1)
Estadı́stica Básica para Estudiantes de Ciencias
s 21
σ 1 2
;
χ 2 n 2 −1 = (n 2 − 1)
s 22
,
σ 2 2
Febrero 20098.5 Distribución F de Fisher
101
de forma que se puede construir la variable F dada por
F n 1 −1,n 2 −1
χ 2 n 1 −1
n − 1
.
= 1 2
χ n 2 −1
n 2 − 1
En otras palabras, si s 21 y s 22 son las varianzas de variables aleatorias independientes de tamaños n 1 y n 2 que
se extraen de poblaciones normales con varianzas σ 1 2 y σ 2 2 respectivamente, entonces la variable
F n 1 −1,n 2 −1 =
s 21 /σ 1 2
s 22 /σ 2 2
(8.28)
sigue una distribución F de Fisher con n 1 − 1 y n 2 − 1 grados de libertad. En particular, si σ 1 = σ 2
F n 1 −1,n 2 −1 =
Estadı́stica Básica para Estudiantes de Ciencias
s 21
.
s 22