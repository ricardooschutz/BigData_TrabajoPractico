# BigData_TrabajoPractico
#Parte 1 Get the Data
Primeramente se importan las siguientes librerias: 
- from config import *
- import tweepy
- import datetime
- import pandas as pd
- import re
- from wordcloud import WordCloud
- from textblob import TextBlob
  En la primera parte del trabajo se acceden a los tokens para admitir las credenciales y su posterior autenticacion.
Luego se crea un input donde se inserta el tema seleccionado a buscar los hashtaqs de los tweets
A su vez se le consulta al usuario tambien con un input la cantidad de tweets a traer
Luego se muestran los tweets, y luego ya se crea un Data frame con 4 columnas que son:
['Tweet' , 'Autor', 'Fecha', 'Likes', 'Retweets']
Luego se crea un archivo .csv del Data Frame

#Parte 2 Limpieza y  Analisis de Sentimiento los Tweets
Primeramente para el preprocesamiento de analisis de los datos se llevo a cabo la limpieza de los tweets
Para ello se lee el archivo .csv creado anteriormente
En el cual removemos las menciones, los hashtaqs, el RT, y el hyperlink
Tambien se crea una funcion para eliminar los emojis
Luego se imprime el data frame llamado "tweets_list" para chequear que todo esta en orden
Para el analisis de sentimientos de los tweets se utilizo el algoritmo de TextBlob, 
con el se analizaron la polaridad y subjetividad de los tweets
Se crean dos funciones, una para obtener los tweets llamada Subjetividad (qué tan subjetivo  es el texto: una puntuación de 0 es un hecho, y una puntuación de +1 es en gran medida una opinión)
y la otra funcion es para obtener los tweets llamados Polaridad (qué tan positivo o negativo es el texto, -- una puntuación de -1 es la puntuación negativa más alta y una puntuación de +1 es la puntuación positiva más alta). 
Luego se procede al mismo analisis pero creando listas de positivos, neutrales y negativos.
Este analisis nuevo se procede a guardar en el mismo csv: tweets_list.to_csv("Analisis_de_" + hashtag + ".csv")
Luego se eliminan conectores y palabras inutiles, para asi generar una nube de palabras de los tweets analizados. Finalmente se crean tres graficos, un scatter plot con la subjetividad 
y polaridad de los sentimientos analizados para entender que tan variados son los tweets, y otro con la cantidad de los tweets positivos, negativos y neutrales.
Estos mismo analisis se realizan en un grafico de barras y un grafico circular para ver la proporcion de los mismos
