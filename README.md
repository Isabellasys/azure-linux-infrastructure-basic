# Azure Linux Infrastructure Basic 🚀

Proyecto realizado para practicar automatización de infraestructura en Microsoft Azure utilizando Ansible, Linux y Docker.

La idea de este proyecto fue aprender a desplegar una máquina virtual Linux sin crear recursos manualmente desde el portal de Azure, utilizando Infraestructura como Código (IaC).

Como parte de la práctica, la máquina virtual se aprovisiona automáticamente, instala Docker mediante Cloud-Init, descarga este repositorio desde GitHub y ejecuta la aplicación web dentro de un contenedor Docker.

La infraestructura en Azure fue utilizada como entorno de aprendizaje y pruebas. La versión pública de la web se encuentra desplegada en Netlify mediante integración automática con GitHub.

## 🌐 Web publicada

https://azure-linux-infrastructure-basic.netlify.app

---

## Tecnologías utilizadas

* Microsoft Azure
* Azure Cloud Shell
* Azure CLI
* Ansible
* Ubuntu Server
* Docker
* GitHub
* Netlify
* HTML
* CSS
* JavaScript

---

## ¿Qué hace este proyecto?

El playbook de Ansible automatiza la creación de:

* Resource Group
* Virtual Network (VNet)
* Subred
* Network Security Group (NSG)
* Dirección IP pública
* Tarjeta de red (NIC)
* Máquina virtual Ubuntu Server

Una vez creada la máquina virtual, Cloud-Init ejecuta automáticamente las siguientes tareas:

1. Actualiza el sistema operativo.
2. Instala Docker y Git.
3. Clona este repositorio desde GitHub.
4. Construye la imagen Docker.
5. Ejecuta la aplicación web en un contenedor.

De esta forma la máquina queda preparada sin necesidad de configuraciones manuales posteriores.

---

## Seguridad

El Network Security Group (NSG) permite únicamente los puertos necesarios para la práctica:

| Puerto | Uso               |
| ------ | ----------------- |
| 22     | Acceso SSH        |
| 80     | Servicio Web HTTP |

---

## Flujo de despliegue

```text
Ansible
    ↓
Azure
    ↓
Ubuntu Server
    ↓
Cloud-Init
    ↓
Instalación automática de Docker
    ↓
Clonado del repositorio desde GitHub
    ↓
Construcción de la imagen Docker
    ↓
Ejecución del contenedor web
```

---

## Despliegue de la web

La versión pública de la aplicación está conectada a GitHub mediante Netlify.

Cada vez que realizo cambios en el repositorio y ejecuto:

```bash
git push origin main
```

Netlify detecta automáticamente la actualización y publica una nueva versión de la web.

---

## Cómo ejecutar el proyecto

### Clonar el repositorio

```bash
git clone https://github.com/Isabellasys/azure-linux-infrastructure-basic.git
```

### Ejecutar el playbook

```bash
cd azure-linux-infrastructure-basic/ansible

ansible-playbook create-infra.yml
```

---

## Lo que he practicado con este proyecto

* Infraestructura como Código (IaC)
* Automatización con Ansible
* Administración básica de Linux
* Redes en Azure
* Network Security Groups (NSG)
* Cloud-Init
* Docker
* Git y GitHub
* Integración continua básica mediante Netlify

---

## Autora

**Isabella**

Estudiante de Administración de Sistemas Informáticos en Red (ASIR) interesada en Linux, Cloud Computing, Automatización y tecnologías Cloud.
