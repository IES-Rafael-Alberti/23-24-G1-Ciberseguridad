# Informe Técnico proyecto 4
# Índice
1. [Resumen Ejecutivo](#resumen)  
    1.1. [Línea temporal](#tiempo)
2. [Introducción](#introduccion)  
    2.1 [Antecedentes](#antecedentes)  
    2.2 [Objetivos](#objetivos)  
    2.3 [Alcance](#alcance)  
3. [Información analizada](#informacion)  
4. [Análisis](#analisis)    
    4.1 [Comparación de hashes](#comparacion)     
    4.2 [Análisis de la memoria](#forense) 
5. [Conclusión](#conclusion) 

# 1. Resumen Ejecutivo<div id='resumen' />

Tras una amenaza de bomba en la escuela, se llevó a cabo un análisis forense del equipo de Francisco José Jiménez, quien había sido señalado como sospechoso. La verificación de hashes confirmó la integridad de la evidencia, y el análisis de la memoria reveló una conversación en la que Francisco José parece admitir haber realizado la llamada para evitar un examen. Esta confesión, junto con otras discusiones encontradas en la memoria, proporciona evidencia concluyente de su participación en el incidente.

## 1.1 Línea Temporal<div id='tiempo' />

![Línea temporal.png](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Informe%20T%C3%A9cnico%20proyecto%204%20f4cc1c561991422cbb5b7277c5568eb1/Amenaza_de_bomba_falsa.png)

# 2. Introducción<div id='introduccion' />

## 2.2 Antecedentes<div id='antecedentes' />

Una escuela recibió una llamada anónima de amenaza de bomba. Se sospecho de un alumno, Francisco José Jiménez, alias Pacopepe de ser el autor de dicha llamada. 

Este usuario, reafirma su inocencia, pero un compañero suyo, Benji, lo incrimina sin prueba alguna.

Esta incoherencia es la que nos lleva a realizar un análisis forense del equipo de Pacopepe.

## 2.3 Objetivos<div id='objetivos' />

El objetivo de este informe técnico es realizar una línea temporal con los eventos encontrados en el equipo de Pacopepe y llegar a comprobar si es el autor de la amenaza de bomba o no.

## 2.4 Alcance<div id='alcance' />

El alcance del análisis forense realizado es toda información que se pueda encontrar en el volcado de memoria del equipo del sospechoso.

# 3. Información analizada<div id='informacion' />

| Adquisición | DESKTOP-01S7HH9-20220408-171552.dmp |
| --- | --- |
| Tamaño (Bytes) | 4294504448 |
| HASH SHA256 | edcdbcac27263a45d6dfe27f6c8baff55952b2357a70031de20de057730cd359 |

# 4. Análisis<div id='analisis' />

Antes de comenzar con el análisis se realizará la comprobación de hashes para verificar que la evidencia no ha sido alterada.

### 4.1 Comparación de hashes<div id='comparacion' />

Verificamos si esta información es correcta o no:

| Criptografía | HASH | Prueba |
| --- | --- | --- |
| SHA256 | edcdbcac27263a45d6dfe27f6c8baff55952b2357a70031de20de057730cd359 | [Ver anexo de imágenes. Imagen 1](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Anexos.md) |

Como se puede apreciar, los hashes coinciden perfectamente con los proporcionados en un inicio.

### 4.2 Análisis de la memoria<div id='forense' />

Una vez realizada la comprobación de los hashes para verificar que coinciden, comenzaremos con el análisis.

Primero que nada, se verificará que el volcado de memoria pertenezca al usuario, para ello utilizaremos la herramienta Volatility.

Esta herramienta nos permite realizar una búsqueda de información dentro de la memoria del equipo.

Debemos realizar la transformación del archivo del volcado de memoria a un formato que dicha herramienta pueda leer. Una vez realizada la transformación al formato adecuado, se puede proceder al análisis completo de la memoria.

[Ver anexo de imágenes. Imagen 2](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Anexos.md)

Utilizando un plugin de la herramienta y mediante el comando “envars”, podremos obtener las variables de entorno del equipo, por la que podremos obtener el nombre del equipo.

[Ver anexo de imágenes. Imagen 3](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Anexos.md)

Después, al realizar un escaneo de los procesos que estaban corriendo en el equipo del sospechoso, podemos encontrar un proceso de aplicación que es utilizado para poder visualizar documentos PDF.

[Ver anexo de imágenes. Imagen 4](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Anexos.md)

Tras, visualizar el proceso del PDF, se parseó entre todos los archivos que hay dentro de la imagen del disco, para ver si hay algún documento de texto creado o en escritura (temporal). Y encontramos un fichero de extensión .odt, como se puede ver en la imagen siguiente:

[Ver anexo de imágenes, Imagen 5](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Anexos.md)

Como podemos apreciar, a demás de encontrar el archivo, también hallamos el ID del proceso por el cual se esta ejecutando, en este caso el LibreOffice:

[Ver anexo de imágenes, Imagen 6](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Anexos.md)

Visualizando en crudo la información de la memoria, se encontró una conversación, entre dos usuarios, Francisco José Jiménez (pakopepe88) y otra persona (marcosheredia666), en la cual podemos observar que hablaban sobre como evadir un examen. 

El presunto sospechoso, parece buscar una excusa para no hacer dicho examen, habla con la otra persona sobre fingir estar malo o “cualquier cosa” (1). También podemos ver que la otra persona lo incita a hacer algo para no hacer el examen (2).

[Ver anexo de imágenes, Imagen 7](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Anexos.md)

Podemos observar distintas conversaciones de ambos sobre coger un tren o sobre videojuegos como Fortnite o Tap Ninja y sobre un trabajo de historia que deberían de realizar.

[Ver anexo de imágenes, Imagen 8](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Anexos.md)

[Ver anexo de imágenes, Imagen 9](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Anexos.md)

Esta conversación empieza con la negación de ambos ha realizar el trabajo de historia (1). Poco después, podemos observar como marcosheredia666 le pregunta a nuestro presunto sospechoso, si ha realizado él la falsa llamada de bomba al centro educativo, en lo que podemos continuar la conversación es que nuestro presunto sospechoso Francisco José  Jiménez contesta afirmativamente que él ha sido el que ha realizado dicha llamada para no tener que realizar el dicho examen.

[Ver anexo de imágenes, Imagen 10](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Anexos.md)

Poco después, podemos ver como ambos hablando sobre que Benji podría chivarse sobre lo ocurrido y una posible amenaza a esta misma persona por parte de Francisco José  Jiménez.

[Ver anexo de imágenes, Imagen 11](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Anexos.md)

# 5. Conclusión<div id='conclusion' />

Basado en el análisis forense informático, se puede concluir que hay evidencia sólida de actividad sospechosa por parte del usuario Francisco José Jiménez. La información recuperada de la memoria del equipo sugiere que Jiménez estaba buscando formas de evadir un examen y que incluso pudo realizar una falsa llamada de bomba para lograr este objetivo. Además, existe una preocupación sobre un tercero, “Benji”, que podría revelar la verdad.


