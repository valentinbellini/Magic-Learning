## Regression models

 - [Diabetes Dataset](./1.testing-diabetes-dataset.ipynb) : Get started with Python and Scikit-learn for regression models
 - [Cleaning Data](./2.cleaning-data.ipynb) : Visualize and clean data in preparation for ML
 - [Linear and Polynomial Regression](./3.linear-and-polynomial.ipynb) : Build linear and polynomial regression models	
 - [Logistic regression to predict categories](./4.logistic-regression.ipynb)
 - [Country predictor base on ufos.csv](./5.Ofnis.ipynb)

## Que és la regresión

La regresión busca encontrar la relación funcional entre las variables independientes (input) y la variable dependiente (output). Esta relación se representa típicamente como una función matemática. En términos simples, la regresión intenta ajustar una línea (o curva) que mejor se ajuste a los datos observados.

La regresión se utiliza cuando queremos predecir valores numéricos. Algunos ejemplos de aplicación incluyen predecir precios de viviendas basados en características como el tamaño, el número de habitaciones, etc., predecir el rendimiento de un estudiante en un examen basado en el tiempo de estudio, edad, etc., o predecir la temperatura basada en variables como la humedad, la presión atmosférica, etc.

## Diferencia con clasificación y clustering:
- Clasificación: En la clasificación, el objetivo es predecir una etiqueta o clase discreta. Por ejemplo, predecir si un correo electrónico es spam o no spam, o si una imagen contiene un perro, un gato o un pájaro.
- Clustering: En el clustering, el objetivo es agrupar un conjunto de datos en grupos o clústeres basados en similitudes. A diferencia de la regresión, no hay una variable objetivo específica que se esté prediciendo, sino que el objetivo es descubrir estructuras intrínsecas en los datos.

## Tipos de regresiones:
- *Regresión lineal*: Busca ajustar una línea recta que mejor se ajuste a los datos.
- *Regresión polinómica*: Utiliza una función polinómica para ajustarse a los datos en lugar de una línea recta.
- *Regresión logística*: Se utiliza cuando la variable dependiente es binaria (0/1) y queremos predecir la probabilidad de que ocurra un evento.
- *Regresión Ridge y Lasso*: Métodos de regresión lineal regularizados que ayudan a prevenir el sobreajuste al agregar términos de penalización a la función de pérdida.
- *Regresión de series temporales*: Utilizada cuando los datos tienen una estructura de tiempo y se busca predecir valores futuros.
- *Regresión de vecinos más cercanos (KNN)*: Utiliza los valores de las k observaciones más cercanas para predecir el valor de una nueva observación.

## Cómo se utilizan en scikit-learn:
En scikit-learn, una biblioteca popular de machine learning en Python, la regresión se implementa a través de la clase `LinearRegression` para regresión lineal, `LogisticRegression` para regresión logística y otras clases específicas para diferentes tipos de regresión. Aquí hay un ejemplo simple de cómo usar regresión lineal en scikit-learn:

```python
    from sklearn.model_selection import train_test_split
    from sklearn.linear_model import LinearRegression

    # Suponiendo que tenemos X como nuestras características y y como nuestros objetivos
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

    # Crear un modelo de regresión lineal
    model = LinearRegression()

    # Entrenar el modelo
    model.fit(X_train, y_train)

    # Hacer predicciones
    predictions = model.predict(X_test)

```
