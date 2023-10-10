## CVE-2020-10987

### Descripción

El goform/setUsbUnload endpoint de Tenda AC15 AC1900 versión 15.03.05.19 permite a atacantes remotos ejecutar comandos del sistema de su elección a través del parámetro POST deviceName.

### Referencias

[https://nvd.nist.gov/vuln/detail/CVE-2020-10987](https://nvd.nist.gov/vuln/detail/CVE-2020-10987)

[https://blog.securityevaluators.com/tenda-ac1900-vulnerabilities-discovered-and-exploited-e8e26aa0bc68](https://blog.securityevaluators.com/tenda-ac1900-vulnerabilities-discovered-and-exploited-e8e26aa0bc68)

[https://www.fortiguard.com/encyclopedia/ips/49352](https://www.fortiguard.com/encyclopedia/ips/49352)

### Impacto

- Base Score: [9.8 CRITICAL](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2020-10987&vector=AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
- Vector: [CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2020-10987&vector=AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
- Sistemas Afectados: Tenda AC15 AC1900

### Explotación

El atacante puede cambiar el parámetro deviceName de tu enrutador y ejecutar comandos arbitrarios.  
CWE: [CWE-78](https://cwe.mitre.org/data/definitions/78.html)

### Solución

Actualmente no se conoce ningún parche proporcionado por el proveedor ni actualizaciones disponibles para este problema.

## CVE-2021-0920

### Descripción

Se descubrió un problema en el sistema operativo Linux que afecta a la forma en que se manejan ciertos tipos de conexiones de red llamadas "sockets de dominio Unix". Este problema puede llevar a que el sistema no limpie adecuadamente cierta información, lo que podría causar un mal uso de la memoria y, en última instancia, hacer que el sistema se bloquee o permitir que un usuario local aumente sus privilegios en el sistema.

### Referencias

[https://www.cve.org/CVERecord?id=CVE-2021-0920](https://www.cve.org/CVERecord?id=CVE-2021-0920)

[https://nvd.nist.gov/vuln/detail/cve-2021-0920](https://nvd.nist.gov/vuln/detail/cve-2021-0920)

[https://googleprojectzero.github.io/0days-in-the-wild//0day-RCAs/2021/CVE-2021-0920.html](https://googleprojectzero.github.io/0days-in-the-wild//0day-RCAs/2021/CVE-2021-0920.html)

[https://access.redhat.com/security/cve/cve-2021-0920](https://access.redhat.com/security/cve/cve-2021-0920)

### Impacto

- Base Score: [6.9 MEDIUM](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2021-0920&vector=AV:L/AC:H/PR:H/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
- Vector: [AV:L/AC:M/Au:N/C:C/I:C/A:C](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2021-0920&vector=AV:L/AC:H/PR:H/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
- Sistemas Afectados: AndroidVersions: Android kernelAndroid ID: A-196926917

### Explotación

En unix_scm_to_skb de af_unix.c, existe un posible error que podría conducir a una escalada local de privilegios. 

La interacción del usuario no es necesaria para la explotación.

CWE: [CWE-416](https://cwe.mitre.org/data/definitions/416.html)  

### Solucion

La mitigación para este problema no está disponible.

