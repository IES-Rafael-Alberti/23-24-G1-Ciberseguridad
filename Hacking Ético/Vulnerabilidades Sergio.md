## CVE-2022-31503

### Descripción

El repositorio orchest/orchest anterior a 2022.05.0 en GitHub permite un recorrido de ruta absoluto porque la función Flask send_file se usa de manera insegura.

### Referencias

[https://github.com/github/securitylab/issues/669#issuecomment-1117265726](https://github.com/github/securitylab/issues/669#issuecomment-1117265726)

[https://github.com/orchest/orchest/pull/913](https://github.com/orchest/orchest/pull/913)

[https://github.com/orchest/orchest/releases/tag/v2022.05.0](https://github.com/orchest/orchest/releases/tag/v2022.05.0)

### Impacto

- Base Score: [9.3 Critico](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2022-31503&vector=AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:N/A:L&version=3.1&source=NIST)
- Vector: CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:N/A:L
- Sistemas Afectados: Orchest/orchest anterior a la versión 2022.05.0 

### Explotación

- Clase: Recorrido de ruta absoluta
  
  Gracias a la función Flask send_file un archivo cargado en orchest nos puede dar acceso a la ruta raiz.
  
- CWE: [CWE22](https://cwe.mitre.org/data/definitions/22.html)

### Solución

- Actualzar Orchest a una versión más nueva.
- Eliminar rutas no seguras en los modulos de los proyectos.

## CVE-2022-24877

### Descripción

Flux es una solución de entrega continua abierta y extensible para Kubernetes. Path Traversal en el controlador kustomize a través de un `kustomization.yaml` malicioso permite a un atacante exponer datos confidenciales del sistema de archivos pod del controlador y posiblemente una escalada de privilegios en implementaciones de múltiples inquilinos. Las soluciones alternativas incluyen herramientas automatizadas en la canalización de CI/CD del usuario para validar que los archivos `kustomization.yaml` cumplan con políticas específicas. Esta vulnerabilidad se solucionó en kustomize-controller v0.24.0 y se incluyó en flux2 v0.29.0.

### Referencias

[https://github.com/fluxcd/flux2/security/advisories/GHSA-j77r-2fxf-5jrw](https://github.com/fluxcd/flux2/security/advisories/GHSA-j77r-2fxf-5jrw)

### Impacto

- Base Score: [8.8 Alto](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2022-24877&vector=AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:H&version=3.1&source=NIST)
- Vector: CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:H
- Sistemas Afectados: Flux2 versión anterior a 0.29.0 y Kustomize-controller versión anterior a 0.24.0

### Explotación

- Clase: Exposición de datos confidenciales y posible escalada de privilegios.

  A traves de un fichero .yaml malicioso permite al atacante no solo exponer datos confidenciales si no que además permite una escalada de privilegios en implementaciones de múltiples inquilinos.
- CWE: [CW22](http://cwe.mitre.org/data/definitions/22.html) y [CWE36](http://cwe.mitre.org/data/definitions/36.html)

### Solución



  
