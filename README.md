# TALLER ENFOQUE SIMULACIÓN BASADO EN EVENTOS DISCRETOS

Realice la implementación de los siguientes modelos y funciones en lenguaje R. El código debe ir acompañado de cualquier análisis que usted realice para desarrollar su solución. Entregue la solución en formato notebook (*.Rmd). De la librería de generación de números aleatorios de R solo se puede usar la función *runif()*.

---

En un modelo de cola con un solo servidor, la llegada de unos clientes sigue un proceso no homogéneo de Poisson, cuya tasa inicial es 3 por hora. La tasa se incrementa de forma lineal hasta que alcanza las 12 llegadas por hora a las 5 horas. Finalmente, la tasa de llegada de clientes decrece linealmente hasta que llega a 5 llegadas por hora después de 5 horas más. Realice la simulación durante las 10 horas si el tiempo de servicio sigue una distribución exponencial con tasa de 9 por hora. Use la simulación para estimar el valor esperado de clientes atendidos durante las 10 horas de simulación. Verifique que la distribución de llegada de los clientes sigue el proceso de Poisson descrito anteriormente. Ejecute 1000 veces la simulación para obtener el promedio del estimado.

---

Un sistema necesita $n$ máquinas funcionando. Para asegurarse en caso de fallas mecánicas se dispone de algunas máquinas adicionales. Si una máquina falla es inmediatamente reemplazada por una de las máquinas disponibles. La máquina con fallos es enviada a la sección de reparación. La sección de reparación consiste en una sola persona que repara las máquinas de una en una. Una vez la máquina es reparada se reincorpora al conjunto de máquinas disponibles como reemplazo. Todos los tiempos de reparación son variables aleatorias independientes con distribución de probabilidad $G$. Cada vez que una maquina es puesta en uso, el tiempo que funciona antes de sufrir una falla mecánica es una variable aleatoria con función de probabilidad $F$. Se dice que el sistema colapsa cuando una máquina falla y no hay máquinas extra disponibles para reemplazo. Asumiendo que inicialmente existen $n + s$ máquinas funcionales de las cuales $n$ están en uso, y $s$ pueden ser utilizadas para reemplazar las máquinas que fallen, encuentre el tiempo esperado $T$, en el cual el sistema colapsa después de ejecutar la simulación 100 veces, si $n = 4$, $s = 3$, $F(x) = 1 - e^{-x}$, y $G(x) = 1 − e^{-2x}$. Realice el análisis del sistema y utilizando la estrategia de simulación basada en eventos discretos implemente la simulación en R.

---

Un sistema experimenta choques que ocurren de acuerdo con un proceso de Poisson que tiene una tasa de 1 por hora. Cada choque tiene una cierta cantidad de daños asociados. Estos daños son asumidos como variables aleatorias independientes (que también son independientes del tiempo en el cual ocurre el choque), y que tiene la siguiente función de densidad de probabilidad:

$f(x) = xe^{-x}, x > 0$

Los daños se disipan en el tiempo con una tasa exponencial $\alpha$ – Esto es, un choque cuyo daño inicial es $y$ tendrá un valor de daño igual a $ye^{-\alpha s}$ en el tiempo $s$ después de que el choque ocurra. Adicionalmente, los valores de daño son acumulativos. Así, por ejemplo, si en el instante $t$ ha habido un total de 2 choques, originados en los tiempos $t_{1}$ y $t_{2}$, y que tuvieron daños iniciales $y_{1}$ y $y_{2}$, entonces el daño total en el instante $t$ es $\sum_{i=1}^{2} y_{i}e^{-\alpha (t-t_{i})}$. El sistema falla cuando el daño total excede una constante fija $C$.

Suponga que estamos interesados en usar un estudio de simulación para estimar el valor del tiempo promedio en el cual el sistema falla. Defina los eventos, variables de estado del sistema, variables contadoras y variables de salida de este modelo. Realice una implementación de este modelo en lenguaje de programación R. Extienda el programa para realizar $k$ réplicas que permita estimar el valor del tiempo promedio en el cual el sistema falla, si tenemos los valores de $\alpha = 0.5$, $C = 5$, y $k = 1000$. ¿Cuál es ese tiempo promedio de falla?
