# Informe Técnico proyecto 4

# 1. Resumen Ejecutivo

El análisis del volcado de memoria ha desvelado una serie de indicios con respecto a la llamada anónima de una amenaza de bomba. Se encontraron una serie de conversaciones de Discord donde se procedió a hablar sobre dicha amenaza.

## 1.1 Línea Temporal

![Amenaza de bomba falsa.png](Informe%20Te%CC%81cnico%20proyecto%204%20f4cc1c561991422cbb5b7277c5568eb1/Amenaza_de_bomba_falsa.png)

# 2. Introducción

## 2.2 Antecedentes

Una escuela recibió una llamada anónima de amenaza de bomba. Se sospecho de un alumno, Francisco José Jiménez, alias Pacopepe de ser el autor de dicha llamada. 

Este usuario, reafirma su inocencia, pero un compañero suyo, Benji, lo incrimina sin prueba alguna.

Esta incoherencia es la que nos lleva a realizar un análisis forense del equipo de Pacopepe.

## 2.3 Objetivos

El objetivo de este informe técnico es realizar una línea temporal con los eventos encontrados en el equipo de Pacopepe y llegar a comprobar si es el autor de la amenaza de bomba o no.

## 2.4 Alcance

El alcance del análisis forense realizado es toda información que se pueda encontrar en el volcado de memoria del equipo del sospechoso.

# 3. Información analizada

| Adquisición | DESKTOP-01S7HH9-20220408-171552.dmp |
| --- | --- |
| Tamaño (Bytes) | 4294504448 |
| HASH SHA256 | edcdbcac27263a45d6dfe27f6c8baff55952b2357a70031de20de057730cd359 |

# 4. Análisis

Antes de comenzar con el análisis se realizará la comprobación de hashes para verificar que la evidencia no ha sido alterada.

### 4.1 Comparación de hashes

Verificamos si esta información es correcta o no:

| Criptografía | HASH | Prueba |
| --- | --- | --- |
| SHA256 | edcdbcac27263a45d6dfe27f6c8baff55952b2357a70031de20de057730cd359 | https://www.notion.so/Informe-T-cnico-proyecto-4-f4cc1c561991422cbb5b7277c5568eb1?pvs=21 |

Como se puede apreciar, los hashes coinciden perfectamente con los proporcionados en un inicio.

### 4.2 Análisis de la memoria

Una vez realizada la comprobación de los hashes para verificar que coinciden, comenzaremos con el análisis.

Primero que nada, se verificará que el volcado de memoria pertenezca al usuario, para ello utilizaremos la herramienta Volatility.

Esta herramienta nos permite realizar una búsqueda de información dentro de la memoria del equipo.

Debemos realizar la transformación del archivo del volcado de memoria a un formato que dicha herramienta pueda leer. Una vez realizada la transformación al formato adecuado, se puede proceder al análisis completo de la memoria.

[(Ver anexo de imágenes. Imagen 2)](https://www.notion.so/Informe-T-cnico-proyecto-4-f4cc1c561991422cbb5b7277c5568eb1?pvs=21)

Utilizando un plugin de la herramienta y mediante el comando “envars”, podremos obtener las variables de entorno del equipo, por la que podremos obtener el nombre del equipo.

[(Ver anexo de imágenes. Imagen 3)](https://www.notion.so/Informe-T-cnico-proyecto-4-f4cc1c561991422cbb5b7277c5568eb1?pvs=21)

Después, al realizar un escaneo de los procesos que estaban corriendo en el equipo del sospechoso, podemos encontrar un proceso de aplicación que es utilizado para poder visualizar documentos PDF.

[(Ver anexo de imágenes. Imagen 4)](https://www.notion.so/Informe-T-cnico-proyecto-4-f4cc1c561991422cbb5b7277c5568eb1?pvs=21)

Tras, visualizar el proceso del PDF, se parseó entre todos los archivos que hay dentro de la imagen del disco, para ver si hay algún documento de texto creado o en escritura (temporal). Y encontramos un fichero de extensión .odt, como se puede ver en la imagen siguiente:

[(Ver anexo de imágenes, Imagen 5)](https://www.notion.so/Informe-T-cnico-proyecto-4-f4cc1c561991422cbb5b7277c5568eb1?pvs=21)

Como podemos apreciar, a demás de encontrar el archivo, también hallamos el ID del proceso por el cual se esta ejecutando, en este caso el LibreOffice:

[(Ver anexo de imágenes, Imagen 6)](https://www.notion.so/Informe-T-cnico-proyecto-4-f4cc1c561991422cbb5b7277c5568eb1?pvs=21)

Visualizando en crudo la información de la memoria, se encontró una conversación, entre dos usuarios, Francisco José Jiménez (pakopepe88) y otra persona (marcosheredia666), en la cual podemos observar que hablaban sobre como evadir un examen. 

El presunto sospechoso, parece buscar una excusa para no hacer dicho examen, habla con la otra persona sobre fingir estar malo o “cualquier cosa” (1). También podemos ver que la otra persona lo incita a hacer algo para no hacer el examen (2).

[(Ver anexo de imágenes, Imagen 7)](https://www.notion.so/Informe-T-cnico-proyecto-4-f4cc1c561991422cbb5b7277c5568eb1?pvs=21)

Podemos observar distintas conversaciones de ambos sobre coger un tren o sobre videojuegos como Fortnite o Tap Ninja y sobre un trabajo de historia que deberían de realizar.

[(Ver anexo de imágenes, Imagen 8)](https://www.notion.so/Informe-T-cnico-proyecto-4-f4cc1c561991422cbb5b7277c5568eb1?pvs=21)

[(Ver anexo de imágenes, Imagen 9)](https://www.notion.so/Informe-T-cnico-proyecto-4-f4cc1c561991422cbb5b7277c5568eb1?pvs=21)

Esta conversación empieza con la negación de ambos ha realizar el trabajo de historia (1). Poco después, podemos observar como marcosheredia666 le pregunta a nuestro presunto sospechoso, si ha realizado él la falsa llamada de bomba al centro educativo, en lo que podemos continuar la conversación es que nuestro presunto sospechoso Francisco José  Jiménez contesta afirmativamente que él ha sido el que ha realizado dicha llamada para no tener que realizar el dicho examen.

[(Ver anexo de imágenes, Imagen 10)](https://www.notion.so/Informe-T-cnico-proyecto-4-f4cc1c561991422cbb5b7277c5568eb1?pvs=21)

Poco después, podemos ver como ambos hablando sobre que Benji podría chivarse sobre lo ocurrido y una posible amenaza a esta misma persona por parte de Francisco José  Jiménez.

[(Ver anexo de imágenes, Imagen 11)](https://www.notion.so/Informe-T-cnico-proyecto-4-f4cc1c561991422cbb5b7277c5568eb1?pvs=21)

# 5. Conclusión

Tras analizar exhaustivamente el disco, podemos decir que ha habido una planificación, a través de una conversación de Discord de notificación al colegio de una presunta amenaza de bomba el cual, se hizo, para evitar hacer un examen ese día. El usuario que hizo esa notificación fue el propio PakoPepe88 y MarcosHeredia66 a través de la conversación con el usuario, admitió lo que hizo.

# 6. Herramientas usadas

Volatility 

| Nombre | Volatility Foundation Volatility Framework |
| --- | --- |
| Versión: | 2.6.1 |
| Página web | https://volatilityfoundation.org/ |

# 7. Anexo

### 7.1 Metodología Utilizada

A continuación, se explica la metodología que ha seguido el perito para adquirir y analizar
las evidencias:

- Adquisición de evidencia digital
1. La captura de la adquisición debe ser lo más precisa posible.
2. Detallar las fechas y horas a la que se realizó la extracción.
3. Intentar no sobrescribir las pruebas instalando software, si no es estrictamente
necesario.
4. Recoger las evidencias en orden de volatilidad:
5. Transparencia: A la hora de realizar la adquisición tendremos que explicar
detalladamente el proceso que hemos seguido para que pueda ser totalmente
reproducible.
- Preservación y almacenamiento de evidencia
A la hora de almacenamiento, se documentará:
- Dónde, cuándo y quién descubrió y recolectó la evidencia.
-  Dónde, cuándo y quién manejó la evidencia.
-  Quién ha custodiado la evidencia, cuánto tiempo y cómo la ha almacenado
-  Si se ha cambiado de custodia indicar a quien, que fecha y hora y comprobar que los
hashes coinciden
-  Dónde almacenarlo. Dependiendo del dispositivo tendremos que almacenarlo de una
u otra forma, por ejemplo, si es un dispositivo portátil tendremos que custodiarlo en
una bolsa de Faraday para que no pueda ser comprometido por las redes móviles.
- Análisis de evidencias

Se llevarán a cabo una serie de procesos y tareas que intentarán dar respuesta a preguntas
relacionadas con una intrusión, como su origen, la lista de sistemas afectados, los métodos
usados, etc. Todos estos procesos y tareas deberán realizarse de forma metódica,
auditable, repetible y defendible.

## 8. Anexo de Imágenes

Imagen 1.

![Hash SHA-256 volcado de memoria Pacopepe](Informe%20Te%CC%81cnico%20proyecto%204%20f4cc1c561991422cbb5b7277c5568eb1/Untitled.png)

Hash SHA-256 volcado de memoria Pacopepe

Imagen 2.

![Proceso con el que el archivo .dmp se transforma a un archivo raw para poder leerse en volatility.](Informe%20Te%CC%81cnico%20proyecto%204%20f4cc1c561991422cbb5b7277c5568eb1/Untitled%201.png)

Proceso con el que el archivo .dmp se transforma a un archivo raw para poder leerse en volatility.

Imagen 3.

![Nombre del equipo Pacopepe](Informe%20Te%CC%81cnico%20proyecto%204%20f4cc1c561991422cbb5b7277c5568eb1/Untitled%202.png)

Nombre del equipo Pacopepe

Imagen 4.

![Proceso de lectura de archivo PDF](Informe%20Te%CC%81cnico%20proyecto%204%20f4cc1c561991422cbb5b7277c5568eb1/Untitled%203.png)

Proceso de lectura de archivo PDF

Imagen 5.

![Archivo en edición](Informe%20Te%CC%81cnico%20proyecto%204%20f4cc1c561991422cbb5b7277c5568eb1/Untitled%204.png)

Archivo en edición

Imagen 6.

![Proceso con el que el archivo .odt esta en ejecución o en escritura](Informe%20Te%CC%81cnico%20proyecto%204%20f4cc1c561991422cbb5b7277c5568eb1/Untitled%205.png)

Proceso con el que el archivo .odt esta en ejecución o en escritura

Imagen 7.

![Conversación Parte 1](Informe%20Te%CC%81cnico%20proyecto%204%20f4cc1c561991422cbb5b7277c5568eb1/Untitled%206.png)

Conversación Parte 1

Imagen 8.

![Conversación Parte 2](Informe%20Te%CC%81cnico%20proyecto%204%20f4cc1c561991422cbb5b7277c5568eb1/3.png)

Conversación Parte 2

Imagen 9.

![Conversación Parte 3](Informe%20Te%CC%81cnico%20proyecto%204%20f4cc1c561991422cbb5b7277c5568eb1/4.png)

Conversación Parte 3

Imagen 10.

![Conversación Parte 4](Informe%20Te%CC%81cnico%20proyecto%204%20f4cc1c561991422cbb5b7277c5568eb1/Untitled%207.png)

Conversación Parte 4

Imagen 11.

![Conversación Parte 5](Informe%20Te%CC%81cnico%20proyecto%204%20f4cc1c561991422cbb5b7277c5568eb1/6.png)

Conversación Parte 5

# 9. Cadena de Custodia

| Registro de la cadena de custodia de la imagen forense |  |  |  |  |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
|  |  |  |  |  |
