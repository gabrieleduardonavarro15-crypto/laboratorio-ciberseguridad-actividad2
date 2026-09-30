# Informe Técnico: Mi Primer Laboratorio Seguro de Ciberseguridad

## 1. Introducción y Objetivo
El propósito de este laboratorio es implementar un entorno virtualizado seguro utilizando Ubuntu Desktop en Oracle VirtualBox, aplicando medidas fundamentales de hardening (endurecimiento del sistema), gestión segura de usuarios, actualización de paquetes y preservación del estado mediante instantáneas (snapshots).

---

## 2. Descripción de las Fases e Implementación

### Paso 1: Instalación de Ubuntu Desktop
Se realizó la instalación limpia del sistema operativo Ubuntu Desktop en una máquina virtual sobre Oracle VirtualBox.
* **Propósito de Seguridad:** Contar con un entorno base controlado, aislado del sistema anfitrión, reduciendo la superficie de ataque inicial.
* **Evidencia:**  
  ![Instalación Ubuntu](IMG/01-instalacion-ubuntu.png)

---

### Paso 2: Gestión de Usuarios y Separación de Privilegios
Se configuró el principio de mínimo privilegio creando una cuenta de usuario estándar (`gabriel`) para las operaciones cotidianas, reservando el acceso administrativo únicamente mediante el uso explícito de `sudo`.
* **Propósito de Seguridad:** Evitar ejecutar tareas diarias como superusuario (`root`), lo que previene modificaciones accidentalmente destructivas o la ejecución de software malicioso con privilegios elevados.
* **Evidencia:**  
  ![Usuario Estándar](IMG/02-usuario-estandar.png)

---

### Paso 3: Actualización y Parcheo de Paquetes del Sistema
Se ejecutaron los comandos de actualización de repositorios y paquetes para garantizar que todo el software instalado cuente con los últimos parches de seguridad.
* **Comandos Ejecutados:**
  ```bash
  sudo apt update
  sudo apt upgrade -y


* **Propósito de Seguridad:** Mitigar vulnerabilidades conocidas (CVEs) en el kernel y paquetes del sistema operativo antes de exponer el entorno a redes.
* **Evidencias:**
* *Lectura de repositorios:*
* *Sistema completamente actualizado:*



---

### Paso 4: Gestión de Permisos de Archivos

Se verificaron y ajustaron los permisos de acceso en archivos críticos del sistema mediante el uso de listas detalladas.

* **Comando Ejecutado:**
```bash
ls -l prueba.txt



* **Propósito de Seguridad:** Garantizar la confidencialidad e integridad de la información restringiendo los permisos de lectura, escritura y ejecución solo a los usuarios autorizados.
* **Evidencia:**
![Permisos de Archivos](IMG/04-permisos-lsl.png)
---

### Paso 5: Creación de Snapshot de Respaldo

Se generó una instantánea (snapshot) en Oracle VirtualBox bajo el nombre `Clean Install - Hardening applied`.

* **Propósito de Seguridad:** Establecer una línea base segura (*baseline*) que permite restaurar el laboratorio a un estado limpio y seguro en caso de fallos, ataques o pruebas destructivas.
* **Evidencia:**
![Snapshot de VirtualBox](IMG/06-snapshot-laboratorio.png)
---

## 3. Conclusión

Se logró desplegar un laboratorio virtualizado aplicando controles básicos de seguridad cibernética: aislamiento de entorno, separación de privilegios, parcheo continuo de vulnerabilidades, control de accesos a archivos y respaldo de estado.

