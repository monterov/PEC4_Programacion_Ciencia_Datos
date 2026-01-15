## Ejercicio 3: Análisis Visual de Tendencias Temporales

### 3.1. Generación de Gráficos de Series Temporales
Crear una función que genere visualizaciones de series temporales con las siguientes características:

Crear dos gráficos (subplots) en una misma figura:

Gráfico 1: Evolución del % de Abandonamiento por curso académico
Gráfico 2: Evolución de la Tasa de Rendimiento por curso académico
Cada gráfico debe mostrar:

Una línea diferente para cada rama de estudio (Branca)
Leyenda identificando cada rama
Grid para facilitar la lectura
Etiquetas de ejes apropiadas
Título descriptivo
Visualización:

Tamaño de figura recomendado: 14x10 pulgadas
Utilizar colores distintos para cada rama (sugerencia: plt.cm.tab10)
Rotar etiquetas del eje X si es necesario para mejor legibilidad

### Error

pantallazo 6, error

Durante las pruebas del Ejercicio 3, me encontré con un error al intentar exportar los gráficos de Matplotlib. El script fallaba porque la función no encontraba la ruta de guardado.

El problema: La variable IMG_DIR (que apunta a src/img/) no estaba disponible en el ámbito global del programa cuando la función intentaba llamarla. En Python, si una función no encuentra una variable local ni una global previamente declarada, lanza un NameError.

Como solución, centralicé todas las rutas del proyecto al inicio de main.py. Utilicé la librería pathlib para que las rutas sean dinámicas y funcionen en cualquier sistema operativo:

pantallazo 7, solución

También me he dado cuenta al ejecutar el ejercicio 3 que también se ejecuta el ejercicio 2. Tienen que poderse ejecutar independientemente, así que...
