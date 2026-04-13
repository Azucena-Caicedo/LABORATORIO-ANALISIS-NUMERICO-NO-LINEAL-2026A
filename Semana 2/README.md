**Referencia**: Quarteroni, A., Sacco, R., & Saleri, F. , 2000. Numerical Mathematics. Lugar de publicación: . EditorialSpringer
# Método de la Secante — Ejemplo 6.4

## 📌 Definición del problema

Queremos encontrar la raíz de la función:

$$
f(x) = \cos^2(2x) - x^2
$$

con los siguientes datos iniciales:

- $x^{(-1)} = 0$
- $x^{(0)} = 0.75$
- Tolerancia:  
  $$
  \varepsilon = 10^{-10}
  $$

---

## 📐 Fórmula del método de la secante

El método está definido por:

$$
x^{(k+1)} = x^{(k)} - 
\frac{x^{(k)} - x^{(k-1)}}{f(x^{(k)}) - f(x^{(k-1)})} \, f(x^{(k)})
$$

---
# Método Regula Falsi (Falsa Posición)

## 📌 Definición

El método **Regula Falsi** es un método numérico para encontrar raíces de una función $f(x)=0$.  
Es una variante del método de la secante, pero con la diferencia de que **mantiene siempre un intervalo donde la raíz está garantizada**.

---

## 🎯 Condición inicial

Se requieren dos puntos iniciales $a$ y $b$ tales que:

$$
f(a)\cdot f(b) < 0
$$

Esto garantiza que existe al menos una raíz en el intervalo $[a,b]$.

---

## 📐 Fórmula del método

En cada iteración se construye una recta secante entre los puntos $(a,f(a))$ y $(b,f(b))$.

La intersección con el eje $x$ es:

$$
x^{(k+1)} = b - \frac{b-a}{f(b)-f(a)}\,f(b)
$$

---

## 🔁 Actualización del intervalo

Después de calcular $x^{(k+1)}$, se evalúa el signo de la función:

- Si:
$$
f(a)\cdot f(x^{(k+1)}) < 0
$$
entonces la raíz está en $[a, x^{(k+1)}]$ y se actualiza:
$$
b = x^{(k+1)}
$$

- Si:
$$
f(x^{(k+1)})\cdot f(b) < 0
$$
entonces la raíz está en $[x^{(k+1)}, b]$ y se actualiza:
$$
a = x^{(k+1)}
$$

---

## 🧠 Idea del método

- Se construye una secante como en el método de la secante.
- Pero a diferencia de este, se conserva siempre el intervalo donde hay cambio de signo.
- Esto garantiza que la raíz nunca se pierde.

---

## 📈 Propiedades

- ✔ Garantiza convergencia (método global)
- ✔ La raíz siempre permanece dentro del intervalo
- ❌ Convergencia lineal (más lento que la secante)
- ❌ Puede volverse lento si un extremo se queda fijo muchas iteraciones

---

## ⚠️ Observación importante

El método puede volverse lento cuando uno de los extremos del intervalo no cambia, lo que provoca que la secante se construya repetidamente con el mismo punto.

---

## 🎯 Resumen

El método Regula Falsi combina:

- la rapidez del método de la secante  
- con la seguridad del método de bisección  

manteniendo siempre un intervalo donde se garantiza la existencia de la raíz.
# 📊 Comparación de métodos de búsqueda de raíces

| Método        | Idea principal                              | Requiere derivada | Mantiene intervalo | Convergencia | Orden \(p\) | Rapidez | Ventajas | Desventajas |
|--------------|--------------------------------------------|------------------|--------------------|--------------|-------------|---------|----------|-------------|
| **Bisección** | Divide el intervalo en dos                | ❌               | ✔                  | Lineal       | \(p = 1\)   | 🐢 Lenta | Muy estable, siempre converge | Muy lento |
| **Secante**   | Usa secante entre dos puntos              | ❌               | ❌                 | Superlineal  | \(p \approx 1.618\) | ⚡ Rápida | No usa derivadas, rápida | Puede fallar |
| **Regula Falsi** | Secante con cambio de signo garantizado | ❌               | ✔                  | Lineal       | \(p = 1\)   | 🐢 Media-lenta | Más segura que secante | Puede estancarse |

---

## 🎯 Interpretación de la rapidez

- 🐢 **Lenta (Bisección):** reduce el error de forma constante  
- ⚡ **Rápida (Secante):** mejora cada vez más rápido  
- 🐢⚡ **Intermedia (Regula Falsi):** segura pero puede volverse lenta  

---

## 🧠 Idea clave

- **Bisección:** seguridad total  
- **Secante:** velocidad  
- **Regula Falsi:** equilibrio entre seguridad y rapidez  

---

## 📌 Conclusión

- ✔ Si quieres seguridad → **Bisección o Regula Falsi**  
- ✔ Si quieres rapidez → **Secante**  
- ✔ En práctica → se combinan métodos
