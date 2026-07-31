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

- Los laboratorios se desarrollaron en pareja con ANDRES CAMILO VIVAS BAQUERO (`Cam1lo27` en GitHub), quien es colaborador directo en `Plataforma-Base-y-Servidor-DNS-AYSR`, `Configuracion-de-SO-y-Shell-Scripting-AYSR` e `Infraestructura-Basica-y-Capa-de-Red-AYSR` (estos tres son los repositorios originales del curso, renombrados para reflejar su contenido real tras dividir cada uno en sus laboratorios individuales — se conservó el mismo repositorio, en vez de crear uno nuevo, para no tener que reenviarle la invitación de colaborador).
- Cada laboratorio se documenta como un informe en LaTeX (compilado a PDF) dentro de su propio repositorio.
- Cada repositorio incluye una carpeta `scripts/` con el código Shell (u otro código ejecutable, como SQL) relacionado con ese laboratorio, extraído o reconstruido a partir del informe:
  - `Infraestructura-Basica-y-Capa-de-Red-AYSR`: `network_info.sh` y `check_port.sh` — extraídos textualmente del informe (`lstlisting`).
  - `Servidores-Web-Nginx-y-Apache-AYSR`: `nginx.conf`, `rc.nginx`, `rc.local` — transcritos de las capturas de pantalla del informe.
  - `Plataforma-Base-y-Servidor-DNS-AYSR`: `setup_dns.sh` — combina los comandos reales de instalación/arranque de BIND mostrados en el informe.
  - `Capa-de-Aplicacion-y-Capa-Fisica-AYSR`: `http_dhcp_demo.sh` — combina los comandos reales de la demostración DHCP/HTTP del informe.
  - `Protocolos-de-Red-para-Bases-de-Datos-AYSR`: `database.sql` (SQL real del informe) y `setup_database.sh` (wrapper).
  - `Plataforma-Base-Windows-Server-y-Android-AYSR`: `sysinfo.sh` — combina los comandos Linux/Unix del comparativo de comandos del informe.
  - `Capa-de-Enlace-y-Aplicacion-AYSR`: `verify_connectivity.sh` — sintetizado a partir de la verificación de conectividad descrita en el informe.
  - `Configuracion-de-SO-y-Shell-Scripting-AYSR`: `new_group.sh`, `new_user.sh`, `ls_command.sh`, `file_search.sh`, `log_file_review.sh` — el código fuente original no se subió a GitHub; estos scripts se **reconstruyeron** a partir del comportamiento observado en las capturas de pantalla de su ejecución, por instrucción explícita del autor.

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
