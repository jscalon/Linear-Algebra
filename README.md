# Álgebra lineal desde cero

Una biblioteca de álgebra lineal escrita a mano en Python, sin apoyarse en ninguna librería
para los cálculos: vectores, matrices, determinantes y sistemas de ecuaciones.

## Qué incluye

- **Vectores:** producto por escalar, producto punto y norma.
- **Matrices:** validación, suma, producto, transpuesta, menores e intercambio de filas.
- **Determinantes**, por dos métodos:
  - **por cofactores**, recursivo, que sigue la definición pero crece muy rápido;
  - **por eliminación gaussiana**, que lleva la matriz a forma triangular y multiplica la
    diagonal, mucho más eficiente.
- **Sistemas de ecuaciones** por **Gauss-Jordan**, que además clasifica el sistema: devuelve
  la solución si es única, y distingue si no tiene solución o si tiene infinitas.

## Un detalle

Los cálculos se hacen con **fracciones exactas** (`fractions.Fraction`) y no con decimales.
Al dividir por los pivotes, los decimales acumulan errores de redondeo; con fracciones, un
determinante o una solución sale exacto, como cuando se resuelve a mano.

## Uso

```python
from CN_UnidadII import det_gaussiano, gauss_jordan

A = [[2, 1, -1],
     [-3, -1, 2],
     [-2, 1, 2]]

print(det_gaussiano(A))               # -1
print(gauss_jordan(A, [8, -11, -3]))  # [Fraction(2, 1), Fraction(3, 1), Fraction(-1, 1)]
```

## Por qué lo hice

Es un proyecto personal, escrito a mano, para practicar Python, entender mejor la matemática
detrás de cada método y ejercitar la algorítmica: pasar de un procedimiento que se hace con
lápiz y papel a un algoritmo que funcione para cualquier matriz.

---

**English** — A linear algebra library hand-written in Python: vectors, matrices, determinants
(by cofactors and by Gaussian elimination) and linear systems by Gauss-Jordan, which also tells
whether a system has one solution, none or infinitely many. Calculations use exact fractions
rather than floats, so results carry no rounding error. A personal project to practise Python,
the maths behind each method and algorithm design.
