# Proyecto 03b: Investigación pasiva
## Índice  
1. [Empresa seleccionada: Razorpay](#id1)
2. [WHois y Nslookup](#id2)
3. [TheHarvester](#id3)
4. [Referencias](#id4)

## Empresa seleccionada: Razorpay<a name="id1"></a>

Primeramente, hemos buscado información de la empresa, de cúal es su origen como tal. Su origen fue en India, el cúal dos personas llamadas Kumar ([Linkedin](https://in.linkedin.com/in/kumarshashank?trk=org-employees)) y Mathur ([CEO de la Empresa](https://in.linkedin.com/in/harshilmathur)) crearon  la plataforma. Sin embargo, vieron que era un problema el pago online, así que hicieron la plataforma a base de pago sencillo para empresas emergentes.

Hemos incluso podido encontrar el twitter de los creadores, los cuales uno de ellos, es el CEO y otro el director:

*[Director de Razorpay](https://twitter.com/shashank_kr)
*[CEO de Razorpay](https://twitter.com/harshilmathur?lang=es)

Actualmente tiene un total de 3000 personas trabajando en ella, su sede se encuentra en Bangalore, Karnataka.

También hemos podido encontrar, su Github, el cúal tiene un total de 161 proyectos, donde cualquier persona puede cogerlo y modificarlo, para su uso de estudio o mejoras. Se encuentra en:  https://opensource.razorpay.com/

Razopay participó en Hacktoberfest de 2023, el cual hizo que desarrolladores de todo el mundo hicieran contribuciones a sus repositorios de código abierto. Toda persona que realizó una o más contribuciones recibió obsequios especiales.

Razorpay se empezó a globalizar recientemente, pero por ahora no se puede realizar pago en algunas partes del mundo, debido a que algunas divisas no se encuentran disponibles.

Actualmente, Razorpay está buscando empleados en la zona de Malasia e India. Esto se puede ver en su propio Linkedln: [Linkedin Razorpay](https://www.linkedin.com/company/razorpay/?originalSubdomain=es)

Tiene Razorpay varias empresas asociadas a su alrededor, como son el caso de:

![](img/paginasasociadas.png)

El director senior de la empresa es Rizawanul Haque ([Linkedin](https://in.linkedin.com/in/rizwanul-haque-736236)).

## Whois y Nslooup <a name="id2"></a>

### Whois

Después de hacer la investigación a través de las redes sociales e internet, procedimos a realizar un escaneo de sus redes a través de whois y nslookup. A través del comando whois; haciendo previamente un export con la página web de razorpay, pudimos sacar mucha información de la propia página:

![](img/whois.png)

Pudimos encontrar el ID de registro de dominio, su nombre de dominio, de cual servidor de whois viene la información y cuando fue actualizada la última vez, junto con los nombres de servidores.

*![](img/whois2.png)

También podemos notar que hay información que está prohibida, como el estatus del dominio. Pero eso no impide que exista otra información, como la localización actual de la organización, que está situada en París, Francia, junto con números de contacto y fax para poder contactarnos con ellos. Sin embargo, el email de registro parece que está encriptado.

![](img/whois3.png)

También se ha proporcionado el nombre del Administrador. con información de donde vive, en este caso Palo Alto, California, en Estados Unidos, email y teléfonos de contacto. También es el técnico encargado, con datos similares sobre la persona.

![](img/whois4.png)

### NSlookup

Luego de hacer el whois, y sacar toda la información acerca de la propia página, se procedió a hacer uso de la herramienta nslookup para averiguar más información acerca de la propia página.

![](img/exportnslookup.png)

Como se puede comprobar, está más protegida la página con respecto a la averiguación de datos, pero aún así, se obtienen diversas direcciones IP que se pueden consultar en mayor profundidad.

![](img/nslookup2.png)
![](img/nslookup3.png)
![](img/nslookup4.png)
![](img/nslookup5.png)

Como se puede comprobar, obtenemos en la respuesta no autorizada, un nombre, mientras que se pueden encontrar en cierta medida respuestas autorizadas de las páginas amazonaws.com, amazonaws.org, y pdns1.ultradns.net.

Luego de eso, se procede a intentar obtener todos los registros posibles:

![](img/nslookup6.png)
![](img/nslookup7.png)
![](img/nslookup8.png)

Como se puede ver, aunque haya respuestas no autorizadas, sigue habiendo mucha información al respecto, como nombres de servidor, un email de contacto, servidores de correo, y numerosos registros de texto.

Después de esto, también usamos dnsrecon para averiguar más información del dominio de razorpay.

![](img/dnsrecon1.png)
![](img/dnsrecon2.png)
![](img/dnsrecon3.png)

Además, hicimos una búsqueda acerca de los certificados de SSL/TLS para intentar averiguar más información, empleando la web [search.censys.io](https://search.censys.io/certificates).

![image](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/assets/146707444/bc028b29-f150-4b07-9e8e-0c11e087fbbe)

Esta web nos muestra una gran lista certificados de subdominios, hay tantos que hemos obviado las demás capturas, pero es tan sencillo como ingresar a la página y buscar el dominio de la web objetivo.

## TheHarvester <a name="id3"></a>

También hemos buscando mediante la herramientas "theHarvester".

![image](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/assets/146707444/93a6c6c5-9b6b-4814-9866-e06865e53c02)

![image](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/assets/146707444/a47391c8-a502-4229-ae37-189f2147f91b)


Como podemos observar, esta herramienta nos ha proporcionado algunos emails que tienen y 33 hosts de dominios que ha encontrado bajo su nombre.

## WappAlyzer

Mediante esta extensión hemos comprobado las tecnologías con las que funciona su página web.

![image](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/assets/146707444/b940f67b-a76c-4e45-ba0b-dc2dc6325521)

![image](https://github.com/IES-Rafael-Alberti/23-24-G1-Ciberseguridad/assets/146707444/5ff0d96d-6fd1-4681-a2ec-acec5954d6a1)

Esta herramienta nos ha proporcionado datos muy especificos, como las herramientas que usa su web y su versión actual.

## Referencias <a name="id4"></a>

- [Página web de Razorpay](https://razorpay.com/)
- [Blog de Razorpay](https://razorpay.com/blog/)
- [Modos de pago de Razorpay](https://razorpay.com/pricing/)
- [Devtools Razorpay](https://razorpay.com/docs/#home-devtools)
- [Twitter Razorpay](https://twitter.com/Razorpay?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)
- [Instagram Razorpay](https://www.instagram.com/razorpay/?hl=es)
- [Linkedin Razorpay](https://www.linkedin.com/company/razorpay/?originalSubdomain=es)
- [Github Razorpay](https://github.com/razorpay)
- [Plugin Razorpay para Wordpress](https://es.wordpress.org/plugins/tags/razorpay/)
- [Payroll software para Starts-up](https://razorpay.com/payroll/)
- [Lista de integraciones Razorpay](https://razorpay.com/integrations/)
- [Vicepresidente de Razorpay Linkedin](https://www.linkedin.com/in/vivek-agarwal-03575711/)
- [Director Senior](https://in.linkedin.com/in/rizwanul-haque-736236?trk=org-employees)
- [Fundador](https://in.linkedin.com/in/kumarshashank?trk=org-employees)
- https://www.marketfeed.com/read/en/the-success-story-of-razorpay
