# 🔢 Sudokutastrophe
Sudokutastrophe es un resolvedor de Sudoku por consola escrito en C++. Lee un tablero inicial desde un archivo de texto, y encuentra todas sus soluciones posibles mediante backtracking.
1. Carga el archivo `Tablero Sudoku.txt` con el tablero a resolver.
2. Ejecuta el programa.
3. El tablero inicial se muestra en pantalla y el programa comienza a buscar soluciones.
4. Cada solución encontrada se imprime numerada. Al finalizar, se indica el total de soluciones halladas.

---

## 📄 Formato del Tablero
El tablero de entrada es un archivo de texto que representa una cuadrícula 9×9. Los ceros indican casillas vacías. Las líneas con guiones o barras indican los separadores entre bloques.

```
 5 3 0 | 0 7 0 | 0 0 0
 6 0 0 | 1 9 5 | 0 0 0
 0 9 8 | 0 0 0 | 0 6 0
-----------------------
 8 0 0 | 0 6 0 | 0 0 3
 4 0 0 | 8 0 3 | 0 0 1
 7 0 0 | 0 2 0 | 0 0 6
-----------------------
 0 6 0 | 0 0 0 | 2 8 0
 0 0 0 | 4 1 9 | 0 0 5
 0 0 0 | 0 8 0 | 0 7 9
```

---

## ⚙️ Resolución
El programa recorre las casillas vacías de izquierda a derecha y de arriba a abajo, prueba valores del 1 al 9 y valida que se cumplan las restricciones de repetición del sudoku. Si ningún valor es válido, retrocede y prueba el siguiente.

| Tipo de restricción | Descripción                             |
|---------------------|-----------------------------------------|
| Fila                | El valor no se repite en su fila.       |
| Columna             | El valor no se repite en su columna.    |
| Bloque              | El valor no se repite en su bloque 3×3. |

Luego de la ejecución, el programa emite un mensaje final con el número de soluciones halladas. Para optimizar el tiempo de búsqueda, el número máximo de soluciones a encontar por cada tablero se definió por defecto en `10`, por lo que, si el tablero llegase a tener más soluciones posibles, el programa de igual manera se detendrá al llegar a ese límite.

| Resultado         | Mensaje final                                 |
|-------------------|-----------------------------------------------|
| 0 soluciones      | No se hallaron soluciones para este sudoku.   |
| 1 solución        | Se halló solo 1 solución.                     |
| N soluciones      | Se hallaron N soluciones.                     |
| Límite alcanzado  | Se llegó al límite de soluciones habilitadas. |

---

## 🛠️ Recursos
- 🖥️ **NetBeans** `21` — IDE utilizado para escribir y compilar el proyecto en C++.
