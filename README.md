# Gateway-Appliance-BYOL-VMWare


# GUIA DE INSTALACIÓN DE CLOUDGUARD DENTRO DE UN GATEWAY APPLIANCE

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

## MONTAJE DE LA IMAGEN .ISO DE VMWARE ESXI AL GATEWAY APPLIANCE: 🚀

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


## Crear maquina virtual con CloudGuard dentro del VMWare ESXi: 🚀

### Paso 1
_Descargar el .iso de CloudGuard desde el siguiente link:_

```
https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk111841&partition=Basic&product=All
```
### Paso 2
_Crear un **Virtual Switch** dentro de MVware ESXi con las siguentes caracteristicas:_

<p align="center">
<img width="559" alt="vs" src="https://user-images.githubusercontent.com/60987042/103815974-33a57380-5032-11eb-9fbc-6a59275a1f22.PNG">
</p>

### Paso 3
_Crear un **Port Group** dentro de MVware ESXi con las siguentes caracteristicas:_

<p align="center">
<img width="521" alt="pg" src="https://user-images.githubusercontent.com/60987042/103816523-1ae98d80-5033-11eb-9e51-c7ae690e4181.PNG">
</p>

### Paso 4
_Crear una maquina virtual con la imagen .iso que descargamos en el paso 1, teniendo especial cuidado en la configuración:_

_**Para:**_

_**1. Select Creation Type**, se debe seleccionar la primera opción (Create a new virtual machine):_

<p align="center">
<img width="519" alt="p1" src="https://user-images.githubusercontent.com/60987042/103817008-e6c29c80-5033-11eb-897e-2dc43dc20a75.PNG">
</p>


_**2. Select a name and guest OS**, se debe seleccionar las siguentes opciones:_

<p align="center">
<img width="521" alt="p2" src="https://user-images.githubusercontent.com/60987042/103817442-b3ccd880-5034-11eb-95ce-2d8cefad18c5.PNG">
</p>

_**3. Select Storage**, es necesario seleccionar el Storage disponible para la instalación despues dar clic en Next:_

<p align="center">
<img width="522" alt="p3" src="https://user-images.githubusercontent.com/60987042/103817641-0e663480-5035-11eb-87fd-dbacfd22a0e0.PNG">
</p>


_**4. Customize Settings**, se debe seleccionar las siguentes opciones:_

_**CPU** = 2_

_**Hard Disk 1** = 50Gb_

_**Network Adapter 1** = Se debe seleccionar el que creamos mediante el **Port Group** con el nombre de publico_

_**CD/DVD Drive 1** = inicialmente se debe seleccionar la opción ""DataStore iso file"" y despues seleccionar la imagen .iso o subirla para poder elegirla._

<p align="center">
<img width="522" alt="p4" src="https://user-images.githubusercontent.com/60987042/103818383-70736980-5036-11eb-802d-9ef32e60718c.PNG">
</p>

_**5. Ready to Complete**, es el paso final para la creación de la maquina virtual y debemos dar clic en **Finish**._

<p align="center">
<img width="524" alt="p5" src="https://user-images.githubusercontent.com/60987042/103818569-ca742f00-5036-11eb-9ad3-5608345e1e4b.PNG">
</p>

### Paso 5

_Dado por terminado el paso # 4, se debe dirigir a la sección de maquinas virtuales y dar clic sobre la que lleva el nombre de **CloudGuard**:_

<p align="center">
<img width="521" alt="im" src="https://user-images.githubusercontent.com/60987042/103818875-50907580-5037-11eb-8597-1b8f2ebfed1c.PNG">
</p>

## Instalación de CloudGuard dentro del VMWare ESXi: 🚀

### Paso 1

_Al acceder a la maquina virtual, debe aparecer el menu de instalación de CloudGuard, en el cual debemos seleccionar la primera opción:_

<p align="center">
<img width="522" alt="mi" src="https://user-images.githubusercontent.com/60987042/103819198-f512b780-5037-11eb-98e1-2a54370670e9.PNG">
</p>

### Paso 2

_Cuando inicia el proceso de instalación, se van a mostrar un primer menú en el cual debemos seleccionar **OK**:_

<p align="center">
<img width="520" alt="i1" src="https://user-images.githubusercontent.com/60987042/103821071-7a4b9b80-503b-11eb-8c1c-ea931823a5df.PNG">
</p>

### Paso 3

_La primera configuración se nos va a pedir el proceso de instalación es la del idioma del teclado:_

<p align="center">
<img width="522" alt="i2" src="https://user-images.githubusercontent.com/60987042/103821202-b848bf80-503b-11eb-88ac-cc0dcfc8da99.PNG">
</p>

### Paso 4

_Despues del idioma del teclado, es necesario configurar la distribución del almacenamineto disponible y debe quedar asi:_

<p align="center">
<img width="523" alt="i3" src="https://user-images.githubusercontent.com/60987042/103821384-0eb5fe00-503c-11eb-9e9a-f4de5a77b05a.PNG">
</p>

### Paso 5

_Ahora, es necesario crear una contraseña para poder acceder al panel de administración y a la CLI de CloudGuard:_

<p align="center">
<img width="521" alt="i4" src="https://user-images.githubusercontent.com/60987042/103821532-59377a80-503c-11eb-95e1-80afd7a2e0c2.PNG">
</p>

### Paso 6

_Por ultimo, es necesario configurar una IP mediante la cual vamos a acceder al panel de administración del CloudGuard:_

_**Nota: La dirección IP que debemos colocar debe estar en la misma subnet publica o privada del Gateway Aplaince**_

<p align="center">
<img width="520" alt="i5" src="https://user-images.githubusercontent.com/60987042/103821739-d2cf6880-503c-11eb-808c-1790a53ecb9b.PNG">
</p>

### Paso 7

_Para completar la instalación de Cloud Guard, va a salir un mensaje final en el cual se pregunta si se quiere continuar el proceso de instalación y se debe selecionar la opcion **OK**_


<p align="center">
<img width="520" alt="i6" src="https://user-images.githubusercontent.com/60987042/103821939-30fc4b80-503d-11eb-9257-6c0be41b0429.PNG">
</p>

### Paso 7

_Como paso final, nos va a salir la IP en la que quedo configurado el panel de administración y un menu que nos pide reiniciar la maquinapara de esta manera concluir la instalación:_

<p align="center">
<img width="521" alt="i7" src="https://user-images.githubusercontent.com/60987042/103822303-dfa08c00-503d-11eb-82cf-43ab98714ed0.PNG">
</p>


## Configuración de CloudGuard: 🚀

### Paso 1

_Para iniciar con la configuración del CloudGuard, debemos ingresar a la IP que definimos para la administración desde un Browser:_

<p align="center">
<img width="523" alt="c1" src="https://user-images.githubusercontent.com/60987042/103823026-3a86b300-503f-11eb-8541-17cc13281e71.PNG">
</p>

### Paso 2

_Al acceder con nuestras credenciales, nos va a aparecer un menu de configuración en el que inicialmente se debe dar clic en next:_

<p align="center">
<img width="524" alt="c2" src="https://user-images.githubusercontent.com/60987042/103823245-b3860a80-503f-11eb-8c10-79991036bbe8.PNG">
</p>

### Paso 3

_Ahora, es necesario dar clic en continuar con la configuración del R80.10 (CloudGuard):_

<p align="center">
<img width="262" alt="c3" src="https://user-images.githubusercontent.com/60987042/103823618-6d7d7680-5040-11eb-910a-56fa2bea8159.PNG">
</p>

### Paso 4

_En Management Connection, dejamos la configuración que esta por default:_

<p align="center">
<img width="261" alt="c4" src="https://user-images.githubusercontent.com/60987042/103823809-cb11c300-5040-11eb-90c7-a3c0924495ca.PNG">
</p>

### Paso 5

_En device Information, cambiamos solamente el nombre que queremos que tenga la maquina de CloudGuard:_

<p align="center">
<img width="260" alt="c5" src="https://user-images.githubusercontent.com/60987042/103824195-6d31ab00-5041-11eb-9f28-b0404aa7627b.PNG">
</p>

### Paso 6

_En Data and Time settings, cambiamos si lo queremos la zona horaria que queremos que tenga la maquina de CloudGuard:_

<p align="center">
<img width="261" alt="c6" src="https://user-images.githubusercontent.com/60987042/103824408-d44f5f80-5041-11eb-8ab5-e1fd0b691655.PNG">
</p>

### Paso 7

_En installation type, selecionamos la primera opción:_

<p align="center">
<img width="262" alt="c7" src="https://user-images.githubusercontent.com/60987042/103824832-ad455d80-5042-11eb-9712-9a75f1c68616.PNG">
</p>

### Paso 8

_En products, selecionamos Security gateway y tambien security management:_

<p align="center">
<img width="263" alt="c8" src="https://user-images.githubusercontent.com/60987042/103824897-cfd77680-5042-11eb-9238-11152f7e90bd.PNG">
</p>

### Paso 9

_En Security mamagement, permitimos todas las IP:_

<p align="center">
<img width="261" alt="c9" src="https://user-images.githubusercontent.com/60987042/103824904-d239d080-5042-11eb-82a8-6efce256e5d5.PNG">
</p>

### Paso 10

_Para finalizar con el proceso de configuración damos clic en Finish:_

<p align="center">
<img width="262" alt="c10" src="https://user-images.githubusercontent.com/60987042/103824906-d534c100-5042-11eb-9d24-3186afa42d49.PNG">
</p>

### Paso 11

_Ahora, se nos pide autorización para aplicar las configuraciones que acabamos de realizar:_

<p align="center">
<img width="264" alt="c11" src="https://user-images.githubusercontent.com/60987042/103824912-d7971b00-5042-11eb-99c7-e0110f10ef4c.PNG">
</p>

### Paso 12

_Se iniciaran a aplicar las configuraciones y nos aparacera un porcentaje que lo indica:_

<p align="center">
<img width="261" alt="c12" src="https://user-images.githubusercontent.com/60987042/103824916-d9f97500-5042-11eb-8766-b423b48ae1cc.PNG">
</p>

### Paso 13

_Por ultimo nos va a pedir reiniciar la maquina para terminar el proceso:_

<p align="center">
<img width="294" alt="c13" src="https://user-images.githubusercontent.com/60987042/103824928-dc5bcf00-5042-11eb-9959-c715e3416c99.PNG">
</p>

## Acceso al panel de administración CloudGuard: 🚀

_Cuando la maquina se reinicie por completo nos debe aparecer nuevamente la panatalla principal y nos pedira realizar el login:_

<p align="center">
<img width="524" alt="ac1" src="https://user-images.githubusercontent.com/60987042/103826445-da930b00-5044-11eb-90b6-d4f653de9c00.PNG">
</p>

_Al acceder con nuestras credenciales de acceso, nos va a aparecer el panel de administración del CloudGuard:_

<p align="center">
<img width="592" alt="ac2" src="https://user-images.githubusercontent.com/60987042/103826453-dc5cce80-5044-11eb-8d28-3172b305b244.PNG">
</p>

## Autores ✒️

_Equipo IBM Cloud Tech sales Colombia._
