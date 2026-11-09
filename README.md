Lagrange vs. Newton (interpolación)

Tarea 1 de la Unidad 5 de Métodos Numéricos, ITS de Xalapa.

Soy Diego Ortiz Morales (257O00332), 3° B. El maestro es Víctor Hugo Vásquez Herrera.

Qué hace esto

Es un programita en Java que interpola el mismo punto con dos métodos, Lagrange y diferencias divididas de Newton, y al final compara qué tanto se parecen los resultados.

El código de Newton ya venía en el repo del maestro. A mí me tocó completar Lagrange, y la línea que faltaba era esta:

java
termino *= (xEval - x[j]) / (x[i] - x[j]);
Archivos

Están en src/Interpolacion/:

InterpolacionLagrange.java: el método de Lagrange.
InterpolacionNewton.java: la tabla de diferencias divididas y la evaluación.
Main.java: corre los dos y los compara.
Para correrlo

Necesitas Java 17 o más nuevo (yo uso el 26) y yo lo corrí en IntelliJ, pero te funciona en cualquier IDE.

En IntelliJ nada más abres el proyecto, checas que las tres clases estén en src/Interpolacion y le das Run a Main.

Si lo quieres por terminal, parado en la carpeta src:

javac Interpolacion/*.java
java Interpolacion.Main
Con qué probé

Los puntos (1, 2), (2, 3) y (4, 10), evaluando en x = 3. Si quieres probar otros, cambia x, y y xEval en Main.java.

Qué te debe salir
text
--- TABLA DE DIFERENCIAS DIVIDIDAS ---
x_i     f[x_i]  Orden 1 Orden 2
-----------------------------------------------------
1.00    2.0000  1.0000  0.8333
2.00    3.0000  3.5000
4.00    10.0000

--- COEFICIENTES DEL POLINOMIO (a_k) ---
a_0 = 2.0000
a_1 = 1.0000
a_2 = 0.8333

--- RESULTADO DE LA INTERPOLACIÓN NEWTON---
El valor estimado en x = 3.00 es P(3.00) = 5.6667

--- RESULTADO DE LA INTERPOLACIÓN LAGRANGE---
El valor estimado en x = 3.00 es p(3.00) = 5.6667

--- COMPARACION ---
diferencia absoluta |Newton - Lagrange| = 8.88e-16

Los dos dan 5.6667. Esa diferencia de 8.88e-16 es puro redondeo de los double, no es que algo esté mal.