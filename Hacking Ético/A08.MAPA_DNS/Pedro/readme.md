# Information Gathering Elpozo

En esta practica usaremos herramientas para obtener información de forma pasiva sobre la empresa el pozo.

# Información WHOIS

Domain Name: [ELPOZO.COM](http://elpozo.com/)  
Registry Domain ID: 1181800_DOMAIN_COM-VRSN  
Registrar WHOIS Server: [https://www.arsys.es/dominios/whois](https://www.arsys.es/dominios/whois)  
Registrar URL: [http://www.arsys.es](http://www.arsys.es/)  
Updated Date: 2023-05-19T09:34:34Z  
Creation Date: 1997-05-23T04:00:00Z  
Registry Expiry Date: 2024-05-24T04:00:00Z  

## Direcciones IP

Usando la herramienta nslookup obtenemos la dirección ip de el pozo:

![Untitled](Information%20Gathering%20Elpozo%20f1fb73f42f3c48a884659e736fbea498/Untitled.png)

## Datos de contacto y emails

Registrar: Arsys Internet, S.L. dba [NICLINE.COM](http://nicline.com/)  
Registrar IANA ID: 379  
Registrar Abuse Contact Email: [abuse@nicline.com](mailto:abuse@nicline.com)  
Registrar Abuse Contact Phone: +34 941 620 100  

# Servidores DNS

A través de la herramienta online [dnsdumpster.com](http://dnsdumpster.com) obtendremos los servidores dns de la empresa junto a su IP.

![Untitled](Information%20Gathering%20Elpozo%20f1fb73f42f3c48a884659e736fbea498/Untitled%201.png)

# Servidores de Correo

Usando el comando dig [elpozo.com](http://elpozo.com) MX sacamos los servidores de correo que posee la empresa:

[elpozo-com.mail.protection.outlook.com](http://elpozo-com.mail.protection.outlook.com/).

![Untitled](Information%20Gathering%20Elpozo%20f1fb73f42f3c48a884659e736fbea498/Untitled%202.png)

# Subdominios

Volviendo a utilizar la herramienta [dnsdumpster.com](http://dnsdumpster.com) sacaremos los subdominios de elpozo.com:

![Untitled](Information%20Gathering%20Elpozo%20f1fb73f42f3c48a884659e736fbea498/Untitled%203.png)

![Untitled](Information%20Gathering%20Elpozo%20f1fb73f42f3c48a884659e736fbea498/Untitled%204.png)

# Información Adicional

Aqui pondremos información que podemos considerar interesante para la investigación.

## Registro TXT

Con la herramienta dig sacamos el registro txt de los servidores de dominio de la empresa:

![Untitled](Information%20Gathering%20Elpozo%20f1fb73f42f3c48a884659e736fbea498/Untitled%205.png)

## URLs Interesantes

Usando theharvester podemos encontrar información valiosa que no muestra otras herramientas como Urls que pueden ser interesantes de visitar para comprobar si hay algo:

![Untitled](Information%20Gathering%20Elpozo%20f1fb73f42f3c48a884659e736fbea498/Untitled%206.png)

## Correos

Esta herramienta ya mencionada en el anterior apartado, tambien nos proporciona direcciones de correo que posean en nombre de la empresa:

![Untitled](Information%20Gathering%20Elpozo%20f1fb73f42f3c48a884659e736fbea498/Untitled%207.png)

# Herramientas

Instaladas ya en Kali: 

- Dig
- TheHarvester
- Nslookup
- Whois

Herramientas de navegador:

[DNSdumpster](https://dnsdumpster.com/)
