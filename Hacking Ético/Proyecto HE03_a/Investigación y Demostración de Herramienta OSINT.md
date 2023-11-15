# Parte 1: Investigación y Demostración de Herramienta OSINT
## Índice  
1. [Seleccion de Herramienta](#id1)
2. [Maltego](#id2)
3. [Descarga e instalación](#id3)
4. [Configuración inicial Maltego](#id4)
5. [Referencias](#id5)

## Seleccion de Herramienta<a name="id1"></a>

Tras meditar y examinar varias herramientas, vamos a definir la herramienta Maltego, una herramienta programada en java y propiedad de la empresa Paterva.

Esta herramienta posee una licencia de la comunidad para permitir a los estudiantes su uso gratuito sin fines de lucro.

## Maltego<a name="id2"></a>

Maltego es un software utilizado para la inteligencia de fuentes abiertas y forense, desarrollado por Paterva. El programa se enfoca en proporcionar una biblioteca de transformaciones para el descubrimiento de datos de fuentes abiertas y visualizar esa información en un formato gráfico, adecuado para análisis de enlaces y minería de datos. 

Maltego permite crear entidades personalizadas, lo que le permite representar cualquier tipo de información además de los tipos básicos de entidades que forman parte del software. El enfoque básico de la aplicación es analizar las relaciones del mundo real.

Algunas características clave de Maltego incluyen:

1. **Interfaz gráfica:**  Maltego utiliza una interfaz gráfica fácil de usar que permite a los usuarios crear visualizaciones de datos interconectadas. Esto facilita la comprensión de las relaciones entre diferentes entidades.
2. **Fuentes de datos:** Maltego puede conectarse a diversas fuentes de datos, como motores de búsqueda en la web, bases de datos públicas, redes sociales, y más. Esto permite a los usuarios reunir información de múltiples fuentes en un solo lugar.
3. **Transformaciones:** Maltego utiliza transformaciones para procesar y analizar datos. Las transformaciones son scripts que extraen información de las fuentes de datos y la presentan de manera visual en el gráfico.
4. **Personalización:** Los usuarios pueden crear transformaciones personalizadas para adaptarse a sus necesidades específicas de investigación. Esto permite extender la funcionalidad de Maltego según los requisitos del usuario.
5. **Colaboración:** Maltego permite a los usuarios compartir y colaborar en sus investigaciones. Esto es útil en entornos donde varios analistas trabajan en el mismo caso o proyecto.
6. **Ediciones:** Maltego se ofrece en varias ediciones, incluyendo una versión gratuita llamada Maltego CE (Community Edition) y versiones comerciales con funcionalidades más avanzadas.

## Descarga e instalación<a name="id3"></a>
Vamos a la página de la aplicación [Maltego](https://www.maltego.com), una vez allí, en el menú superior, seleccionamos la pestaña “product” y clicamos en “Download Maltego”, elegimos la versión y la instalamos en nuestro equipo.

![prueba](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.001.png)

La instalación es bastante simple, solo debemos elegir si será usada por nosotros o por cualquiera que use este equipo, a parte de la ruta en la que queremos que se instale.

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.002.png)

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.003.png)

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.004.png)

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.005.png)

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.006.png)

## Configuración inicial Maltego<a name="id4"></a>
Una vez arrancado el programa, la primera pantalla que nos saldrá será para seleccionar el tipo de producto de Maltego, nosotros, como vamos a usar la licencia gratuita, vamos a seleccionar la versión CE, que, aunque está limitada, nos permite ver como funciona la herramienta con los módulos de aplicaciones.

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.007.png)

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.008.png)

Debemos estar logueados para poder usar la aplicación, si aún no lo estamos, nos trae un enlace directamente al registro, sin tener que buscar en la web donde debemos hacerlo. 

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.009.png)

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.010.png)

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.011.png)

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.012.png)

Este penúltimo paso (7) de configuración de Maltego nos parece muy interesante, ya que, si lo quieres utilizar para investigación, ya que tiene un modo de privacidad, en el que no obtendrá ningún dato directamente desde internet y se bloquearán las descargas de imágenes. 

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.013.png)

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.014.png)

Una vez dentro del programa podemos agregar los mods que veamos oportunos para nuestra labor, para ello vamos al menú superior, a la pestaña de Windows y vamos a Home. Desde aquí solo debemos buscar el que necesitemos e instalarlo. Algunos ejemplos de módulos que podemos encontrar son Shodan, WaybackMachine y WhoisXML entre otros.

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.015.png)

![](img/Aspose.Words.1faf0c9e-02ad-4db6-b73a-8ea5766580e2.016.png)


## Referencias <a name="id5"></a>
[Pagina oficial de Maltego](https://www.maltego.com/)  
[Tutorial - Como Usar Maltego](https://www.youtube.com/watch?v=Ph_KmKY1yEM&ab_channel=TheGoodHacker)  
[Wikipedia - Maltego](https://es.wikipedia.org/wiki/Maltego)  
[Maltego: herramienta que muestra qué tan expuesta está tu información](https://www.welivesecurity.com/la-es/2023/05/11/maltego-herramienta-muestra-tan-expuesto-estas-internet/)  
[Descripción de Maltego por la UCM](https://www.ucm.es/pimcd2014-free-software/maltego)  
[Reconocimiento con Maltego](https://www.youtube.com/watch?v=TLdjUPjfhxY)  

