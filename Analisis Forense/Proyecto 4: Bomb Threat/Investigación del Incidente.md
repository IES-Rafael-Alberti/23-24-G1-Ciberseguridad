# Investigación del Incidente
# Índice
1. [Pregunta 1](#pregunta1)  
2. [Pregunta 2](#pregunta2)
3. [Pregunta 3](#pregunta3)
4. [Pregunta 4](#pregunta4)  


## 1. Confirmar si la imagen de memoria pertenece al ordenador del alumno identificado como “DESKTOP-01S7HH9” <div id='pregunta1' />
    
 Con la herramienta Volatility, si utilizamos uno de los plugins que tiene el programa (”envars”), podemos obtener las variables del entorno del equipo y en una de las variables, podemos ver el nombre del equipo:
    
![Nombre del Equipo](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Investigaci%C3%B3n%20del%20Incidente%2065d490a22b7b4425a97ca654433ee409/Untitled_(13).png)
    
Y como vemos en la imagen, es la imagen del ordenador del alumno Francisco José Jiménez o también llamado Pacopepe.
    
## 2. Determinar el PID del proceso de la aplicación utilizada para visualizar documentos PDF y establecer cuál es su proceso padre. <div id='pregunta2' />
    
    
Si examinamos los procesos con el plugin “pstree” o “psscan” o “pslist”, podemos visualizar, los programas que ha habido o que están activos en la máquina, pero vemos un proceso, que es un lector de PDF y es el Acrobat; a través del proceso llamado AcroCEF.exe
    
![Proceso de lectura de archivo PDF ](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Investigaci%C3%B3n%20del%20Incidente%2065d490a22b7b4425a97ca654433ee409/Untitled_(11).png)
    
## 3. A través de los manejadores, identificar qué documento estaba siendo editado por el alumno durante la intervención policial. <div id='pregunta3' />

Para hacer este apartado, podemos ver todos los ficheros que hay en la máquina usando “filescan” en volatility. Debido a que se esta editando, podemos deducir que será un odt (archivo de Office) dado que en el momento de requisamiento estaba editando un archivo, así que si filtramos con odt, podemos ver lo siguiente en los manejadores que puedan llevar los archivos: 

    
![Archivo en edición](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Investigaci%C3%B3n%20del%20Incidente%2065d490a22b7b4425a97ca654433ee409/Untitled.png)
    
Como podemos, ver hay un documento que es odt, y ya si queremos ver el proceso con el cual se esta haciendo, si buscamos el proceso que pone, podemos ver que esta hecho con office, quedando demostrado en el soffice.bin:
    
![Proceso con el que el archivo .odt esta en ejecución o en escritura]([Investigacio%CC%81n%20del%20Incidente%2065d490a22b7b4425a97ca654433ee409/Untitled%201.png](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Investigaci%C3%B3n%20del%20Incidente%2065d490a22b7b4425a97ca654433ee409/Untitled%201.png))
    
## 4. Buscar en el volcado de memoria pruebas que vinculen al usuario del equipo con la realización de la falsa amenaza de bomba. <div id='pregunta4' />
    
    
A través del comando de string “memoria.raw” | grep bomba, se pueden ver los string que tengan bomba y podemos ver muchas menciones a bombas en el resultado:
    
![Conversacion Bomba](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Investigaci%C3%B3n%20del%20Incidente%2065d490a22b7b4425a97ca654433ee409/Untitled%202.png)
    
 Se puede visualizar una conversación entre los dos usuarios, uno de ellos pakopepe88 y el otro marcosheredia666. Si seguimos investigando, podemos ver que hay una conversación de Discord, donde se admite que el aviso de bomba es falso (Se tiene que leer de abajo a arriba), y esperan que nadie se chive, especialmente Benji dado que es mencionado de manera directa como alguien que puede hacerlo:
    
![Conversación parte 1](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Investigaci%C3%B3n%20del%20Incidente%2065d490a22b7b4425a97ca654433ee409/5.png)
    
![Conversación parte 2](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/blob/main/Analisis%20Forense/Proyecto%204%3A%20Bomb%20Threat/Investigaci%C3%B3n%20del%20Incidente%2065d490a22b7b4425a97ca654433ee409/6.png)
