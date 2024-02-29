# Clustering

## Introducción

El clustering es una tarea de aprendizaje automático no supervisado en la que busca encontrar objetos que se parezcan entre sí y agruparlos en grupos denominados clusters de manera que los elementos dentro de un mismo grupo sean más similares entre sí que con los elementos de otros grupos.

En una configuración profesional, clustering puede ser usado para determinar cosas como segmentación del mercado o determinar que grupo etaria compra que artículos por ejemplo. Otro uso podría ser detectar casos anómalos, como por ejemplo detectar fraudes de un dataset de transacciones de tarjeta de credito. O tambien podría usarse clustering para determinar tumores en un batch de escaneos médicos.

Una vez que los datos están organizados en clusters, se les asigna un identificador de clúster (cluster ID), y esta técnica puede ser útil para preservar la privacidad de un conjunto de datos; En su lugar, puede hacer referencia a un punto de datos por su identificador de clúster, en lugar de por datos identificables más reveladores.


## Scikit-Learn Clustering

[Scikit-learn](https://scikit-learn.org/stable/modules/clustering.html) ofrece una larga lista de métodos para clustering. El tipo que elijas dependerá de cada caso particular. Según la documentación, cada método tiene sus beneficios. Aquí dejamos una lista simplificada de los métodos que soporta Scikit-learn y sus respectivos casos de uso apropiados.

- K-Means:	general purpose, inductive
- Affinity propagation:	many, uneven clusters, inductive
- Mean-shift:	many, uneven clusters, inductive
- Spectral clustering:	few, even clusters, [transductive](https://en.wikipedia.org/wiki/Transduction_(machine_learning))
- Ward hierarchical clustering:	many, constrained clusters, transductive
- Agglomerative clustering:	many, constrained, non Euclidean distances, transductive
- DBSCAN:   [non-flat](https://datascience.stackexchange.com/questions/52260/terminology-flat-geometry-in-the-context-of-clustering) geometry, uneven clusters, transductive
- OPTICS:	[non-flat](https://datascience.stackexchange.com/questions/52260/terminology-flat-geometry-in-the-context-of-clustering) geometry, uneven clusters with variable density, transductive
- Gaussian mixtures:	[flat geometry](https://datascience.stackexchange.com/questions/52260/terminology-flat-geometry-in-the-context-of-clustering), inductive
- BIRCH:	large dataset with outliers, inductive


## Clustering algorithms

Hay mas de 100 algortismos de clustering, y su uso, como dijimos, depende de la naturaleza de los datos. Veamos algunos de los mas utilizados.

- **Hierarchical clustering**. If an object is classified by its proximity to a nearby object, rather than to one farther away, clusters are formed based on their members' distance to and from other objects. Scikit-learn's agglomerative clustering is hierarchical.

- **Centroid clustering**. This popular algorithm requires the choice of 'k', or the number of clusters to form, after which the algorithm determines the center point of a cluster and gathers data around that point. K-means clustering is a popular version of centroid clustering. The center is determined by the nearest mean, thus the name. The squared distance from the cluster is minimized.

- **Distribution-based clustering**. Based in statistical modeling, distribution-based clustering centers on determining the probability that a data point belongs to a cluster, and assigning it accordingly. Gaussian mixture methods belong to this type.

- **Density-based clustering**. Data points are assigned to clusters based on their density, or their grouping around each other. Data points far from the group are considered outliers or noise. DBSCAN, Mean-shift and OPTICS belong to this type of clustering.

- **Grid-based clustering**. For multi-dimensional datasets, a grid is created and the data is divided amongst the grid's cells, thereby creating clusters.


## K-Means clustering

El agrupamiento K-medias es un método derivado del dominio del procesamiento de señales. Se usa para dividir y particionar grupos de datos en 'k' grupos usando una serie de observaciones. Cada observación funciona para agrupar un punto de datos más cercano a su 'media' más cercana, o el punto central de un grupo.

Los grupos pueden ser visualizados como [diagramas Voronoi](https://en.wikipedia.org/wiki/Voronoi_diagram), los cuales incluye un punto (o 'semilla') y su región correspondiente.

El proceso de agrupamiento K-medias se ejecuta en un proceso de tres pasos:

1. El algoritmo selecciona el k-número de puntos centrales al hacer muestreo del conjunto de datos. Después de esto, se repite:
    i. Se asigna cada muestra al centroide más cercano.
    ii. Se crean nuevos centroides al tomar el valor medio de todas las muestras asignadas a los centroides previos.
    iii. Luego, se calcula la diferencia entre los centroides nuevos y viejos y se repite hasta que los centroides se estabilizan.

Un inconveniente de usar K-medias incluye el hecho que necesitarás establecer 'k', que es el número de centroides. Afortunadamente el 'elbow method' ayuda a estimar un buen valor inicial para 'k'. Lo probarás en un minuto.




