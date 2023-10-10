## CVE-2022-31503

El repositorio orchest/orchest anterior a 2022.05.0 en GitHub permite un recorrido de ruta absoluto porque la función Flask send_file se usa de manera insegura.

### Referencias

[https://github.com/github/securitylab/issues/669#issuecomment-1117265726](https://github.com/github/securitylab/issues/669#issuecomment-1117265726)

[https://github.com/orchest/orchest/pull/913](https://github.com/orchest/orchest/pull/913)

[https://github.com/orchest/orchest/releases/tag/v2022.05.0](https://github.com/orchest/orchest/releases/tag/v2022.05.0)

### Impacto

- Base Score: [9.3 Critico](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator?name=CVE-2022-31503&vector=AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:N/A:L&version=3.1&source=NIST)
- Vector: CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:N/A:L
- Sistemas Afectados: Orchest/orchest anterior a la versión 2022.05.0 
