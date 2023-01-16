Programa para generar hisotgramas de los datos extraidos de osciloscopios de mediciones de la respuesta de tubos fotomultiplicadores (PMT), utilizando el método Single electron response(SER). Con el fin de calcular la ganancia de los PMT.

El código realiza las siguientes tareas:
  - Leer los datos de un archivo .csv
  - Graficar los datos para su exploración
  - Calcular el offset de las señales, el cual corresponde a un valor de voltaje inicial, este valor se resta a cada uno de los datos de voltaje de la señal respectiva, de este modo si se calcula la integral de la señal, se obtendrá la carga real y no una carga afectada por el offset. En pocas palabras: se ajusta el voltaje de offset a cero.
  - Verificar que el offset esté aplicándose correctamente.
  - Calcular las integrales de cada una de las señales y dividirla por la impedancia utilizada, en este caso son 50 ohm, de este modo se obtiene la carga de la señal.
  - Generar un histograma con matplolib de las cargas.
  - Generar un histograma con ROOT (programa creado por CERN para la visualización y análisis de datos), este histograma no se puede ver en GitHub.
  - Realizar un fit con ROOT al histograma obtenido.
  - Calcular la ganancia del PMT.

Sobre las imagenes del repositorio:
- El archivo histograma-root-ser800.png es la imagen del histograma y los fits realizados con ROOT.
- El archivo DATOS-NOPROCESADOS.png es la imagen del histograma de los datos si a estos no se les aplica la corrección de offset. Se añade para demostrar la necesidad de realizar esta corrección.

Idealmente debe verse en el hisograma un contenedor en el valor de carga 0 con mucha cantidad de datos y una distribución gaussiana a la derecha de este, representan las señales vacías y las señales que correponden a cuando incide 1 solo fotón, respectivamente.
Esto se produce debido a que la eficiencia de detección de los PMT suele ser baja, menos del 20%.
