# Arquitectura y Servicios de Red (AYSR)

Repositorio general del curso Arquitectura y Servicios de Red (ISIS AYSR-6L), que agrupa —mediante submódulos de git— los laboratorios del curso.

Cada submódulo es un repositorio independiente con su propio historial de commits y README. Para clonar este repositorio junto con todo su contenido, ver [Cómo clonar](#cómo-clonar).

## Estructura del proyecto

```
Arquitectura-y-Servicios-de-Red/
└── Laboratorios/
    ├── Plataforma-Base-y-Servidor-DNS-AYSR/
    ├── Capa-de-Aplicacion-y-Capa-Fisica-AYSR/
    ├── Protocolos-de-Red-para-Bases-de-Datos-AYSR/
    ├── Configuracion-de-SO-y-Shell-Scripting-AYSR/
    ├── Plataforma-Base-Windows-Server-y-Android-AYSR/
    ├── Infraestructura-Basica-y-Capa-de-Red-AYSR/
    ├── Servidores-Web-Nginx-y-Apache-AYSR/
    └── Capa-de-Enlace-y-Aplicacion-AYSR/
```

## Temas del curso

El curso recorre la arquitectura de redes de computadores por capas y el montaje de servicios de red reales sobre infraestructura propia:

- **Infraestructura base y capa física**: montaje de máquinas virtuales, pruebas de conectividad, configuración de equipos Cisco.
- **Capa de enlace y capa de red**: protocolos de enrutamiento, análisis de tráfico y rutas (capturas `.pcapng`), simulación de redes con Cisco Packet Tracer.
- **Capa de aplicación**: servidores web (Apache, Nginx), servidores DNS (`named`/BIND), y protocolos de aplicación.
- **Plataforma base de servicios**: montaje de plataformas completas (servidor web + base de datos PostgreSQL, Windows Server, Android) con arranque automático de servicios (scripts `rc.d` estilo Slackware/BSD).
- **Bases de datos y protocolos de red**: acceso y gestión de bases de datos a través de la red.
- **Administración de sistemas mediante shell**: creación de usuarios/grupos, listados avanzados de archivos, búsqueda en archivos y revisión de logs mediante scripts propios.
- **Despliegue en la nube**: publicación de aplicaciones web en Azure.

## Cosas a tener en cuenta

- Los laboratorios se desarrollaron en pareja con ANDRES CAMILO VIVAS BAQUERO.
- Cada laboratorio se documenta como un informe en LaTeX (compilado a PDF) dentro de su propio repositorio.
- Los 8 repositorios de este curso provienen de 3 repositorios originales (`network-protocols-and-databases-AYSR`, `it-infrastructure-AYSR`, `AYSR3`), cada uno con 2-3 laboratorios mezclados, separados aquí en un repositorio por laboratorio.
- En `Servidores-Web-Nginx-y-Apache-AYSR` se integraron scripts de arranque de Nginx (`rc.nginx`, `rc.local`, `nginx.conf`) transcritos de las capturas de pantalla del informe, ya que el código fuente original no se había subido a GitHub.
- En `Configuracion-de-SO-y-Shell-Scripting-AYSR` se usaron cinco scripts de shell propios cuyo código fuente no se pudo recuperar (`new_group.sh`, `new_user.sh`, `ls_command.sh`, `file_search.sh`, `log_file_review.sh`) — solo queda la evidencia de su ejecución en capturas de pantalla.

## Herramientas

- LaTeX / IEEEtran (formato de los informes)
- Cisco Packet Tracer
- Apache, Nginx, PostgreSQL, BIND (named)
- Scripts de shell (administración de sistema, arranque de servicios)
- Microsoft Azure

## Cómo clonar

```bash
git clone --recurse-submodules https://github.com/JuanGuayazanC/Arquitectura-y-Servicios-de-Red.git
```

Si ya clonaste el repositorio sin submódulos:

```bash
git submodule update --init --recursive
```
