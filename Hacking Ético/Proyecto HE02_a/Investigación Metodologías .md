
# Investigación de Metodologías de pentesting

En esta parte del proyecto vamos a realizar un pequeño estudio de las diferentes metodologías de pentesting que podemos usar a la hora de realizar una auditoria. 

## OSSTMM

El OSSTMM, o Open Source Security Testing Methodology Manual, es una metodología completa desarrollada por ISECOM para llevar a cabo pruebas, análisis y medición de la seguridad operativa real.

 Es una herramienta diseñada para realizar auditorías técnicas de seguridad de manera consistente y repetible.

Esta metodología se puede dividir en varios temas:

- Seguridad de la Información
- Seguridad de los Procesos
- Seguridad en las Tecnologías de Internet
- Seguridad en las Comunicaciones
- Seguridad Inalámbrica
- Seguridad Física

Tambien especifica lo necesario a saber para realizar una auditoria:

- Conceptos básicos (lo que debes saber / lo que debes hacer)
- Metodología de análisis de seguridad
- Métricas de seguridad operacional
- Confiabilidad
- Flujo de trabajo

### Objetivos

El objetivo principal del OSSTMM es construir las mejores defensas de seguridad. Sus objetivos específicos incluyen establecer un enfoque sistemático para auditorías de seguridad más consistentes y repetibles, proporcionar un mecanismo para evaluar los resultados de las auditorías de manera objetiva y permitir una presentación estructurada y comparativa de los resultados.

### Fases de una auditoria

Estas son las fases que deberia de tener una auditoria según OSSTMM:

1. **Lanzar el proyecto:** Esta etapa implica la aprobación de recursos y la conciencia de los posibles impactos no deseados en los sistemas de información.
2. **Fase inductiva:** En esta fase, se comprenden los requisitos, alcance y limitaciones de la auditoría, lo que ayuda a determinar las pruebas a realizar.
3. **Fase interactiva:** Aquí se planifica la auditoría después de definir el alcance y los tipos de pruebas para cada elemento a auditar.
4. **Fase de investigación:** Se analizan los aspectos organizativos y de gestión de la organización, junto con un análisis técnico inicial de fuentes abiertas.
5. **Fase de intervención:** Esta es la fase central de la auditoría, donde se realizan pruebas técnicas en los elementos del alcance, pudiendo modificar, sobrecargar o bloquear elementos para evaluar la seguridad.
6. **Reporte:** Como fase final, se elabora un informe que evalúa los resultados objetivos y valora los hallazgos identificados durante la auditoría.
7. **Resolución de deficiencias:** La organización debe abordar las deficiencias identificadas en la auditoría, utilizando los resultados y valoraciones como base para priorizar las acciones correctivas.

## OWASP Testing Guide

La metodología de pruebas de penetración de OWASP (Open Web Application Security Project) se centra en evaluar la seguridad de las aplicaciones web y ayudar a identificar y abordar vulnerabilidades de seguridad.

### Objetivos

Estos son los objetivos que se definen en OWASP:

1. **Identificar Vulnerabilidades de Seguridad:**
2. **Evaluar la Seguridad de las Aplicaciones Web**
3. **Proporcionar Recomendaciones de Mitigación**
4. **Concienciar sobre la Seguridad**
5. **Ayudar a las Organizaciones a Proteger sus Activos Digitales**
6. **Mejorar la Calidad del Software**
7. **Promover Pruebas de Penetración Éticas**

### Fases

Estas son las fases a la hora de realizar una auditoria según la metodología OWASP:

1. **Fase de Recopilación de Información:** Esta etapa inicial implica reunir datos sobre el objetivo, como información sobre la aplicación, tecnologías utilizadas, arquitectura, etc. También se busca información de dominio público y se lleva a cabo una enumeración de recursos.
2. **Fase de Análisis:** En esta fase, se analizan las vulnerabilidades potenciales, los puntos de entrada y los flujos de datos. Se evalúa la lógica de la aplicación y se identifican posibles vectores de ataque.
3. **Fase de Descubrimiento de Vulnerabilidades:** Aquí es donde se realizan pruebas activas para descubrir vulnerabilidades, como inyecciones SQL, ataques de cross-site scripting (XSS), vulnerabilidades de seguridad en la autenticación y la autorización, entre otras.
4. **Fase de Explotación:** Si se encuentran vulnerabilidades significativas, se intenta explotarlas para evaluar el impacto real de un ataque. Esto puede incluir la obtención de datos confidenciales o la ejecución de código malicioso.
5. **Fase de Informe:** Luego de las pruebas, se genera un informe que documenta todas las vulnerabilidades encontradas, su gravedad y recomendaciones para solucionarlas. Este informe es una herramienta importante para la organización objetivo para mejorar su seguridad.
6. **Fase de Validación:** Después de que se hayan corregido las vulnerabilidades, se realiza una validación para asegurarse de que los problemas identificados se hayan solucionado adecuadamente.
7. **Fase de Documentación y Entrega Final:** La metodología OWASP enfatiza la importancia de documentar todo el proceso de prueba de penetración y entregar esta documentación a la organización objetivo.

## PTES

El Penetration Testing Execution Standard (PTES) es un estándar que proporciona un marco común para realizar pruebas de penetración o pentesting en empresas y proveedores de servicios de seguridad.

### Objetivos

Los objetivos del estándar PTES son los siguientes:

- Disponer de un marco de referencia para la realización de las auditorías técnicas de seguridad de los sistemas de información de una manera más consistente y replicable.
- Incrementar el valor proporcionado por las pruebas de penetración.

### Fases

1. Interacción previa: En esta etapa se define el alcance y las acciones a realizar para llevar a cabo con éxito la prueba de penetración.
2. Recopilación de información: Se recopila información sobre el objetivo a través de fuentes OSINT, inspección y caracterización, considerando medidas de protección que deben evitarse.
3. Modelado de amenazas: Se analiza el contexto interno y externo para identificar elementos que podrían utilizarse en ataques. Se caracterizan los activos y las amenazas para perfilar los tipos de ataques más probables.
4. Análisis de vulnerabilidades: Se buscan fallos en los sistemas que puedan ser aprovechados por atacantes, desde mala configuración hasta diseños inseguros. Estas vulnerabilidades se verifican para su posible explotación.
5. Explotación: Se ejecutan mecanismos para obtener acceso a sistemas o recursos al aprovechar las vulnerabilidades identificadas. Se utilizan exploits y ataques dirigidos.
6. Post-Explotación: Aquí se asegura la persistencia del acceso obtenido, se realizan movimientos laterales para controlar otros activos y se recopila información valiosa.
7. Informe: Implica la elaboración de un informe detallado que resume los resultados técnicos y metodológicos de la prueba, así como un informe ejecutivo que resume los resultados, riesgos y propuestas de mitigación.

# Selección de Metodología

Nostros vamos a escoger la metodología PTES debido a que comparandolo con los demás, veos que es la más completa ya que se centra en todos los ámbitos de la informática y que ofrece la suficiente versatibilidad para cubrirlos. Y vemos que es la que encaja perfectamente con nuestra empresa.
