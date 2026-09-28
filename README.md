#  Fundamentos de Seguridad en Windows Server y Active Directory

Este repositorio documenta la configuración de políticas de acceso, gestión de identidades y monitorización de eventos de seguridad en un entorno de Directorio Activo (AD DS), orientado al análisis defensivo (Blue Team) y operaciones de SOC (Nivel 1).

---

##  Resumen del Laboratorio
* **Servidor (DC):** Windows Server (`WS-25-DC-1-DOM1.dominio1.local`) con rol Active Directory Domain Services.
* **Cliente:** Windows 11 Pro (`WIN11-CLIENTE`) unido al dominio `DOMINIO1`.
* **Identidad auditada:** Usuario estándar `deniz.auditor` perteneciente al grupo de seguridad `G-Auditores`.
* **Mecanismo de seguridad:** Directiva de Bloqueo de Cuentas vía GPO (*Default Domain Policy*), configurada con un umbral de 3 intentos fallidos y duración de 15 minutos.
* **Objetivo defensivo:** Trazar el ciclo de vida de una sesión (inicio, fallos repetidos, bloqueo reactivo y cierre) en el Visor de Eventos de Windows (`Security.evtx`).

---

##  Contenido del Repositorio
* **[`windows-ad-security-basics.md`](./windows-ad-security-basics.md):** Documentación técnica exhaustiva con explicación de eventos, códigos NTSTATUS, tabla de análisis forense y procedimiento de triaje SOC.
* **`assets/`:** Evidencias gráficas extraídas del Visor de Eventos tanto en el Controlador de Dominio como en el equipo cliente.

---

##  Habilidades Demostradas
* Administración y auditoría de objetos en Active Directory (OUs, Usuarios, Grupos de Seguridad).
* Despliegue de políticas de contraseñas y directivas de bloqueo mediante GPO.
* Análisis e interpretación de registros de seguridad (`Event IDs 4624, 4625, 4740, 4647`).
* Comprensión de la arquitectura cliente-servidor en la recolección de telemetría (logs locales en endpoint vs. centralización en DC y SIEM).
