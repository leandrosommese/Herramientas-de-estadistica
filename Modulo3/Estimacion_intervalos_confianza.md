# Estimación por intervalos de confianza

En la práctica, interesa no solamente dar una estimación, sino precisar la incertidumbre de dicha estimación. Esto se consigue mediante la estimación por intervalos de confianza, en la cual se calcula un intervalo sobre el que podamos establecer que, con cierta probabilidad, está contenido el parámetro poblacional desconocido. De esta manera, en vez de calcular un único estimador, se determinan dos estimadores que serán los lı́mites inferior (L<sub>1</sub> ) y superior (L<sub>2</sub>) (o lı́mites de confianza) de un `intervalo de confianza` I = [L<sub>1</sub>, L<sub>2</sub>].

Al valor concreto que toma el intervalo aleatorio en una muestra en particular se le llama estimación
por intervalo. Al ser el estimador por intervalo una variable aleatoria, podrá decirse que existe una cierta
`probabilidad de que el intervalo aleatorio cubra el verdadero valor` del parámetro poblacional β.

P (L<sub>1</sub>< β < L<sub>2</sub>) = 1 − α

donde, por definición, a 1−α se le llama `nivel de confianza`.

Evidentemente, al aumentar el tamaño de la muestra ha de aumentar la precisión con que se conoce el parámetro poblacional, y por lo tanto, para un nivel de confianza fijo, el intervalo de confianza ha de hacerse más pequeño. Es decir, la longitud del intervalo de confianza indica la precisión de la estimación.

## Intervalos de confianza para la media

Supongamos en primer lugar que la población en estudio sigue una distribución normal N (µ, σ) y que como estimador puntual de la media poblacional µ se usa la media muestral X. Distinguiremos tres casos principales:

**Varianza poblacional σ 2 conocida:**

Ya se ha visto que si la población es normal, la media muestral sigue una distribución normal.

**Varianza poblacional σ 2 desconocida y n > 30**

En general, la desviación tı́pica σ de la población se desconoce a priori. Sin embargo, cuando la muestra es grande, la desviación tı́pica muestral S suele ser un estimador muy preciso de σ,

**Varianza poblacional σ 2 desconocida y n < 30**

Cuando las muestras son pequeñas la varianza muestral puede variar considerablemente de muestra a muestra, por lo que la aproximación anterior no se considera válida. En estos casos, el intervalo confianza sigue una distribución t de Student con n − 1 grados de libertad. 

## Determinación del tamaño de la muestra

Hasta ahora siempre se ha supuesto conocido el tamaño de la muestra n. Sin embargo, y fundamentalmente en el diseño de experimentos, en ocasiones el problema principal es la determinación del tamaño muestral requerido para obtener la estimación de los parámetros poblacionales con una determinada precisión.

La precisión de una estimación por intervalos de confianza vendrá marcada por la longitud del intervalo (en ocasiones, llamada error).

La longitud del intervalo es inversamente proporcional al tamaño de la muestra y la precisión aumenta, por tanto, al aumentar n. El problema se plantea entonces en cómo calcular el tamaño de la muestra n para estimar la media poblacional con una cierta precisión, es decir, para que la diferencia entre la media poblacional y muestral sea, en valor absoluto y con un cierto nivel de confianza (1 − α), menor que un cierto error.

```python
# Calculate sample size for a two-sample t-test in Python
statistics.samplesize.ttest_ind_samplesize(0.5, # effect size
                                           alpha=0.05, # alpha level
                                           power=0.8, # desired power
                                           alternative="two-sided") # two-sided test
```

Para poder aplicar la expresión anterior es necesario conocer previamente σ. Si éste no es el caso, en
la práctica se toma una muestra piloto pequeña (aunque es deseable que n > 30) para poder estimar σ
mediante la desviación tı́pica muestral S.

What do we need to calculate the sample size?

In order to calculate the sample size we always need the following parameters;

    sample size — what we need to determine;
    α-level (alpha-level), usually = 0.05 (or 5%). Learn more here.
    Power, usually 0.8 (or 80%). Learn more here.
    Effect size

What about the effect size?

The effect size is a measure of the magnitude of an effect in a statistical analysis, such as a comparison between two groups.

    For continuous outcomes (e.g., BMI, blood pressure); The effect size is expressed as the difference between two means divided by a standard deviation;
    For a discrete/binary outcome (e.g., success/failure, yes/no), the effect size can be expressed as an Odds Ratio (OR).

The larger the effect size, the smaller the sample size required to detect it. In other words the larger the difference between groups, the fewer participants you will need to prove the difference.