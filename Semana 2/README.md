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
