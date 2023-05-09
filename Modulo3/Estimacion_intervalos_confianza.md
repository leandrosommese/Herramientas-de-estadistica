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

¿Qué necesitamos para calcular el tamaño de la muestra?

Para calcular el tamaño de la muestra siempre necesitamos los siguientes parámetros;

    - Nivel α (nivel alfa), generalmente = 0.05
    - Potencia, normalmente 0,8
    - Tamaño del efecto

¿A qué se refiere con el tamaño del efecto?

El tamaño del efecto es una medida de la magnitud de un efecto en un análisis estadístico, como una comparación entre dos grupos.

    Para resultados continuos, el tamaño del efecto se expresa como la diferencia entre dos medias dividida por una desviación estándar;
    Para un resultado discreto/binario, el tamaño del efecto se puede expresar como una razón de probabilidades (OR).

Cuanto mayor sea el tamaño del efecto, menor será el tamaño de muestra necesario para detectarlo. En otras palabras, cuanto mayor sea la diferencia entre los grupos, menos participantes necesitará para demostrar la diferencia.