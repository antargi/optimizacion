Repositorio para el bin packing problem método clásico

## Procedimiento estimado:

Función read_bin_packing_instance:

Lee el archivo de instancia.
Extrae el número de problemas (P).
Para cada problema, lee el identificador, la capacidad del contenedor, el número de objetos y el número de contenedores de la mejor solución conocida.
Almacena estos datos en una lista de tuplas.

Función bin_packing_glpk:

Define y resuelve el problema de bin packing utilizando JuMP y GLPK.
Modela las variables binarias x[i,j] y y[i].
Agrega las restricciones necesarias.
Define la función objetivo para minimizar el número de contenedores utilizados.
Resuelve el modelo y devuelve los resultados.

Función bin_packing_cbc

Define y resuelve el problema de bin packing utilizando JuMP y Cbc.
Modela las variables binarias x[i,j] y y[i].
Agrega las restricciones necesarias.
Define la función objetivo para minimizar el número de contenedores utilizados.
Resuelve el modelo y devuelve los resultados.

Función process_and_solve:

Lee y procesa las instancias de bin packing desde un archivo.
Para cada problema, llama a bin_packing_glpk y muestra el resultado junto con la mejor solución conocida.


## Instancias conocidas:

Identificador del Problema: uniform1, uniform2, etc.
Capacidad del Contenedor: Valor fijo para cada instancia.
Número de Ítems (n): Varía entre 6 y 12.
Número de Contenedores en la Mejor Solución Conocida: Varía entre 2 y 5.
Tamaños de los Ítems: Listados individualmente, distribuidos uniformemente dentro del intervalo (20, 100).

Identificador del Problema: Cada problema se identifica con un nombre único, como triplet1, triplet2, etc.
Capacidad del Contenedor: Todos los contenedores tienen una capacidad fija, que varía entre 80.0 y 100.0 unidades.

Número de Ítems (n): El número de ítems en cada problema varía de 6 a 9.
Número de Contenedores en la Mejor Solución Conocida: Varía entre 2 y 3 contenedores, dependiendo del problema.

Tamaños de los Ítems:
Los ítems tienen tamaños que oscilan entre 10.0 y 35.0 unidades.
Los ítems están distribuidos en intervalos específicos para simular condiciones de empaquetado realistas y desafiantes.

El proyecto considera cuatro archivos:

invg_1.ipynb           -> primer acercamiento al problema, se prueban arreglos muy pequeños.
invg_1_1.ipynb         -> primer acercamiento al problema, se prueban instancias creadas con glpk y cbc.
invg_1_2.ipynb         -> se copian las funciones anteriores  y se intenta resolver instancias conocidas.
instance_creator.ipynb -> permite generar instancias creadas a partir de las conocidas. (Se requiere python)