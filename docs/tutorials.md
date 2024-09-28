# Ejemplo de uso

A continuación, se muestra un ejemplo de uso del método RK4 aplicado a la ecuación \( \frac{dy}{dt} = -i[O, y(t)] \):

```python
import numpy as np
import matplotlib.pyplot as plt

def rk4(f, y0, t0, h, n):
    t = t0
    y = y0
    for i in range(n):
        k1 = h * f(t, y)
        k2 = h * f(t + h/2, y + k1/2)
        k3 = h * f(t + h/2, y + k2/2)
        k4 = h * f(t + h, y + k3)
        y += (k1 + 2*k2 + 2k3 + k4) / 6
        t += h
    return y

# Graficar los resultados
O = np.array([[0, 1], [-1, 0]])
y0 = np.array([1, 0], dtype=complex)
y = rk4(lambda t, y: -1j * O @ y, y0, 0, 0.01, 100)

plt.plot(np.real(y), np.imag(y))
plt.xlabel('Re(y)')
plt.ylabel('Im(y)')
plt.show()

