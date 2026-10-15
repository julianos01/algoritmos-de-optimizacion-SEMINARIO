# algoritmos-de-optimizacion-SEMINARIO
Seminario de Algoritmos de Optimización (VIU, 03MIAR): planificación de sesiones de doblaje con fuerza bruta y algoritmo voraz en Python, con análisis de complejidad y pruebas con datos aleatorios.


Seminario – Algoritmos de Optimización

Trabajo práctico de la asignatura Algoritmos de Optimización (03MIAR) del Máster en Inteligencia Artificial de la Universidad Internacional de Valencia (VIU).

Autor: Martín Julián Osorio Marulanda

Problema elegido: organizar sesiones de doblaje

Se precisa coordinar el doblaje de una película. Los actores deben coincidir en las tomas en las que sus personajes aparecen juntos, y todos cobran la misma cantidad por cada día que se desplazan al estudio, independientemente del número de tomas que se graben. No es posible grabar más de 6 tomas por día.

Objetivo: planificar las sesiones por día de forma que el gasto en actores de doblaje sea el menor posible.

Datos: 30 tomas y 10 actores, representados como una tabla que indica qué actores participan en cada toma.

Contenido del notebook
Sección	Resumen
Espacio de soluciones	Sin restricciones hay B₃₀ ≈ 8,47 · 10²³ formas de agrupar las tomas (número de Bell). Con un máximo de 6 tomas por día quedan ≈ 7,26 · 10²³.
Estructura de datos	Cada toma se representa como el conjunto de actores que participan en ella; una solución es una lista de días con sus tomas.
Función objetivo	Sumatoria, día por día, del número de actores distintos que deben ir al estudio. Problema de minimización.
Fuerza bruta	Genera todas las planificaciones válidas sin repetir y se queda con la de menor coste. Complejidad superexponencial, O(n · B(n)).
Algoritmo voraz	Construye los días uno a uno, añadiendo siempre la toma que obliga a traer menos actores nuevos. Complejidad cuadrática, O(n²).
Datos aleatorios	Generador de instancias con actores protagonistas y secundarios, reproducible mediante semilla.
Líneas de avance	Búsqueda local, metaheurísticas, métodos exactos y variaciones del problema.
Resultados principales
Fuerza bruta: resuelve hasta 12 tomas (4.163.743 planificaciones en unos 40 segundos). Con las 30 tomas resulta inviable.
Voraz con los datos del problema: planificación de 5 días con un coste de 30 desplazamientos en menos de un milisegundo, frente a 38 si las tomas se graban en orden.
Voraz con datos aleatorios (60 tomas, 15 actores): coste de 77 desplazamientos, frente a 104 grabando en orden.
Escalabilidad: al duplicar el número de tomas (de 250 a 2.000), el tiempo del voraz se multiplica aproximadamente por 4, lo que confirma su complejidad cuadrática.
Limitación: el voraz no garantiza la solución óptima; existe al menos una planificación de las 30 tomas con coste 27.
Cómo ejecutarlo
Abrir Seminario_Algoritmos.ipynb en Google Colab o en Jupyter.
Ejecutar todas las celdas en orden (en Colab: Entorno de ejecución → Ejecutar todas).

Solo utiliza la biblioteca estándar de Python (math, itertools, random, time), por lo que no requiere instalar dependencias. La celda de fuerza bruta tarda alrededor de 40 segundos por el caso de 12 tomas.

Referencias
Cormen, T. H., Leiserson, C. E., Rivest, R. L. y Stein, C. (2022). Introduction to Algorithms (4.ª ed.). MIT Press.
OEIS Foundation. A000110: Bell numbers.
OEIS Foundation. A008277: Stirling numbers of the second kind.
Python Software Foundation. itertools.

