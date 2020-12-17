# Gateway-Appliance-BYOL-VMWare


# GUIA DE INSTALACIÓN DE SISTEMA OPERATIVO EN GATEWAY APPLIANCE


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


_Para poder acceder a la plataforma de configuracion y administración del Gateway Appliance, debemos seguir los siguientes pasos:_

_•	Ingresar a la plataforma de IBM cloud con sus credenciales de inicio de sesión, lo puede hacer desde el siguiente link:_

```
https://cloud.ibm.com/
```

_•	Diríjase a la sección de **Classic infrastructure.**_

<p align="center">
  
</p>

_• Ingrese a la sección de **Network** y luego en la sección de **Gateway Appliance.**_

<p align="center">
  
</p>

_• De click sobre el **nombre de la máquina** y en la sección **hardware** vuelva a dar click sobre el **nombre de la máquina.**_

<p align="center">
  
</p>

_• En la sección de **Actions** abrimos la que dice **KVM Console*_

<p align="center">
  
</p>
_Al dar clic en esta sección, nos redireccionará a una pestaña de configuración del servidor virtual._

_• Para poder ingresar a la plataforma de supermicro (Plataforma de acceso y configuración de la máquina) debemos tener en cuenta las credenciales de ingreso que podrá encontrar en **Remote Management.**_

<p align="center">
  
</p>

_Al ingresar las credenciales nos redireccionara a la ventana inicial de supermicro, y desde aquí podremos tener un escritorio remoto al servidor. Pero también nos da una opción para subir una nueva imagen .iso._

### Paso 3

_Para subir la imagen .iso al Gateway Appliance, debemos seguir los siguientes pasos:_

_• Al ingresar ala plataforma de supermicro, debe dar click en **Remote control** y luego en **Console Redirection.**_

<p align="center">
<img width="667" alt="Supermicro" src="https://user-images.githubusercontent.com/60987042/100012996-26923500-2da2-11eb-8115-2d1efdec305e.PNG">    
</p>

_• Al terminar el paso anterior se nos descargará a nuestro ordenador un archivo con extensión **.jnlp** el cual abriremos con plugin Ice-tea que instalamos previamente._

_• Al abrir el archivo con extencion **.jnlp** se nos abre una nueva ventana en la cual podemos ver como escritorio remoto nuestro servidor, pero también podremos cargar un nuevo .iso para iniciarlo desde el Boot de la máquina e instalarlo._

_• En esta nueva ventana debemos dar click en la pestaña **Virtual media** y luego en la que dice **Virtual storage.**_

<p align="center">
<img width="660" alt="VirtualStorage" src="https://user-images.githubusercontent.com/60987042/100013438-d2d41b80-2da2-11eb-88a8-9cb09b4b1f96.PNG">  
</p>

_• Al terminar el paso anterior se nos abre la ventana que vemos a continuación y aquí es donde podremos subir nuestro .iso que tenemos guardado en el pc local. _

<p align="center">
<img width="445" alt="Subir_iso" src="https://user-images.githubusercontent.com/60987042/100013468-dd8eb080-2da2-11eb-8eec-0b5cf7578839.PNG">  
</p>

_• Cuando se selecciona el .iso debemos dar click en Plug in para subirla la imagen y lo último que tenemos que hacer es ingresar a nuestra máquina virtual desde un escritorio remoto e iniciar la maquina desde el Boot con la imagen que acabamos de subir y seguir todas las instrucciones de instalación._

**NOTA: Finalmente se accede al boot de la máquina donde selecciona el .iso de arranque para la máquina**



## Referencias



## Autores ✒️

_Equipo IBM Cloud Tech sales Colombia._
