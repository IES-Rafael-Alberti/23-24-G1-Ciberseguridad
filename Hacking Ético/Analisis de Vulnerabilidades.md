---
marp: true
title: Analisis de Vulnerabilidades
paginate: true
_class: lead
color: #ffffff
theme: default
backgroundImage: url('https://venngage-wordpress.s3.amazonaws.com/uploads/2018/11/15-Presentation-Background-Examples33.png')
style: |
    section{
      justify-content: flex-start;
      text-align: center;
      align-items: center;
      display: flex;
      font-size: 25px;
    }
---
# 
#
#
# Analisis de Vulnerabilidades

##### Eduardo de Motrico Fedriani
##### Rafael Valverde Cros
##### Pedro Luis Borrego Vargas
##### Adrián Campó Merlo
##### Sergio Guerrero Merlo
---
# CVE-2020-11899

## La pila Treck TCP/IP anterior a 6.0.1.66 tiene una lectura fuera de límites de IPv6.

## Puntuacion -> 5.4

## Explotacion -> Lectura fuera de limites
---
# CVE-2022-42971

## Carga sin restricciones de archivos peligrosos que podría causar la ejecución remota de código cuando el atacante carga un archivo JSP malicioso en Easy UPS de APC en Windows.

![width:300px, height:200px](https://cdn.computerhoy.com/sites/navi.axelspringer.es/public/media/image/2020/02/ransomware-1862491.jpg)

## Puntuacion -> 9.8

## Explotacion -> Carga sin restricciones de archivos de tipo peligroso.
---
# CVE-2023-20805

## En imgsys, existe una posible escritura fuera de límites debido a una verificación de límites faltantes. Esto podría conducir a una escalada local de privilegios con privilegios de ejecución del sistema necesarios.

## Puntuacion -> 6.7

## Explotacion -> Impacto tecnico: modificar la memoria; DoS: Bloqueo, Salir o Reiniciar; Ejecutar código o comandos no autorizados.
---
# CVE-2023-38435

## Conseguir datos por pagina webs con ataque XSS. 

## Puntuacion -> 6.1

## Explotación -> Confidencialidad del control de acceso, Integridad, Confidencialidad, Disponibilidad, Control de Acceso...

![width:300px, height:225px](https://easydmarc.com/blog/wp-content/webp-express/webp-images/doc-root/wp-content/uploads/2022/06/What-is-Cross-site-Scripting-XSS-Attack-and-How-to-Fix-it_-1.jpg.webp)
---
# CVE-2023-38435

## Permitir un recorrido de ruta absoluto porque la función Flask send_file se usa de manera insegura. 

## Puntuación -> 9.3

## Explotacion -> Clase: Recorrido de ruta absoluta. Gracias a la función Flask send_file un archivo cargado en orchest nos puede dar acceso a la ruta raiz.
---
# CVE-2022-24877

##  Permite a un atacante exponer datos confidenciales del sistema de archivos pod del controlador de la solución Flux para Kubernetes. 

## Puntuacion -> 8.8

![width:300px, height:175px](https://blog.ehcgroup.io/wp-content/uploads/2020/03/screenshot.1005.jpg?v=1585670179)

## Explotación -> A través de un fichero .yaml malicioso permite al atacante una escalada de privilegios en implementaciones de múltiples inquilinos..
---
# CVE-2022-31503

## El repositorio orchest/orchest anterior a 2022.05.0 en GitHub permite un recorrido de ruta absoluto porque la función Flask send_file se usa de manera insegura.

## Puntuación -> 9.3

## Explotación -> Recorrido de ruta absoluta.
---
# CVE-2020-10987

##  El goform/setUsbUnload endpoint de Tenda  permite a atacantes remotos ejecutar comandos del sistema de su elección.

## Puntuación -> 9.8

## Explotacion -> El atacante puede cambiar el parámetro deviceName de tu enrutador y ejecutar comandos arbitrarios.


![width:300px, height:175px](https://assets.website-files.com/5ff66329429d880392f6cba2/6275065bd4a769dc2e3c3739_Remote%20code%20execution.jpg)

---
# CVE-2021-0920

##  Este problema puede llevar a que el sistema de Linux no se limpie adecuadamente cierta información.

## Puntuación -> 6.9

## Explotación -> La interacción del usuario no es necesaria para la explotación.
---
# CVE-2023-34476

## Un comando SQL usando entradas externas de un componente, no neutraliza o neutraliza incorrectamente elementos especiales que pueda modificar el comando SQL intencionado.

## Puntuación -> 9.8

## Explotación -> Confidencialidad, Control de Acceso, Integridad.
---
# CVE-2021-32566

##  Un atacante puede crear el input de una forma que no es esperada por el resto de la aplicación en HTTP/2 de Apache Traffic Server.

## Puntuacion -> 7.5

## Explotacion -> Disponibilidad, Confidencialidad, Integridad.
