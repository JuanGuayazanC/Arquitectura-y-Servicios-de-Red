# Arquitectura y Servicios de Red (AYSR)

Repositorio general del curso Arquitectura y Servicios de Red, que agrupa —mediante submódulos de git— los laboratorios del curso, incluyendo dos intentos: 2025-2 y 2026-1.

Cada submódulo es un repositorio independiente con su propio historial de commits y README. Para saber cómo aprovechar este repositorio, ver [Cómo usar este repositorio](#cómo-usar-este-repositorio).

## Estructura del proyecto

```
Arquitectura-y-Servicios-de-Red/
└── Laboratorios/
    ├── Plataforma-Base-y-Servidor-DNS-AYSR/            # Servidor DNS (BIND/named)
    │   ├── AYSR-6L/                                    #   Intento 2026-1
    │   └── AYSR-5L/                                    #   Intento 2025-2
    ├── Capa-de-Aplicacion-y-Capa-Fisica-AYSR/           # Protocolos de capa de aplicación y física
    │   ├── AYSR-6L/
    │   └── AYSR-5L/
    ├── Protocolos-de-Red-para-Bases-de-Datos-AYSR/      # Bases de datos y protocolos de red
    │   ├── AYSR-6L/
    │   └── AYSR-5L/
    ├── Servidores-Web-Nginx-y-Apache-AYSR/              # Servidores web y protocolos de aplicación
    │   ├── AYSR-6L/
    │   └── AYSR-5L/
    ├── Infraestructura-Basica-y-Capa-de-Red-AYSR/       # Infraestructura básica y capa de red
    │   ├── AYSR-6L/
    │   └── AYSR-5L/
    ├── Capa-de-Enlace-y-Aplicacion-AYSR/                # VLANs, WiFi, capa de enlace
    │   ├── AYSR-6L/
    │   └── AYSR-5L/
    ├── Configuracion-de-SO-y-Shell-Scripting-AYSR/      # Configuración de SO y shell scripting (2026-1)
    ├── Plataforma-Base-Windows-Server-y-Android-AYSR/   # Windows Server y Android (2026-1)
    └── Creacion-de-Instancia-EC2-en-AWS-AYSR/        # Instancia EC2 en AWS (2025-2)
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

- El curso se vio dos veces: 2025-2 y 2026-1. Los laboratorios con versión en ambos intentos quedan agrupados en la misma carpeta.
- Los laboratorios se desarrollaron en pareja.
- Cada laboratorio se documenta como un informe en LaTeX (compilado a PDF) dentro de su propio repositorio.
- En el intento 2026-1, cada repositorio incluye una carpeta `scripts/` con el código Shell (u otro código ejecutable, como SQL) relacionado con ese laboratorio, extraído o reconstruido a partir del informe:
  - `Infraestructura-Basica-y-Capa-de-Red-AYSR`: `network_info.sh` y `check_port.sh` — extraídos textualmente del informe (`lstlisting`).
  - `Servidores-Web-Nginx-y-Apache-AYSR`: `nginx.conf`, `rc.nginx`, `rc.local` — transcritos de las capturas de pantalla del informe.
  - `Plataforma-Base-y-Servidor-DNS-AYSR`: `setup_dns.sh` — combina los comandos reales de instalación/arranque de BIND mostrados en el informe.
  - `Capa-de-Aplicacion-y-Capa-Fisica-AYSR`: `http_dhcp_demo.sh` — combina los comandos reales de la demostración DHCP/HTTP del informe.
  - `Protocolos-de-Red-para-Bases-de-Datos-AYSR`: `database.sql` (SQL real del informe) y `setup_database.sh` (wrapper).
  - `Plataforma-Base-Windows-Server-y-Android-AYSR`: `sysinfo.sh` — combina los comandos Linux/Unix del comparativo de comandos del informe.
  - `Capa-de-Enlace-y-Aplicacion-AYSR`: `verify_connectivity.sh` — sintetizado a partir de la verificación de conectividad descrita en el informe.
  - `Configuracion-de-SO-y-Shell-Scripting-AYSR`: `new_group.sh`, `new_user.sh`, `ls_command.sh`, `file_search.sh`, `log_file_review.sh` — el código fuente original no se subió a GitHub; estos scripts se **reconstruyeron** a partir del comportamiento observado en las capturas de pantalla de su ejecución.

## Herramientas

- LaTeX / IEEEtran (formato de los informes)
- Cisco Packet Tracer
- Apache, Nginx, PostgreSQL, BIND (named)
- Scripts de shell (administración de sistema, arranque de servicios)
- Microsoft Azure

## Profesores

Claudia Patricia Santiago Cely (intento 2025-2). William Fernando Sánchez Pacheco (teoría) y Fabián Eduardo Sierra Sánchez (laboratorio) (intento 2026-1).

## Cómo usar este repositorio

Este repositorio no contiene código directamente: es una colección de repositorios independientes, uno por laboratorio (y, en algunos casos, dos versiones del mismo laboratorio de intentos distintos), organizados por carpetas dentro de `Laboratorios/`. Cada carpeta es un submódulo de git que apunta al repositorio real de esa actividad.

- **Para consultar un laboratorio puntual**: entra directamente a su carpeta en GitHub (o navega el submódulo) y revisa su propio README.
- **Para tener todo el contenido en tu máquina**:

```bash
git clone --recurse-submodules https://github.com/JuanGuayazanC/Arquitectura-y-Servicios-de-Red.git
```

Si ya clonaste el repositorio sin submódulos:

```bash
git submodule update --init --recursive
```
