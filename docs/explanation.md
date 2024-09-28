# Explicación del Método RK4

El método RK4 es un método numérico para aproximar soluciones de ecuaciones diferenciales ordinarias. Calcula cuatro inclinaciones intermedias para mejorar la precisión de la solución en cada paso:

\[
k_1 = h f(t_n, y_n)
\]
\[
k_2 = h f(t_n + \frac{h}{2}, y_n + \frac{k_1}{2})
\]
\[
k_3 = h f(t_n + \frac{h}{2}, y_n + \frac{k_2}{2})
\]
\[
k_4 = h f(t_n + h, y_n + k_3)
\]

Finalmente, la solución en el siguiente paso es:

\[
y_{n+1} = y_n + \frac{1}{6}(k_1 + 2k_2 + 2k_3 + k_4)
\]

