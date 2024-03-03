# Introduction to time series forecasting

¿Qué es la predicción de series de tiempo? Se trata de predecir eventos futuros al analizar las tendencias del pasado.

## Tema regional: Uso de la electricidad en el mundo ✨

En estas dos lecciones, se te presentará la predicción de series de tiempo, un área algo menos conocida del aprendizaje automático que sin embargo es extremadamente valiosa para la industria y aplicaciones empresariales, entre otros campos. Mientras las redes neuronales pueden ser usadas para mejorar la utilidad de estos modelos, las estudiaremos en el contexto del aprendizaje automático clásico como modelos que ayudan a predecir el desempeño futuro basado en el pasado.

Nuestro enfoque regional es el uso de la electricidad en el mundo, un conjunto de datos interesante para aprender a predecir el uso de la energía a futuro basado en patrones de cargas pasadas. Puedes ver cómo esta clase de predicción puede ser extremadamente útil en un entorno empresarial.

> El útil plan de estudios de series de tiempo de Penn State puede ser encontrado [aquí](https://online.stat.psu.edu/stat510/lesson/1)

## Introducción
Supón que mantienes un arreglo de parquímetros inteligentes que proveen datos acerca de que tan seguido son usados y con qué duración de tiempo.

> ¿Qué pasaría si pudieras predecir, basado en el rendimiento pasado del medidor, su valor futuro de acuerdo a las leyes de suministro y demanda?

Predecir de forma precisa cuándo actuar para así lograr tu objetivo es una desafío que podría ser abordado con la predicción de series de tiempo.No haría feliz a la gente que le cobraran más en hora pico cuando están buscando un lugar para estacionarse, ¡pero sería una forma segura de generar ingresos para limpiar las calles!

## Algunas definiciones

🎓 **Series de tiempo**

En matemáticas, *"una serie de tiempo es una serie de puntos de datos indexados (o listados o graficados) en orden de tiempo. Más comúnmente, una serie de tiempo es una secuencia tomada en puntos sucesivos igualmente espaciados en el tiempo."* Un ejemplo de una serie de tiempo es el valor diario de cierre de el `Promedio Industrial Down Jones`. El uso de gráficos de series de tiempo y modelado estadístico se encuentra frecuentemente en el procesamiento de señales, predicción del clima, predicción de sismos, y otros campos donde ocurren eventos y los puntos de datos pueden ser graficados en el tiempo.

🎓 **Análisis de series de tiempo**

El análisis de series de tiempo, es el análisis de los datos de las series de tiempo previamente mencionadas. Los datos de las series de tiempo pueden tomar distintas formas, incluyendo `series de tiempo interrumpidas` las cuales detectan patrones en la evolución de las series de tiempo antes y después de un evento de interrupción. El tipo de análisis necesario para las series de tiempo depende de la naturaleza de los datos. Los datos de series de tiempo en sí mismos pueden tomar la forma de series de números o caracteres.

El análisis a realizar, usa una variedad de métodos, incluyendo dominio de frecuencia y dominio de tiempo, lineal y no lineal y más.

🎓 **Predicción de series de tiempo**

La predicción de series de tiempo es el uso de un modelo para predecir valores futuros basándose en patrones mostrados por datos previamente recopilados como ocurrieron en el pasado. Mientras es posible usar modelos de regresión para explorar los datos de las series de tiempo, con índices de tiempo como variables x en un plano, dichos datos se analizan mejor usando tipos especiales de modelos.

Los datos de series de timpo son una lista de observaciones ordenadas, a diferencia de los datos que pueden ser analizados por regresión lineal. El más común es `ARIMA`, el cual es un acrónimo que significa "Autoregressive Integrated Moving Average".

Los [modelos ARIMA](https://online.stat.psu.edu/stat510/lesson/1/1.1) *"relacionan el valor presente de una serie de valores pasados y errores de predicción anteriores"*. Estos son más apropiados para el análisis de datos en el dominio de tiempo, donde los datos están se ordenan en el tiempo.

## Características de datos de series de tiempo a considerar

Al mirar datos de series de tiempo, puedes notar que tienen ciertas características que necesitas tomar en consideración y mitigar para entender mejor sus patrones. Si consideras los datos de las series de tiempo como proporcionando potencialmente una 'señal' que quieres analizar, estas características pueden ser interpretadas como 'ruido'. Frecuentemente necesitarás reducir este 'ruido' al compensar algunas de estas características usando ciertas técnicas estadísticas.

Aquí hay algunos conceptos que deberías saber para ser capaz de trabajar con las series de tiempo:

🎓 **Tendencias**: Las tendencias se definen como incrementos y decrementos medibles en el tiempo. En el contexto de las series de tiempo, se trata de cómo usar las tendencias y, si es necesario, eliminarlas.

🎓 **Estacionalidad**: La estacionalidad se define como fluctuaciones periódicas, tales como prisas de vacaciones que pueden afectar las ventas, por ejemplo. [Da un vistazo](https://itl.nist.gov/div898/handbook/pmc/section4/pmc443.htm) a cómo los distintos tipos de gráficos muestran la estacionalidad en los datos.

🎓 **Valores atípicos**: Los valores atípicos están muy lejos de la varianza de datos estándar.

🎓 **Ciclos de largo plazo**: Independiente de la estacionalidad, los datos pueden mostrar un ciclo de largo plazo como un declive que dura más de un año.

🎓 **Varianza constante**: En el tiempo, algunos datos muestran fluctuaciones constantes, tales como el uso de energía por día y noche.

🎓 **Cambios abruptos**: Los datos pueden mostrar un cambio abrupto que puede necesitar mayor análisis. El cierre abrupto de negocios debido al COVID, por ejemplo, causó cambios en los datos.


# Time series forecasting with ARIMA

> [R Tutorial: ARIMA Time Series 101](https://www.youtube.com/watch?v=IUSk-YDau10&feature=youtu.be)

ARIMA models are particularly suited to fit data that shows `non-stationarity`.

## Conceptos generales

Para poder trabajar con ARIMA, hay algunos conceptos que tenemos que saber:

🎓 Estacionariedad. Desde un contexto estadístico, la estacionariedad se refiere a datos cuya distribución no cambia cuando se desplazan en el tiempo. Los datos no estacionarios, entonces, muestran fluctuaciones debido a tendencias que deben transformarse para ser analizadas. La estacionalidad, por ejemplo, puede introducir fluctuaciones en los datos y puede ser eliminada mediante un proceso de `diferenciación estacional`.

🎓 Diferenciación. La diferenciación de datos, nuevamente desde un contexto estadístico, se refiere al proceso de transformar datos no estacionarios para hacerlos estacionarios mediante la eliminación de su tendencia no constante. "La diferenciación elimina los cambios en el nivel de una serie temporal, eliminando la tendencia y la estacionalidad y estabilizando consecuentemente la media de la serie temporal."

## ARIMA in the context of time series

Desglosemos las partes de `ARIMA` para entender mejor cómo nos ayuda a modelar series temporales y hacer predicciones sobre ellas.

**AR - AutoRegressive (Autorregresivo)**. Los modelos autorregresivos, como su nombre lo indica, miran hacia atrás en el tiempo para analizar valores anteriores en tus datos y hacer suposiciones sobre ellos. Estos valores anteriores se llaman `lags`. Un ejemplo sería datos que muestran las ventas mensuales de lápices. El total de ventas de cada mes se consideraría una `variable evolutiva` en el conjunto de datos. Este modelo se construye cuando "la variable evolutiva de interés se regresa sobre sus propios valores de lags (es decir, anteriores)."

**I - Integrated (Integrado)**. A diferencia de los modelos `ARMA` similares, la 'I' en `ARIMA` se refiere a su aspecto integrado. Los datos se `integran` cuando se aplican pasos de diferenciación para eliminar la no estacionariedad.

**MA - Moving Average (Media Móvil)**. El aspecto de media móvil de este modelo se refiere a la variable de salida que se determina observando los valores actuales y pasados de los rezagos.

En resumen: `ARIMA` se utiliza para hacer que un modelo se ajuste lo más posible a la forma especial de los datos de series temporales.

Ahora trabajaremos en [ARIMA-model.ipynb](./2.ARIMA-model.ipynb)