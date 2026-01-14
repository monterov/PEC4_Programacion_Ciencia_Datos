## Ejercicio 2: limpieza de los datos y filtrado
Se pretende hacer un análisis de los dos datasets que se proporcionan. Para ello, lo primero que queremos hacer es limpiar y unir los datasets. Como habrás podido comprobar en el EDA, los datasets tienen estructuras similares pero no completamente iguales. Los objetivos de este ejercicio son:

Homogeneizar ambos datasets: implica que las columnas tengan el mismo nombre y que los datos que se muestren tengan el mismo origen
Actualmente cada línea de datos muestra la información de un estudio en concreto por curso académico y sexo (para diferenciar los resultados entre hombres y mujeres). Para simplificar el análisis posterior, queremos agrupar los estudios por rama (Branca), de tal forma que tengamos una línea por curso académico y rama de estudio, donde la tasa de rendimiento y el % de abandono sea la media de los estudios que contienen esa rama.
Finalmente queremos crear un dataset fusionado a partir de ambos datasets

Para comenzar, creo una función para cargar los dos archivos.
Una vez cargados, compruebo las columnas de cada fichero 

**¿Qué columnas hay en los archivos?**

**En el archivo Rendimiento:**

1- Curs Acadèmic
2- Tipus universitat
2- Universitat
3- Sigles
4- Unitat
5- Tipus Estudi
6- Branca
7- Codi Estudi
8- Estudi
9- Sexe
10- Integrat S/N
11- Crèdits ordinaris superats
12- Crèdits ordinaris matriculats
13- Taxa rendiment

**En el archivo Abandono:**

1- Curs Acadèmic
2- Naturalesa universitat responsable, *esta entiendo que equivaldría a Tipus universitat* 
3- Universitat Responsable, *esta entiendo que equivaldría a Universitat*
4- Sigles
5- Unitat
6- Tipus Estudi
7- Branca
8- Estudi
9- Sexe Alumne, *esta entiendo que equivaldría a Sexe*
10- Tipus de centre
11- % Abandonament a primer curs 

### 2.1. Renombrar las columnas del dataset taxa_abandonament.xlsx para que coincida con el dataset rendiment_estudiants.xlsx

**Para hacerlo, creo un archivo en src\modules llamado clean.py:**

En este archivo creo una función para renombrar las columnas:

- Naturalesa universitat responsable por Tipus universitat
- Universitat Responsable por Universitat
- Sexe Alumne por Sexe

Para comprobar si funciona, en el archivo src\modules\main.py incluyo las instrucciones para cargar el ejercicio 2 y hago un print con las columnas del archivo abandono:

![Renombrado de columnas del dataset de abandono](pantallazo_4.png)


## 2.2. Eliminar las columnas de "Universitat", "Unitat" en ambos dataframes, y también "Crèdits ordinaris superats" y "Crèdits ordinaris matriculats" en el caso del dataset de rendimiento.




## 2.3. Crear y aplicar a los datasets una función que agrupe todas las filas que compartan las mismas características (excepto el nombre del estudio) para ambos datasets. La función debe devolver un nuevo dataset con:
    * Una fila por cada combinación únicas de las columnas ['Curs Acadèmic', 'Tipus universitat', 'Sigles', 'Tipus Estudi', 'Branca', 'Sexe', 'Integrat S/N']
    * Una columna con el rendimiento medio, en el caso del dataset de rendimiento y con la tasa media de abandono en el caso del dataset de abandono.

    
## 2.4. Crear una función para fusionar ambos datasets. El dataset resultante solo debe contener las filas coincidentes entre ambos datasets. A partir de ahora utilizaréis este datasets en los ejercicios futuros. 

*Nota*: Para agrupar los datasets podéis utilizar el método _groupby_ de pandas, y para fusionar ambos datasets, el método _merge_ con la propiedad _inner_. 


