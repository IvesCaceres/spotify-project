
# Análisis musical (Most Streamed Spotify Songs 2023)

Este proyecto se centra en examinar y comprender las tendencias, patrones y características de las canciones más reproducidas en la plataforma de transmisión de música Spotify durante el año 2023. El objetivo principal es proporcionar información detallada sobre qué canciones, artistas, géneros y características musicales dominaron el panorama musical durante ese período.


## Conclusiones
Comenzamos con el top de artistas con mas canciones presentes en los streams de spotify

![top_artist](https://github.com/IvesCaceres/spotify-project/blob/main/Files/top%20artist.jpg?raw=true)

Tambien las canciones mas escuchadas en la siguiente imagen:

![top_tracks](https://github.com/IvesCaceres/spotify-project/blob/main/Files/top%20songs.jpg?raw=true)

Posteriormente, se llevó a cabo un análisis de los diversos aspectos relacionados con la musicalidad de las canciones más escuchadas que se encontraban en la base de datos. Estos aspectos incluyen el tempo (BPM), la capacidad de baile (danceability), la energía, la positividad emocional (valence), el nivel de acústica, y la presencia de discurso (speechiness).
![distribution](https://github.com/IvesCaceres/spotify-project/blob/main/Files/plots%20distribution.png?raw=true)

En los gráficos de caja y bigote, se destacan elementos clave como la mediana, los cuartiles, los valores atípicos y la distribución general de los datos. En esta visualización, se observa que los tempos más populares varían entre 100 y 140 BPM. Respecto a la danzabilidad, se aprecia una tendencia hacia canciones más bailables, con una mediana posicionada en el 70%. En cuanto a la energía de las canciones, también se percibe una inclinación hacia aquellas con mayor energía, con valores que oscilan entre el 50% y el 75%.

El análisis de la positividad emocional revela una distribución relativamente equilibrada, con un promedio centralizado en el 50%. Además, se evidencia una clara preferencia por las canciones acústicas en la muestra analizada.

Intrumentalness, este valor representa la cantidad de voces en la canción, en este caso la mayor cantidad de insidencias fueron cercanas del 1.0, es decir, más instrumental son las canciónes.

Liveness, este valor describe la probabilidad de que la canción haya sido grabada con una audiencia en vivo, un valor superior a 0,8 proporciona una gran probabilidad de que la pista esté en vivo, lo cual no es el caso, por lo tanto, podemos concluir que hay mayor cantidad de insidencias en musica grabada en estudio" 

El último parámetro, speechiness, indica la presencia de palabras habladas en una pista. Si el nivel de habla supera 0,66, es probable que la canción esté compuesta principalmente por palabras habladas. Una puntuación entre 0,33 y 0,66 sugiere una combinación de música y letra, mientras que una puntuación inferior a 0,33 indica ausencia de discurso. En este contexto, se observa una inclinación hacia canciones con una baja presencia de palabras habladas, lo que refleja una preferencia por la música instrumental.

#### BPM
Se creó un gráfico de BPM con el objetivo de buscar alguna clasificación, dado que la base de datos no incluía un campo que indicara el género musical, como rock, pop, hip hop, etc. Tras realizar la agrupación, se obtuvo un conjunto de datos con una longitud de 120 registros. Dado que esto representaba una parte significativa de la muestra, compuesta por solo 816 datos, se decidió no considerarla. No obstante, se optó por graficar los 20 BPM con mayor tendencia para su revisión.
![bpm](https://github.com/IvesCaceres/spotify-project/blob/main/Files/plot%20bpm%20x%20streams.png?raw=true)   
![bpm](https://github.com/IvesCaceres/spotify-project/blob/main/Files/pie%20bpm.png?raw=true)   

#### Key Mode
Al igual que se intentó agrupar las canciones por su ritmo cardíaco (BPM), se llevó a cabo una agrupación basada en un nuevo campo creado, obtenido a partir de la concatenación entre el campo 'Key' y 'Mode'. De este modo, se logró determinar la tonalidad en la que están escritas las canciones. En este caso, la agrupación resultó en un total de solo 22 combinaciones. Aunque esta clasificación no permite diferenciar entre los diversos géneros musicales, proporciona insights valiosos al evidenciar correlaciones con otros datos que serán explorados más adelante.

A continuación se presenta el gráfico que ilustra la distribución de streams según las diferentes tonalidades musicales. Destaca que la tonalidad predominante es C# Mayor (Do sostenido mayor), que registra la mayor cantidad de streams
![keymode](https://github.com/IvesCaceres/spotify-project/blob/main/Files/streams%20x%20keymode.png?raw=true)

#### Heatmap correlaciones distintas tonalidades

Se realizaron Heatmap de correlación agrupando la información según las tonalidades o campo "key mode" más representativas, con el objetivo de examinar si existían correlaciones sugestivas de regresión. Se observó que en la tonalidad de C# Major, hay una correlación entre los beats por minuto (bpm) y la cantidad de reproducciones (streams). En D Major, se identificó una correlación entre la valencia y la cantidad de reproducciones. En G Major, se encontró una relación entre los bpm y las reproducciones, así como entre la "speechiness" y las reproducciones. Además, en G Major se detectó una correlación entre la "danceability" y las reproducciones, así como entre la "acousticness" y las reproducciones. En contraste, en C# Major y B Minor no se encontraron correlaciones entre las reproducciones y los diferentes campos analizados.
Seria interesante realizar este mismo análisis utilizando un conjunto de datos más amplio o incorporando la clasificación por género musical. De esta manera, podríamos identificar correlaciones más significativas o incluso descartar la noción de su existencia.
![heatmap_keymode](https://github.com/IvesCaceres/spotify-project/blob/main/Files/heatmap%20por%20key.png?raw=true)

#### Heatmap correlacion completo
Se creó un mapa de calor de correlación utilizando todos los datos musicales para investigar la presencia de correlaciones. Sin embargo, no se identificaron resultados significativos que sugirieran una relación entre la cantidad de reproducciones y otros aspectos relacionados con las características musicales
![Heatmap](https://github.com/IvesCaceres/spotify-project/blob/main/Files/heatmap%20all.png?raw=true)

#### Pairplot completo
Para finalizar se realizó un pairplot para evaluar nuevamente las caracteristicas musicales.
![Pairplot](https://github.com/IvesCaceres/spotify-project/blob/main/Files/pairplot.png?raw=true) 

Se logra identificar una relacion lineal entre algunos datos como acousticness y energy, tambien en valence y energy, y en menor medida entre valence y danceability. En el caso de los streams no se observan relaciones lineares.

