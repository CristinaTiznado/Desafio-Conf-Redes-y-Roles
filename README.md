# Configuración de Redes y Roles Web

[![GitHub License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Windows Server](https://img.shields.io/badge/Platform-Windows%20Server%202019-0078d4.svg)](https://www.microsoft.com/es-es/windows-server)
[![IIS](https://img.shields.io/badge/Services-IIS%20%7C%20HTTP%20%7C%20FTP-blue.svg)](https://www.iis.net/)
[![VMware](https://img.shields.io/badge/Virtualization-VMWare-607d8b.svg)](https://www.vmware.com/)

## 📋 Descripción del Proyecto

Análisis práctico y comprobación del funcionamiento de los servicios **HTTP** y **FTP** en un entorno de **Windows Server 2019**. Este proyecto, realizado como parte de una evaluación académica, tiene como objetivo asegurar que la configuración de los roles web sea efectiva y cumpla con los requerimientos planteados, incluyendo pruebas locales en el servidor y pruebas remotas desde un equipo cliente.

## 🖥️ Entorno de Pruebas

El entorno de laboratorio fue levantado en **VMware Workstation**, y consta de dos componentes principales:
- **Servidor:** Máquina Virtual con Windows Server 2019 (4GB RAM, 2 CPU, 60GB HDD).
- **Cliente:** Equipo anfitrión con Debian 11 para realizar las pruebas de conexión remota.

## 🎯 Objetivos de la Evaluación

### ✅ 1. Entorno de Laboratorio
Levantar una máquina virtual con el entorno de Windows Server.

### ✅ 2. Configuración de Servicios
Los servicios HTTP y FTP deben estar configurados en el servidor. Se debe haber modificado la página de bienvenida (HTTP) y activado el protocolo FTP.

### ✅ 3. Cliente FTP
Instalar un cliente FTP en el equipo cliente para realizar pruebas de transferencia de archivos.

## 🔄 Proceso de Ejecución

### Paso 1: Entorno de Laboratorio
- Se configuró una máquina virtual "Windows Server 2019" en VMWare Workstation.
- La VM se configuró con adaptador de red NAT.

### Paso 2: Configuración de Servicios (HTTP y FTP)
- Se instalaron y configuraron los roles web (IIS) en el servidor Windows.
- **Servicio HTTP:** Se mantuvo el "Default Web Site" y se modificó su contenido por una "Calculadora de IMC", accesible localmente vía `localhost`.
- **Servicio FTP:** Se creó un nuevo sitio FTP llamado "desafio" apuntando a la ruta `C:\inetpub\ftproot` y permitiendo acceso anónimo.
- **Prueba Local:** Se realizó una prueba de conexión FTP local desde el CMD del servidor (`ftp 172.16.70.128`), confirmando el acceso y listando archivos.

### Paso 3: Pruebas de Cliente FTP
- Se utilizó **FileZilla** desde el host Debian 11 como cliente FTP.
- Se estableció conexión exitosa con el servidor en la IP `172.16.70.128` usando el usuario `ftp`.
- Se verificó el listado de directorios remotos.
- Se realizaron pruebas de transferencia de archivos:
    - **Descarga:** Se transfirió `documento_servidor.rtf` del servidor al cliente.
    - **Subida:** Se transfirió `documento_cliente.txt` del cliente al servidor.
- Ambas transferencias se completaron exitosamente.

## 📸 Evidencia del Cumplimiento

| Requerimiento | Evidencia Visual | Descripción |
|---------------|--------------------------------|-------------|
| **1. Entorno de Laboratorio** | ![](images/VM%20Windows%20Server%202019.png) | Configuración de la VM Windows Server 2019 en VMWare. |
| **2. Configuración IIS** | ![](images/Configuraci%C3%B3n%20IIS.png) | Administrador de IIS mostrando sitios "Default Web Site" (HTTP) y "desafio" (FTP) iniciados. |
| **2. Página HTTP Modificada** | ![](images/P%C3%A1gina%20HTTP%20Modificada.png) | Navegador en el servidor mostrando la página "Calculadora de IMC" en `localhost`. |
| **2. Prueba FTP Local** | ![](images/Prueba%20FTP%20Local.png) | Símbolo del sistema (CMD) en el servidor conectándose al servicio FTP localmente. |
| **3. Cliente FTP Conectado** | ![](images/Cliente%20FTP%20Conectado.png) | Cliente FileZilla (en Debian) conectado al servidor FTP, listando archivos remotos. |
| **3. Transferencia de Archivos** | ![](images/Transferencia%20de%20Archivos.png) | Registro de FileZilla mostrando "Successful transfers (2)", confirmando subida y bajada de archivos. |

## 📊 Resultados Obtenidos

**Todos los requerimientos cumplidos exitosamente**. <br>
✅ **VM Windows Server 2019** operativa y configurada en VMWare. <br>
✅ **Servicio HTTP (IIS)** funcional, sirviendo una página de bienvenida personalizada ("Calculadora de IMC"). <br>
✅ **Servicio FTP (IIS)** activo y funcional, probado exitosamente tanto localmente (CMD) como remotamente (FileZilla). <br>
✅ **Transferencia de archivos** bidireccional (subida y bajada) entre el cliente (Debian) y el servidor (Windows Server) confirmada. <br>

## 🛠️ Tecnologías Utilizadas

- **Virtualización:** VMWare Workstation 17 PRO
- **SO Servidor:** Windows Server 2019
- **SO Cliente:** Debian 11
- **Servicios:** IIS (Internet Information Services) para HTTP y FTP
- **Herramientas Cliente:** FileZilla, Símbolo del sistema de Windows

## 📚 Conclusión

Este proyecto demuestra la comprensión práctica de:
- Configuración de un entorno de servidor virtualizado con Windows Server.
- Instalación, configuración y gestión de roles web y FTP en IIS.
- Modificación de contenido web básico (HTTP).
- Verificación de servicios de red (local y remotamente).
- Uso de clientes FTP para la transferencia de archivos.
- Documentación técnica de un proceso de configuración de red.
