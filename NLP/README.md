## Primeros pasos con el procesamiento de lenguaje natural

El procesamiento de lenguaje natural (NLP) es la capacidad que tiene un programa de computadora para entender el lenguaje humano como se habla y escribe -- referido como lenguaje natural. Es un componente de la inteligencia artificial (AI). NLP ha existido por más de 50 años y tiene raíces en el campo de la lingüística. Todo el campo está dirigido a ayudar a las máquinas a entender y rpocesar el lenguaje humano. Este luego puede ser usado para realizar tareas como corrección ortográfica o traducción automática. Tiene una variedad de apliciones en el mundo real en un número de campos, incluyendo investigación médica, motores de búsqueda e inteligencia de negocios.

En estas lecciones veremos las bases del NLP al construir pequeños bots de conversación par aprender como el aprendizaje automático ayuda en hacer estas conversaciones más y más 'inteligentes'. Viajaremos tiempo atrás, charlando con Elizabeth Bennett y Mr. Darcy de la novela clásica de Jane Austen, Orgullo y Prejuico, publicado 1813. Luego, ampliaremos nuestros conocimientos al aprender acerca de análisis de los sentimientos vía reseñas de hoteles en Europa.

### Introducción al NLP

#### Lingüística computacional
La lingüística computacional es una área de la investigación y desarrollo que por varias décadas ha estudiado cómo pueden trabajar las computadoras e incluso entender, traducir y comunicar con idiomas. El procesamiento del lenguaje natural es un campo relacionado que se enfoca en cómo las computadoras pueden procesar el lenguaje 'natural' o humano.

**Ejemplo - dictado telefónico**: Si alguna vez has dictado a tu teléfono en lugar de escribir o hacerle una pregunta al asistente virtual, tu voz se convirtió a texto y luego fue procesada o parseada desde el idioma que hablaste. Las palabras clave detectadas fueron procesadas en un formato que el teléfono o asistente pueda entender y actuar.

### ¿Cómo es posible esta tecnología?

Es posible porque alguien escribió un programa de computadora que lo hace. Hace algunas décadas, algunos escritores de ciencia ficción predijeron que la gente hablaría regularmente con sus computadoras, y las computadoras siempre entenderían exactamente lo que éstas quieren. Tristemente, resultó ser un problema más complejo del que se imaginó, y aunque es un problema mejor comprendido ahora, hay desafíos significativos en lograr un 'perfecto' procesamiento del lenguaje natural cuando se trata de entender el significado de una oración. Este es un problema particularmente difícil cuando se trata de entender el humor o detectar las emociones tal como el sarcasmo en una oración.

Si tienes problemas diferenciando entre presente simple y presente continuo, no estás solo. Esto es un algo desafiante para mucha gente, incluso hablantes nativos de un idioma. La buena noticia es que las computadoras son muy buenas aplicando reglas formales, y aprenderás a escribir código que puede parsear una oración tan bien como un humano. El mayor desafío que examinarás más adelante es el entender el significado y sentimiento de una oración.

> Requisito: Descargar la libreria textblolb  (también instala corpora, como se muestra abajo):

```
    pip install -U textblob
    python -m textblob.download_corpora
```

### Hablando con las máquinas
La historia de intentar hacer que las computadoras comprendan el lenguaje humano se remota a décadas atrás, y uno de los primeros científicos en considerar el procesamiento del lenguaje natural fue Alan Turing.

#### La 'prueba de Turing'
Cuando Turing estaba investigando la inteligencia artificial en los años 1950, considero que si una prueba conversacional pudiera ser proporcionada a un humano y una computadora (a través de correspondencia mecanografiada) donde el humano en la conversación no estuviese seguro si estuviesen conversando con otro humano o una computadora.

Si, después de cierto tiempo de conversación, el humano no pudiese determinar si las respuestas provinieron de una computadora o no, entonces pudiese decirse que la computadora estaba pensando?

### Ejercicio - Programar un bot conversacional básico
Un bot conversacional, como Eliza, es una programa que obtiene entradas del usuario y parece entender y responder inteligentemente. A diferencia de Eliza, nuestro bot no tendrá varias reglas dándole la apariencia de tener una conversación inteligente. En su lugar, nuestro bot tendrá sólo una habilidad, mantener la conversación con respuestas aleatorias que funcionen en casi cualquier conversación trivial.

#### El plan
Tus pasos para construir un bot conversacional:

- Imprime instrucciones asesorando al usuario cómo interactuar con el bot
- Empieza un ciclo
- - Acepta la entrada del usuario
- - Si el usuario pidió salir, entonces sal
- - Procesa la entrada del usuario y determina la respuesta (en este caso, la respuesta es una elección aleatoria de una lista de posibles respuestas genéricas)
- - Imprime la respuesta
- Vuelve al paso 2

[BOT](./1.Introduction-to-NLPM.py)


## Tareas y técnicas comunes del procesamiento del lenguaje natural
Para la mayoría de tareas de procesamiento del lenguaje natural, el texto a ser procesado debe ser partido en bloques, examinado y los resultados almacenados y tener referencias cruzadas con reglas y conjuntos de datos. Esta tareas, le permiten al programador obtener el significado, intención o sólo la frecuencia de los términos y palabras en un texto.

## Tareas comunes al procesamiento del lenguaje natural

Existen distintas forma de analizar un texto en el cual trabajas. Hay tareas que puedes realizar y a través de estas tareas eres capaz de estimar la comprensión del texto y sacar conclusiones. Usualmente llevas a cabo estas tareas en secuencia.

### Tokenización

Probablemente la primer cosa que la mayoría de los algoritmos tiene que hacer es dividir el texto en `tokens`, o palabras. Aunque esto suena simple, teniendo en cuenta la puntuación y distintas palabras y delimitadoras de oraciones en los diferentes idiomas puede hacerlo difícil. Puede que tengas que usar varios métodos para determinar la separación.

### Incrustaciones

[Las incrustaciones de palabras](https://en.wikipedia.org/wiki/Word_embedding) son una forma de convertir numéricamente tus datos de texto. Las incrustaciones se realizan de tal forma que las palabras con significado similar o palabras que se usan juntas son agrupadas.

> ✅ Prueba [esta herramienta interesante](https://projector.tensorflow.org/) para experimentar con palabras embebidas. Dando cic en una palabra se muestran grupos de palabras similares: `toy` se agrupa con `disney`, `lego`, `playstation`, y `console`.

### Parseo y etiquetado de parte del discurso

Cada palabra que ha sido tokenizada puede ser etiquetada como parte de un discurso - un sustantivo, verbo o adjetivo. La oración `the quick red fox jumped over the lazy brown dog` puede ser etiquetada como parte del discurso como fox = noun, jumped = verb.

El parseo es reconocer qué palabras están relacionadas con otras en una oración - por ejemplo `the quick red fox jumped` es una secuencia adjetivo-sustantivo-verbo que está separada de la secuencia `lazy brown dog`.

### Frecuencias de palabras y frases

Un procedimiento útil cuando analizas un gran bloque de texto es construir un diccionario de cada palabra o frase de interés y qué tan frecuente aparece. La frase `the quick red fox jumped over the lazy brown dog` tiene una frecuencia de palabra de 2 para `the`.

### N-gramas

Un texto puede ser dividido en secuencias de palabras de una longitud definida, una palabra simple (unigrama), dos palabras (bigramas), tres palabras (trigramas) o cualquier número de palabras (n-gramas).

Por ejemplo `the quick red fox jumped over the lazy brown dog` con un n-grama de puntaje 2 produce los siguientes n-gramas:

1. the quick
2. quick red
3. red fox
4. fox jumped
5. jumped over
6. over the
7. the lazy
8. lazy brown
9. brown dog

### Extracción de frases nominales
En la mayoría de las oraciones, hay un sustantivo que es el sujeto u objeto de la oración. En Inglés, se suele identificar como al tener 'a', 'an' o 'the' precediéndole. Identificar el sujeto u objeto de una oración al 'extraer la frase nominal' es una tarea común del procesamiento del lenguaje natural al intentar comprender el significado de una oración.

En la oración `the quick red fox jumped over the lazy brown dog` hay 2 frases nominales: `quick red fox` y `lazy brown dog`.

### Análisis de sentimiento

Una oración o texto puede ser analizado por sentimiento, o que tan positivo o negativo es. El sentimiento se mide en polaridad y objetividad/subjetividad. La polaridad se mide de -1.0 a 1.0 (negativo a positivo) y 0.0 a 1.0 (de más objetivo a más subjetivo).

### Inflexión

La inflexión te permite tomar una palabra y obtener el singular o plural de la misma.

### Lematización

Un lema es la raíz o palabra principal para un conjunto de palabras, por ejemplo flew, flies, flying tiene como lema el verbo fly.

También hay bases de datos útiles para el investigador del procesamiento del lenguaje natural, notablemente:
[WordNet](https://wordnet.princeton.edu/) es una base de datos de palabras, sinónimos antónimos y muchos otros detalles para cada palabra en distintos idiomas. Es increíblemente útil al intentar construir traducciones, correctores ortográficos, o herramientas de idioma de cualquier tipo.

## Bibliotecas NLP

Afortunadamente, no tienes que construir todas estas técnicas por ti mismo, ya que existen excelentes bibliotecas Python disponibles que hacen mucho más accesible a los desarrolladores que no están especializados en el procesamiento de lenguaje natural o aprendizaje automático. Las siguientes lecciones incluyen más ejemplos de estos, pero aquí aprenderás algunos ejemplos útiles para ayudarte con las siguientes tareas.


## Referencia

- Lecciones escritas por [Stephen Howell](https://www.linkedin.com/in/stephenrichardhowell/)
- Quick start de [TextBlob](https://textblob.readthedocs.io/en/dev/quickstart.html#quickstart)  