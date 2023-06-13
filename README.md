[![](https://imagenes.cronica.com.mx/files/image_948_465/uploads/2022/08/03/62ea8b0551d18.jpeg)](http://https://imagenes.cronica.com.mx/files/image_948_465/uploads/2022/08/03/62ea8b0551d18.jpeg)

### MACHINE LEARNING OPERATIONS
###### por Nancy Contreras, estudiante dela carrera Data Science en [Soy Henry](http://https://www.soyhenry.com/?utm_source=google&utm_medium=cpc&utm_campaign=GADS_SEARCH_MEX_BRAND&utm_content=Brand&gad=1&gclid=CjwKCAjwhJukBhBPEiwAniIcNbyXF-NP0qG0EJV5DpncHdjQf96v7MGxR_PIr85AXQ8CoHTHIGx78RoC89AQAvD_BwE "Soy Henry")


### **Introducción**
Hola! Este proyecto tiene por objetivo, entrenar un modelo que recomiende una serie de películas, a raíz de la selección de una. Para ello, se ocupó una base de datos y después de realizar un análisis completo de los mismos se instanció el modelo en una API, terminando con un despliegue en la web. 

------------
# Recorrido por el proyecto

 -Archivos Originales para la primera parte del proyecto se encuentran en el siguiente [Link](http://https://drive.google.com/drive/u/2/folders/10KkqiXHJZrBWVzQQxyXmqhUQRT7EQvPw "Link")

## -> TRANSFORMACIÓN DE LA BASE DE DATOS
- Carga de datos en Python :tw-1f40d: por medio de la biblioteca pandas :tw-1f43c:
- Para poder acceder a los datos, algunas columnas se tuvieron que desanidar
- Se revisaron campos nulos, algunos se eliminaron y otros se remplazaron por 0
- Las fechas, debían tener este formato AAAA-mm-dd
- Se agregó una columna correspondiente al año de estreno de la película y una columna compuesta de dos columnas asociadas entre sí, dando cómo resultado la columna 'return'
- Por último, se eliminaron columnas innecesarias

Esta parte de primeras transformaciones a los datos, lo encuentras en el siguiente link: (https://github.com/NancyData/PI_ML_01/blob/main/Tratamiento_Datos.ipynb)

## -> DESARROLLO API
En un entorno virtual en Python :tw-1f40d: se crearon 6 funciones para los endpoints que se consumirán en la API, se disponibilizaron los datos usando el framework **FastAPI**

Las funciones fueron las siguientes:
1. *def cantidad_de_filmaciones_mes(mes) *-> Al ingresar un mes en español, con minúsculas y escrito sin abreviaturas, retorna: La cantidad de películas estrenadas dicho mes.
2. *def cantidad_de_filmaciones_dia(dia) *-> Al ingresar un día en español, con minúsculas y escrito sin abreviaturas, retorna: La cantidad de películas estrenadas dicho día.
3. *def score_titulo(titulo_de_la_filmacion) *-> Al ingresar el título de una filmación, retorna: El año de estreno y su popularidad
4. *def votos_titulo(titulo_de_la_filmacion) *-> Al ingresar el título de una filmación, retorna: El año de estreno, el conteo de votos que tiene, así cómo el valor promedio recibido, con la condicional que la suma de votos debe ser mayor a 2000, sino, retorna un mensaje indicando que no cumple con las condiciones para retornar la información anterior
5. *def get_actor(nombre_actor) *-> Al ingresar el nombre de un actor, retorna: la cantidad de filmaciones en las que ha participado, el retorno total y el retorno promedio
6. *def get_director(nombre_director) *-> Al ingresar el nombre de un director, retorna: su éxito medido por la suma del retorno, la cantidad de filmaciones que ha dirigido y una lista de dichas películas, en las que puedes encontrar datos cómo: el año de estreno, su retorno individual, presupuesto y ganancia de la misma.

Esta parte de la creación de la API para la codificación de las consultas, lo encuentras en el archivo main.py (este archivo se carga con el dataset ya transformado que encuentras en el siguiente link: (https://github.com/NancyData/PI_ML_01/blob/main/main.py)


**nota** Para utilizar el entorno virtual en Python, se debe primero instalar virtualenv, seguido del siguiente código de activación (WINDOWS):

`pip install virtualenv`

`python -m venv nombre_de_tu_env`

`nombre_de_tu_env\Scripts\activate`

`pip install fastapi`

`pip install uvicorn`

`deactivate` #para desactivar el entorno virtual

`uvicorn main:app --reload` #para levantar el servidor


## -> DEPLOYMENT
El desplegado se hizo en la plataforma de *RENDER* al que se puede acceder através del siguientes link: 
`<link>`  https://myfirstproject-8zpx.onrender.com

## -> ANÁLISIS EXPLORATORIO DE LOS DATOS
Se realizó un análisis más profundo, examinando cada coumna que conformaba el dataset que surgio de la primera transformación, se tomaron decisiones de acuerdo a la experiencia personal, y con base a resultados de la búsqueda de outliers, todo enfocado a obtener el dataset óptimo para la parte del modelado de datos

El archivo correspondiente a este análisis, lo encuentras en el siguiente link: Puedes ver el video con el proyecto deployado en el siguiente enlace: [LINK]('Eda_Modelo.ipynb')

## -> SISTEMA DE RECOMENDACIÓN
Una vez con el dataset listo, con la columna de tags creada, previamente lematizada con la ayuda de la librería *Scikit-learn*, la cuál se debe de descargar previamente con el siguiente código (Windows): 

`pip install -U scikit-learn`

Se procedió al entrenamiento del modelo, para ello, primero se vectorizó con *TfidfVectorizer* y se obtuvo el valor escalar con *linear_kernel*.

Una vez entrenado el modelo se importó la librería joblib, para guardar el algoritmo en una archivo **.pkl** e implementarse en la API ya creada y desplegada, para que por medio de la siguiente función, retornar 5 películas recomendadas de acuerdo a tu primera elección.

* *def recomendacion(titulo) *-> Al ingresar un título de una filmación, te recomienda una lista de similares

El archivo correspondiente al código para el sistema de recomendación, lo encuentras en el mismo archivo que el link anterior :tw-1f446:

------------

### ABRE Y EJECUTA LOS ARCHIVOS

------------

Puedes ver el video con el proyecto deployado en el siguiente enlace:

## [VIDEO YOUTUBE](http://https://youtu.be/LPoPV5E88LY)

`<link>` https://youtu.be/LPoPV5E88LY
