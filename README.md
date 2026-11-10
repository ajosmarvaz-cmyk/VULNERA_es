# VULNERA_es
## Descripción
VULNERA es un servicio en la nube que detecta las vulnerabilidades de un sistema y propone soluciones de manera gratuita.
## Problemas que aborda
Muchas empresas pequeñas publican sitios web sin haber pasado por una auditoría previa, esto conlleva a errores de configuración básicos y evitables: cabeceras de seguridad ausentes, cookies sin los flags adecuados, certificados TLS débiles o caducados, etc.
También el problema, no son solo proyectos que no han pasado por auditorías de seguridad sino también herramientas de seguridad con licencias con un precio excesivo orientadas a empresas grandes.
## Objetivo principal
VULNERA no busca reemplazar a estas herramientas ni busca ser la herramienta más técnica y mejor consolidada, su objetivo es simple, ofrecer una capa accesible para todos y centralizada con un panel web de login, recomendaciones claras, resultados, etc.
## Tecnologías
El motor de análisis, la API y el CLI están escritos en Python, por su cantidad de librerías para peticiones HTTP, análisis TLS y parseo de HTML. La API usa FastAPI, que es rápido de desarrollar y genera su propia documentación. Los datos (usuarios, proyectos, escaneos y hallazgos) se guardan en PostgreSQL, elegido por su solidez con las relaciones entre tablas y su soporte de JSON para la evidencia de cada hallazgo. El panel web es ligero, con HTML, CSS y JavaScript, e i18next para el cambio de idioma entre inglés y español.
La infraestructura se despliega en AWS (VPC, EC2, Security Groups y snapshots) sobre Ubuntu Server, con Nginx como reverse proxy y HTTPS mediante Let's Encrypt. En local se trabaja con VirtualBox y Docker, y las pruebas se hacen contra DVWA y OWASP Juice Shop en un laboratorio aislado. La instalación, los backups y los escaneos programados se automatizan con Bash y cron.
El trabajo se organiza con Git y GitHub (código y documentación), Jira (tablero Kanban) y draw.io y Mermaid (diagramas).
## Funcionalidades o características principales
- Análisis de una URL con comprobación de cabeceras de seguridad, cookies, TLS, banners de servidor, formularios sin protección CSRF y directorios expuestos.
- Informe por hallazgo con evidencia, severidad, referencia OWASP/CWE y recomendación.
- Login seguro, proyectos por usuario e histórico de escaneos en la nube.
- Comparación entre dos escaneos de un mismo proyecto.
- Panel web oscuro y minimalista, en inglés con selector EN/ES, y CLI con salida limpia.
- Escaneos programados y despliegue en AWS con HTTPS, copias de seguridad y monitorización.
## Planificación
El proyecto sigue seis fases: planificación inicial, análisis y diseño, desarrollo, pruebas, despliegue y mantenimiento. El trabajo se reparte en sprints semanales que cierran los miércoles, y el detalle de cada tarea está en Jira.

v0.1 (MVP): CLI con tres checks, a mediados de diciembre de 2026.
v0.2: motor completo con tests, a finales de enero de 2027.
v0.3: API con login y base de datos, a principios de marzo.
v0.4: panel web con selector de idioma, a finales de marzo.
v1.0: despliegue completo en AWS, a mediados de mayo.
##Estado actual del proyecto
Fase 1: planificación inicial. El anteproyecto está redactado y el tablero de Jira y el repositorio están creados. Quedan por completar la planificación de tareas, el diagrama de AWS, los prototipos y la página web.
## Diseño técnico
- Modelo Entidad-Relación
- Prototipo de interfaz
- Arquitectura de red en AWS (en elaboración)
## Enlaces
Tablero Jira: https://joseantoniomartinezvazquez.atlassian.net/jira/software/projects/VUL/list?jql=project+%3D+%22VUL%22+AND+%28statusCategory+%21%3D+Done+OR+%28statusCategory+%3D+Done+AND+statusCategoryChangedDate+%3E%3D+-2w%29%29+ORDER+BY+status+ASC&atlOrigin=eyJpIjoiZDk5NzNkZTE2MGNlNDY3ZTg0NTBkZWQ0NWU3N2Y2MTYiLCJwIjoiaiJ9
Web del proyecto: https://github.com/ajosmarvaz-cmyk/VULNERA_es
