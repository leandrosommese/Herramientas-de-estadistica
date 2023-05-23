Medición del rendimiento de un clasificador

Hasta ahora hemos asumido generalmente que la mejor (o única) forma de medir el rendimiento de un clasificador es por su precisión predictiva, es decir, la proporción de instancias invisibles que clasifica correctamente. Sin embargo, este no es necesariamente el caso.
Hay muchos otros tipos de algoritmos de clasificación además de los
discutido en este libro. Algunos requieren considerablemente más computación o memoria.
que otros. Algunos requieren un número sustancial de instancias de entrenamiento para dar
resultados confiables. Dependiendo de la situación, el usuario puede estar dispuesto a aceptar
un nivel más bajo de precisión predictiva para reducir el tiempo de ejecución/memoria
requisitos y/o el número de instancias de capacitación necesarias.
Una compensación más difícil ocurre cuando las clases están gravemente desequilibradas.
Supongamos que estamos considerando invertir en una de las empresas líderes cotizadas en
determinada bolsa de valores. ¿Podemos predecir qué empresas irán a la quiebra?
en los próximos dos años, para que podamos evitar invertir en ellos? La proporción de
tales empresas es obviamente pequeña. Digamos que es 0.02 (un valor ficticio), entonces
en promedio de cada 100 empresas 2 quebrarán y 98 no.
Llame a estas empresas "malas" y "buenas" respectivamente.
Si tenemos un clasificador muy 'confiado' que siempre predice 'bueno' bajo todos los
circunstancias, su precisión predictiva será de 0,98, un valor muy alto. mirado
solo en términos de precisión predictiva, este es un clasificador muy exitoso. Desgraciadamente
afortunadamente no nos ayudará en absoluto a evitar invertir en malas empresas.
Por otro lado, si queremos estar muy seguros, podríamos usar una actitud muy ‘cautelosa’.
clasificador que siempre predecía "malo". De esta manera nunca perderíamos nuestro dinero.
en una empresa en quiebra pero tampoco invertiría nunca en una buena.

This is similar to the ultra-safe strategy for air traﬃc control: ground all aeroplanes, so
you can be sure that none of them will crash. In real life, we are usually willing
to accept the risk of making some mistakes in order to achieve our objectives.
It is clear from this example that neither the very trusting nor the very
cautious classiﬁer is any use in practice. Moreover, where the classes are severely
unbalanced (98% to 2% in the company example), predictive accuracy on its
own is not a reliable indicator of a classiﬁer’s eﬀectiveness.
12.1 True and False Positives and Negatives
The idea of a confusion matrix was introduced in Chapter 7. When there are
two classes, which we will call positive and negative (or simply + and −), the
confusion matrix consists of four cells, which can be labelled T P , F P , F N and
T N as in Figure 12.1.
Actual class
+
−
+
TP
FP
Predicted class
−
FN
TN
Total
instances
P
N
Figure 12.1 True and False Positives and Negatives
TP: true positives
The number of positive instances that are classiﬁed as positive
FP: false positives
The number of negative instances that are classiﬁed as positive
FN: false negatives
The number of positive instances that are classiﬁed as negative
TN: true negatives
The number of negative instances that are classiﬁed as negative
P = TP + FN
The total number of positive instances
N = FP + TN
The total number of negative instancesMeasuring the Performance of a Classiﬁer
177
It is often useful to distinguish between the two types of classiﬁcation error:
false positives and false negatives.
False positives (also known as Type 1 Errors) occur when instances that
should be classiﬁed as negative are classiﬁed as positive.
False negatives (also known as Type 2 Errors) occur when instances that
should be classiﬁed as positive are classiﬁed as negative.
Depending on the application, errors of these two types are of more or less
importance.
In the following examples we will make the assumption that there are only
two classiﬁcations, which will be called positive and negative, or + and −. The
training instances can then be considered as positive and negative examples
of a concept such as ‘good company’, ‘patient with brain tumour’ or ‘relevant
web page’.
Bad Company Application. Here we would like the number of false positives
(bad companies that are classiﬁed as good) to be as small as possible, ideally
zero. We would probably be willing to accept a high proportion of false negatives
(good companies classiﬁed as bad) as there are a large number of possible
companies to invest in.
Medical Screening Application. It would not be possible in any realistic sys-
tem of healthcare to screen the entire population for a condition that occurs
only rarely, say a brain tumour. Instead the doctor uses his or her experience
to judge (based on symptoms and other factors) which patients are most likely
to be suﬀering from a brain tumour and sends them to a hospital for screening.
For this application we might be willing to accept quite a high proportion
of false positives (patients screened unnecessarily) perhaps as high as 0.90, i.e.
only 1 in 10 of patients screened has a brain tumour, or even higher. However
we would like the proportion of false negatives (patients with a brain tumour
who are not screened) to be as small as possible, ideally zero.
Information Retrieval Application. A web search engine can be looked at as a
kind of classiﬁer. Given a speciﬁcation such as ‘pages about American poetry’ it
eﬀectively classiﬁes all pages on the web that are known to it as either ‘relevant’
or ‘not relevant’ and displays the URLs of the ‘relevant’ ones to the user. Here
we may be willing to accept a high proportion of false negatives (relevant pages
left out), perhaps 30% or even higher, but probably do not want too many false
positives (irrelevant pages included), say no more than 10%. In such information178
Principles of Data Mining
retrieval applications the user is seldom aware of the false negatives (relevant
pages not found by the search engine) but false positives are visible, waste time
and irritate the user.
These examples illustrate that, leaving aside the ideal of perfect classiﬁca-
tion accuracy, there is no single combination of false positives and false neg-
atives that is ideal for every application and that even a very high level of
predictive accuracy may be unhelpful when the classes are very unbalanced. To
go further we need to deﬁne some improved measures of performance.
12.2 Performance Measures
We can now deﬁne a number of performance measures for a classiﬁer applied
to a given test set. The most important ones are given in Figure 12.2. Several
measures have more than one name, depending on the technical area (signal
processing, medicine, information retrieval etc.) in which they are used.
For information retrieval applications the most commonly used measures
are Recall and Precision. For the search engine application, Recall measures
the proportion of relevant pages that are retrieved and Precision measures
the proportion of retrieved pages that are relevant. The F1 Score combines
Precision and Recall into a single measure, which is their product divided by
their average. This is known as the harmonic mean of the two values.
The values of P and N , the number of positive and negative instances, are
ﬁxed for a given test set, whichever classiﬁer is used. The values of the measures
given in Figure 12.2 will generally vary from one classiﬁer to another. Given
the values of True Positive Rate and False Positive Rate (as well as P and N )
we can derive all the other measures.
We can therefore characterise a classiﬁer by its True Positive Rate (TP
Rate) and False Positive Rate (FP Rate) values, which are both proportions
from 0 to 1 inclusive. We start by looking at some special cases.
A: The Perfect Classiﬁer
Here every instance is correctly classiﬁed. T P = P , T N = N and the
confusion matrix is:
Actual class
+
−
+
P
0
Predicted class
−
0
N
Total
instances
P
NMeasuring the Performance of a Classiﬁer
179
True Positive
Rate
or Hit Rate
or Recall
or Sensitivity or
TP Rate
False Positive
Rate
or False Alarm
Rate
or FP Rate
False Negative
Rate
or FN Rate TP/P The proportion of
positive instances that
are correctly classiﬁed as
positive
FP/N The proportion of
negative instances that
are erroneously classiﬁed
as positive
FN/P True Negative
Rate
or Speciﬁcity
or TN Rate
Precision
or Positive
Predictive Value
F1 Score TN/N The proportion of
positive instances that
are erroneously classiﬁed
as negative = 1 − True
Positive Rate
The proportion of
negative instances that
are correctly classiﬁed as
negative
Proportion of instances
classiﬁed as positive that
are really positive
A measure that combines
Precision and Recall
The proportion of
instances that are
correctly classiﬁed
Accuracy or
Predictive
Accuracy
Error Rate
TP/(TP+FP)
(2 × Precision × Recall)
/(Precision + Recall)
(TP + TN)/(P + N)
(FP + FN)/(P + N)
The proportion of
instances that are
incorrectly classiﬁed
Figure 12.2 Some Performance Measures for a Classiﬁer180
Principles of Data Mining
TP Rate (Recall) = P/P = 1
FP Rate = 0/N = 0
Precision = P/P = 1
F1 Score = 2 × 1/(1 + 1) = 1
Accuracy = (P + N )/(P + N ) = 1
B: The Worst Possible Classiﬁer
Every instance is wrongly classiﬁed. T P = 0 and T N = 0. The confusion
matrix is:
Actual class
+
−
Predicted class
+
−
0
P
N
0
Total
instances
P
N
TP Rate (Recall) = 0/P = 0
FP Rate = N/N = 1
Precision = 0/N = 0
F1 Score is not applicable (as Precision + Recall = 0)
Accuracy = 0/(P + N ) = 0
C: The Ultra-liberal Classiﬁer
This classiﬁer always predicts the positive class. The True Positive rate is
1 but the False Positive rate is also 1. The False Negative and True Negative
rates are both zero. The confusion matrix is:
Actual class
+
−
+
P
N
Predicted class
−
0
0
Total
instances
P
N
TP Rate (Recall) = P/P = 1
FP Rate = N/N = 1
Precision = P/(P + N )
F1 Score = 2 × P/(2 × P + N )
Accuracy = P/(P +N ), which is the proportion of positive instances in the
test set.
D: The Ultra-conservative Classiﬁer
This classiﬁer always predicts the negative class. The False Positive rate is
zero, but so is the True Positive rate. The confusion matrix is:
Actual class
+
−
+
0
0
Predicted class
−
P
N
Total
instances
P
NMeasuring the Performance of a Classiﬁer
181
TP Rate (Recall) = 0/P = 0
FP Rate = 0/N = 0
Precision is not applicable (as T P + F P = 0)
F1 Score is also not applicable
Accuracy = N/(P + N ), which is the proportion of negative instances in
the test set.
12.3 True and False Positive Rates versus
Predictive Accuracy
One of the strengths of characterising a classiﬁer by its TP Rate and FP Rate
values is that they do not depend on the relative sizes of P and N . The same
applies to using the FN Rate and TN Rate values or any other combination
of two ‘rate’ values calculated from diﬀerent rows of the confusion matrix. In
contrast, Predictive Accuracy and all the other measures listed in Figure 12.2
are derived from values in both rows of the table and so are aﬀected by the
relative sizes of P and N , which can be a serious weakness.
To illustrate this, suppose that the positive class corresponds to those who
pass a driving test at the ﬁrst attempt and that the negative class corresponds
to those who fail. Assume that the relative proportions in the real world are 9
to 10 (a ﬁctitious value) and the test set correctly reﬂects this.
Then the confusion matrix for a particular classiﬁer on a given test set
might be
Actual class
+
−
Predicted class
+
−
8, 000
1, 000
2, 000
8, 000
Total
instances
9, 000
10, 000
This gives a true positive rate of 0.89 and a false positive rate of 0.2, which
we will assume is a satisfactory result.
Now suppose that the number of successes grows considerably over a period
of time because of improved training, so that there is a higher proportion of
passes. With this assumption a possible confusion matrix for a future series of
trials would be as follows.
Actual class
+
−
Predicted class
+
−
80, 000
10, 000
2, 000
8, 000
Total
instances
90, 000
10, 000182
Principles of Data Mining
The classiﬁer will of course still work exactly as well as before to predict
the correct classiﬁcation of either a pass or a fail with which it is presented. For
both confusion matrices the values of TP Rate and FP Rate are the same (0.89
and 0.2 respectively). However the values of the Predictive Accuracy measure
are diﬀerent.
For the original confusion matrix, Predictive Accuracy is 16,000/19,000 =
0.842. For the second one, Predictive Accuracy is 88,000/100,000 = 0.88.
An alternative possibility is that over a period of time there is a large
increase in the relative proportion of failures, perhaps because of an increase
in the number of younger people being tested. A possible confusion matrix for
a future series of trials would be as follows.
Actual class
+
−
Predicted class
+
−
8, 000
1, 000
20, 000
80, 000
Total
instances
9, 000
100, 000
Here the Predictive Accuracy is 88,000/109,000 = 0.807.
Whichever of these test sets was used with the classiﬁer the TP Rate and
FP Rate values would be the same. However the three Predictive Accuracy
values would vary from 81% to 88%, reﬂecting changes in the relative numbers
of positive and negative values in the test set, rather than any change in the
quality of the classiﬁer.
12.4 ROC Graphs
The TP Rate and FP Rate values of diﬀerent classiﬁers on the same test set are
often represented diagrammatically by a ROC Graph. The abbreviation ROC
Graph stands for ‘Receiver Operating Characteristics Graph’, which reﬂects its
original uses in signal processing applications.
On a ROC Graph, such as Figure 12.3, the value of FP Rate is plotted on
the horizontal axis, with TP Rate plotted on the vertical axis.
Each point on the graph can be written as a pair of values (x, y) indicating
that the FP Rate has value x and the TP Rate has value y.
The points (0, 1), (1, 0), (1, 1) and (0, 0) correspond to the four special cases
A, B, C and D in Section 12.2, respectively. The ﬁrst is located at the best
possible position on the graph, the top left-hand corner. The second is at the
worst possible position, the bottom right-hand corner. If all the classiﬁers are
good ones, all the points on the ROC Graph are likely to be around the top
left-hand corner.Measuring the Performance of a Classiﬁer
183
Figure 12.3 Example of ROC Graph
The other six points shown are (0.1, 0.6), (0.2, 0.5), (0.4, 0.2), (0.5, 0.5),
(0.7, 0.7) and (0.2, 0.7).
One classiﬁer is better than another if its corresponding point on the ROC
Graph is to the ‘north-west’ of the other’s. Thus the classiﬁer represented by
(0.1, 0.6) is better than the one represented by (0.2, 0.5). It has a lower FP Rate
and a higher TP Rate. If we compare points (0.1, 0.6) and (0.2, 0.7), the latter
has a higher TP Rate but also a higher FP Rate. Neither classiﬁer is superior
to the other on both measures and the one chosen will depend on the relative
importance given by the user to the two measures.
The diagonal line joining the bottom left and top right-hand corners corre-
sponds to random guessing, whatever the probability of the positive class may
be. If a classiﬁer guesses positive and negative at random with equal frequency,
it will classify positive instances correctly 50% of the time and negative in-
stances as positive, i.e. incorrectly, 50% of the time. Thus both the TP Rate
and the FP Rate will be 0.5 and the classiﬁer will lie on the diagonal at point
(0.5, 0.5).
Similarly, if a classiﬁer guesses positive and negative at random with positive
selected 70% of the time, it will classify positive instances correctly 70% of the
time and negative instances as positive, i.e. incorrectly, 70% of the time. Thus
both the TP Rate and the FP Rate will be 0.7 and the classiﬁer will lie on the
diagonal at point (0.7, 0.7).
We can think of the points on the diagonal as corresponding to a large
number of random classiﬁers, with higher points on the diagonal corresponding
to higher proportions of positive classiﬁcations generated on a random basis.184
Principles of Data Mining
Figure 12.4 Example of ROC Graph (Amended)
The upper left-hand triangle corresponds to classiﬁers that are better than
random guessing. The lower right-hand triangle corresponds to classiﬁers that
are worse than random guessing, such as the one at (0.4, 0.2).
A classiﬁer that is worse than random guessing can be converted to one
that is better than random guessing simply by reversing its predictions, so that
every positive prediction becomes negative and vice versa. By this method the
classiﬁer at (0.4, 0.2) can be converted to the new one at (0.2, 0.4) in Figure
12.4. The latter point is the former reﬂected about the diagonal line.
12.5 ROC Curves
In general, each classiﬁer corresponds to a single point on a ROC Graph. How-
ever there are some classiﬁcation algorithms that lend themselves to ‘tuning’,
so that it is reasonable to think of a series of classiﬁers, and thus points on a
ROC Graph, one for each value of some variable, generally known as a param-
eter. For a decision tree classiﬁer such a parameter might be the ‘depth cutoﬀ’
(see Chapter 9) which can vary from 1, 2, 3 etc.
In such a case the points can be joined to form a ROC Curve such as
Figure 12.5.Measuring the Performance of a Classiﬁer
185
Figure 12.5 Example of ROC Curve
Examining ROC curves can give insights into the best way of tuning a
classiﬁcation algorithm. In Figure 12.5 performance clearly degrades after the
third point in the series.
The performance of diﬀerent types of classiﬁer with diﬀerent parameters
can be compared by inspecting their ROC curves.
12.6 Finding the Best Classiﬁer
There is no infallible way of ﬁnding the best classiﬁer for a given application,
unless we happen to ﬁnd one that gives perfect performance, corresponding
to the (0, 1) point on the ROC Graph. One approach that is sometimes used
is to measure the distance of a classiﬁer on the ROC Graph from the perfect
classiﬁer.
Figure 12.6 shows the  points (fprate, tprate) and (0, 1). The Euclidean
distance between them is fprate 2 + (1 − tprate) 2 .

We can write Euc = fprate 2 + (1 − tprate) 2 .
The smallest possible value of Euc is zero,
√ when fprate = 0 and tprate = 1
(the perfect classiﬁer). The largest value is 2, when fprate is 1 and tprate is
zero (the worst possible classiﬁer). We could hypothesise that the smaller the
value of Euc the better the classiﬁer.
Euc is a useful measure but does not take into account the relative impor-
tance of true and false positives. There is no best answer to this. It depends on
the use to which the classiﬁer will be put.186
Principles of Data Mining
Figure 12.6 Measuring the Distance from the Perfect Classiﬁer
We can specify the relative importance of making tprate as close to 1 as
possible and making fprate as close to zero as possible by a weight w from 0 to
1 and deﬁne 
the Weighted Euclidean Distance as
WEuc = (1 − w)fprate 2 + w(1 − tprate) 2
If w = 0 this reduces to WEuc = fprate, i.e. we are only interested in
minimising the value of fprate.
If w = 1 it reduces to WEuc = 1 − tprate, i.e. we are only interested in
minimising the diﬀerence between tprate and 1 (thus maximising tprate).
If w = 0.5  the formula reduces to
WEuc = 0.5 ∗ fprate 2 + 0.5 ∗ (1 − tprate) 2
which
 is a constant multiple of
fprate 2 + (1 − tprate) 2 , so the eﬀect when comparing one classiﬁer with
another is the same as if there were no weighting at all.