# Gateway-Appliance-BYOL-VMWare


# GUIA DE INSTALACIÓN DE SISTEMA OPERATIVO EN GATEWAY APPLIANCE

### Indice
1. [Despliegue en OpenShift desde IBM Cloud shell](#Despliegue-en-OpenShift-desde-IBM-Cloud-shell-)
2. [Despliegue Aplicación Hello World en Angular](#despliegue-aplicación-hello-world-en-angular-🅰️)
3. [Despliegue Aplicación Listas en Angular](#despliegue-aplicación-listas-en-angular-🅰️)
4. [Despliegue Aplicación Hello World en Nodejs Desde la consola web de OpenShift ](#Despliegue-Aplicación-Hello-World-en-Nodejs-Desde-la-consola-web-de-OpenShift-)
5. [Despliegue de una imagen Docker en un contenedor de Opeshift](#Despliegue-de-una-imagen-Docker-en-un-contenedor-de-Opeshift-)
6. [Despliegue Aplicación CRUD en Angular](#Despliegue-Aplicación-CRUD-en-Angular-)
7. [Instalación y despliegue de Eclipce Che con un operador](#Instalación-y-despliegue-de-Eclipce-Che-con-un-operador-)
8. [Anexos](#ANEXOS)
9. [Pre-requisitos](#Pre-requisitos-)
10. [Referencias](#Referencias)

_Para el desarrollo de este proyecto se tiene como base una máquina con sistema operativo basado en Windows desde la cual se va a realizar toda la conexión, configuración y montaje de la imagen en el servidor remoto._

## Pre-requisitos 📋
_Antes de iniciar, es necesario instalar los siguientes programas y seguir los siguientes pasos:_

### 1. Instalar MotionPro

_Para tener un medio de conexión con la vpn se necesita tener instalado MotionPro el cual se puede descargar desde el siguiente link:_

```
https://support.arraynetworks.net/prx/001/http/supportportal.arraynetworks.net/downloads/downloads.html
```
### 2. Instalar java

_Al momento de subir la imagen .iso al servidor virtual necesitamos poder acceder al monitor remoto del mismo y para esto utilizaremos en una parte del proceso esta herramienta que se puede descargar desde el siguiente link:_

```
https://support.arraynetworks.net/prx/001/http/supportportal.arraynetworks.net/downloads/downloads.html
```
### 3. Instalar icedtea

_Para acceder al escritorio remoto del servidor se genera un archivo .jnlp el cual hace referencia a Java Network Launching Protocol y una de las formas de abrirlo es mediante icedtea, el cual se descarga mediante el siguiente link:_

```
https://icetea.uptodown.com/windows/descargar
```

## MONTAJE DE LA IMAGEN .ISO AL GATEWAY APPLIANCE: 🚀

### Paso 1

_Lo primero que debemos realizar es la conexión con el motion pro a la vpn, para esto, ingrese a motion pro y añada una nueva conexión._

<p align="center">
<img width="335" alt="MotionPro" src="https://user-images.githubusercontent.com/60987042/100011136-4bd17400-2d9f-11eb-86ad-837f845fd15e.png">
</p>

_**Site Name:** Dirección IP privada de la máquina._

_**Host:** VPN según la región que se encuentre su máquina. Por ejemplo, para la región de dallas: vpn.dal.softlayer.com_

_**Username:** Número de la cuenta seguido de un guión bajo y el correo asociado a la cuenta. Por ejemplo: 1234567_usuario@ibm.com_

_**Password:** Habilite la opción Save Password. Para crear esta contraseña ingrese en cloud.ibm.com, acceda a su cuenta, diríjase a la pestaña **Manage**, luego a **Access (IAM)**, luego en el menú izquierdo diríjase a **Users**, de click sobre su correo electronico y busque el campo **VPN Password**, modifíquelo y luego ingrese este valor en motion pro._

<p align="center">
<img width="500" alt="ContraseñaVPN" src="https://user-images.githubusercontent.com/60987042/100011189-60157100-2d9f-11eb-89fa-4db347c37d38.png">
</p>

_Despues de tener conectada la VPN mediante la herramienta de motion pro, debemos proseguir con la instalación y la adecuación de la maquina._

_La documentación completa de este proceso se encuentra  en IBM Cloud docs  y se puede ver en el siguiente link:_

```
https://cloud.ibm.com/docs/gateway-appliance?topic=gateway-appliance-order-byoa
```

### Paso 2 


_1.	Inicie sesión e ingrese desde la CLI de OpenShift al clúster en el que se va a trabajar._

_Para ingresar al clúster que tengamos aprovisionado en nuestra cuenta de IBM Cloud se deben realizar los siguientes pasos:_

_•	Ingresar a la plataforma de IBM cloud con sus credenciales de inicio de sesión, lo puede hacer desde el siguiente link:_

```
https://cloud.ibm.com/
```

_•	Diríjase al resource list._
_Primero debe dar clic en el navigation menu y luego donde dice Resource list, como se puede ver en la siguiente imagen:_

<p align="center">
<img width="696" alt="7" src="https://user-images.githubusercontent.com/60987042/76996077-da434b00-691e-11ea-92be-558da48f7d97.PNG">
</p>

_•	Diríjase a la sección de clústers y dar clic en el que se desea acceder._

_•	Se da clic en el botón OpenShift web console._

### Haga 'login' en el cluster de Open Shift (ROKS) desde la linea de comando 📦

_•	Ahora en la parte superior derecha se da clic sobre el ID del correo con el que ingresamos y luego en la sección que dice Copy Login Command._

<p align="center">
<img width="144" alt="1" src="https://user-images.githubusercontent.com/60987042/76917049-53479180-6890-11ea-91a1-b2c2c9213729.PNG">
</p>
_•	Y por último volvemos a la terminal que se estaba utilizando pegamos y damos enter._

### Cree un nuevo proyecto en Open Shift para desplegar las aplicaciones 📦

_2.	Cree un nuevo proyecto en el cluster de la siguiente manera:_
```
oc new-project <projectname>
```
_**Nota:** Para el **projectname** coloque **openshift + las iniciales de su nombre y apellido.**_

_3.	Acceda al proyecto que acabo de crear de la siguiente manera:_

```
oc project <projectname>
```




## Referencias

La documentación en linea de IBM Cloud Red Hat OpenShift Managed, se encuentra en el siguiente enlace:

https://cloud.ibm.com/docs/openshift?topic=openshift-getting-started

En la siguiente página se encuentra la información de administración y configuración de Open Shift 3.11.

https://access.redhat.com/documentation/en-us/openshift_container_platform/3.11/

## Autores ✒️

_Equipo IBM Cloud Tech sales Colombia._
