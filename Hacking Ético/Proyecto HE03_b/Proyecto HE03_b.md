# Proyecto 03b: Investigación pasiva
## Índice  
1. [Empresa seleccionada: Razorpay](#id1)
2. [Maltego](#id2)
3. [Descarga e instalación](#id3)
4. [Configuración inicial Maltego](#id4)
5. [Referencias](#id5)

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

![Pagina asociada](img/paginas asociadas.png)

El director senior de la empresa es Rizawanul Haque ([Linkedin](https://in.linkedin.com/in/rizwanul-haque-736236)).


Después de hacer la investigación a través de las redes sociales e internet, procedimos a realizar un escaneo de sus redes a través de whois y nslookup. A través del comando whois; haciendo previamente un export con la página web de razorpay, pudimos sacar mucha información de la propia página:

*whois1*

Pudimos encontrar el ID de registro de dominio, su nombre de dominio, de cual servidor de whois viene la información y cuando fue actualizada la última vez, junto con los nombres de servidores.

*whois2*

También podemos notar que hay información que está prohibida, como el estatus del dominio. Pero eso no impide que exista otra información, como la localización actual de la organización, que está situada en París, Francia, junto con números de contacto y fax para poder contactarnos con ellos. Sin embargo, el email de registro parece que está encriptado.

*whois3*

También se ha proporcionado el nombre del Administrador. con información de donde vive, en este caso Palo Alto, California, en Estados Unidos, email y teléfonos de contacto. También es el técnico encargado, con datos similares sobre la persona.

*whois4*

Luego de hacer el whois, y sacar toda la información acerca de la propia página, se procedió a hacer uso de la herramienta nslookup para averiguar más información acerca de la propia página.

*export/nslookup*

Como se puede comprobar, está más protegida la página con respecto a la averiguación de datos, pero aún así, se obtienen diversas direcciones IP que se pueden consultar en mayor profundidad.

*nslookup2*
*nslookup3*
*nslookup4*
*nslookup5*

Como se puede comprobar, obtenemos en la respuesta no autorizada, un nombre, mientras que se pueden encontrar en cierta medida respuestas autorizadas de las páginas amazonaws.com, amazonaws.org, y pdns1.ultradns.net.

Luego de eso, se procede a intentar obtener todos los registros posibles:

*nslookup6*
*nslookup7*
*nslookup8*

Como se puede ver, aunque haya respuestas no autorizadas, sigue habiendo mucha información al respecto, como nombres de servidor, un email de contacto, servidores de correo, y numerosos registros de texto.

Después de esto, también usamos dnsrecon para averiguar más información del dominio de razorpay.

*dnsrecon1*
*dnsrecon2*
*dnsrecon3*

Además, hicimos una búsqueda acerca de los certificados de SSL/TLS para intentar averiguar más información, empleando crt.sh.

## Referencias

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
