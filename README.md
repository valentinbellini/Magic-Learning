## Introducción al Desarrollo de Modelos de Aprendizaje Automático

### Sobre este Repositorio

Este repositorio es parte de mi ruta personal de aprendizaje en el campo del aprendizaje automático y el análisis de datos. Estoy utilizando estos proyectos como una oportunidad para explorar diferentes técnicas, algoritmos y enfoques en el mundo del ML.

Además, este repositorio forma parte del curso ["Machine Learning for Beginners"](https://github.com/microsoft/ML-For-Beginners) ofrecido por Microsoft. A través de este curso, estoy adquiriendo conocimientos prácticos y teóricos sobre el aprendizaje automático y su aplicación en diversos contextos. Es por esto que muchos de los comentarios y explicaciones de códigos están en inglés.


### Entorno

Para desarrollar código en Python y crear modelos de aprendizaje automático (ML), utilizaré `Jupyter Notebooks`.

Los Notebooks son un entorno interactivo que permite al desarrollador tanto codificar como agregar notas y escribir documentación alrededor del código, lo cual es muy útil para proyectos experimentales o de investigación.

### Bibliotecas

Para estos proyectos, estoy utilizando las siguientes bibliotecas:
- `matplotlib`
- `numpy`
- `pandas`
- `seaborn`
- `scikit-learn`

### Visión General del Modelo de ML

En un nivel alto, el proceso de creación de procesos de aprendizaje automático (ML) consta de varios pasos:

1. **Decidir la pregunta**: La mayoría de los procesos de ML comienzan formulando una pregunta que no puede ser respondida por un programa condicional simple o un motor basado en reglas. Estas preguntas a menudo giran en torno a predicciones basadas en una colección de datos.
   
2. **Recopilar y preparar datos**: Para poder responder tu pregunta, necesitas datos. La calidad y, a veces, la cantidad de tus datos determinarán cuán bien puedes responder tu pregunta inicial. La visualización de datos es un aspecto importante de esta fase. Esta fase también incluye dividir los datos en un grupo de entrenamiento y prueba para construir un modelo.
   
3. **Elegir un método de entrenamiento**: Dependiendo de tu pregunta y la naturaleza de tus datos, debes elegir cómo deseas entrenar un modelo para reflejar mejor tus datos y hacer predicciones precisas contra él. Esta es la parte de tu proceso de ML que requiere experiencia específica y, a menudo, una considerable cantidad de experimentación.
   
4. **Entrenar el modelo**: Utilizando tus datos de entrenamiento, utilizarás varios algoritmos para entrenar un modelo para reconocer patrones en los datos. El modelo puede aprovechar pesos internos que se pueden ajustar para privilegiar ciertas partes de los datos sobre otras para construir un mejor modelo.
   
5. **Evaluar el modelo**: Utilizas datos nunca antes vistos (tus datos de prueba) de tu conjunto recopilado para ver cómo está funcionando el modelo.
   
6. **Ajuste de parámetros**: Basándote en el rendimiento de tu modelo, puedes volver a hacer el proceso utilizando diferentes parámetros, o variables, que controlan el comportamiento de los algoritmos utilizados para entrenar el modelo.
   
7. **Predecir**: Utiliza nuevas entradas para probar la precisión de tu modelo.

#### Características y Objetivo

Una característica es una propiedad medible de tus datos. En muchos conjuntos de datos se expresa como un encabezado de columna como 'fecha', 'tamaño' o 'color'. Tu variable de característica, generalmente representada como `X` en código, representa la variable de entrada que se utilizará para entrenar el modelo.

Un objetivo es lo que estás tratando de predecir. El objetivo generalmente se representa como `y` en el código, representa la respuesta a la pregunta que estás tratando de hacer a tus datos: en diciembre, ¿qué **color** de calabazas será más barato? en San Francisco, ¿qué vecindarios tendrán el mejor **precio** de bienes raíces? A veces, el objetivo también se refiere como atributo de etiqueta.

Antes de entrenar, debes dividir tu conjunto de datos en dos o más partes de tamaño desigual que aún representen bien los datos.

#### División del Conjunto de Datos

- **Entrenamiento**: Esta parte del conjunto de datos se ajusta a tu modelo para entrenarlo. Este conjunto constituye la mayoría del conjunto de datos original.
- **Prueba**: Un conjunto de datos de prueba es un grupo independiente de datos, a menudo recopilado de los datos originales, que utilizas para confirmar el rendimiento del modelo construido.
- **Validación**: Un conjunto de validación es un grupo independiente más pequeño de ejemplos que utilizas para ajustar los hiperparámetros o la arquitectura del modelo para mejorar el modelo. Dependiendo del tamaño de tus datos y la pregunta que estés haciendo, es posible que no necesites construir este tercer conjunto.

#### Construcción de un Modelo

Dependiendo de tu pregunta y la naturaleza de tus datos, elegirás un método para entrenarlo. Al explorar la documentación de [Scikit-learn](https://scikit-learn.org/stable/user_guide.html) - que uso en este repositorio - puedes explorar muchas formas de entrenar un modelo.

### Divisiones de Carpeta en el Repositorio

El repositorio estará organizado en cinco carpetas principales, cada una dedicada a un tipo específico de modelo de aprendizaje automático:
1. Regresión
2. Clasificación
3. Agrupación
4. Procesamiento del Lenguaje Natural (NLP)
5. Series Temporales

Estas carpetas contendrán proyectos específicos relacionados con cada tipo de modelo, junto con documentación y ejemplos de código para guiar el proceso de desarrollo y análisis de datos. Además, se proporcionarán instrucciones para instalar las bibliotecas necesarias y utilizar los cuadernos Jupyter para ejecutar los proyectos.

### Licencia

Este repositorio se distribuye bajo una licencia abierta y libre para todos. Se alienta a los colaboradores y usuarios a contribuir, compartir y aprender juntos en el campo del aprendizaje automático y el análisis de datos.


