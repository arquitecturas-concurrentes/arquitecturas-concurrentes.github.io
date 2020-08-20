---
layout: guia
description: Guia para armar una VM de Virtualbox
resource: false
---

## Alternativa

#### Importante!

Como alternativa tenemos una VM de lubuntu ya creada con todo lo que ncesitan instalado, que pueden ver de bajarlo de este link de [google drive](https://drive.google.com/file/d/1eDaY7klFbKgBannhyN0DWPqb9xrc3jI1/view?usp=drivesdk)

MD5 del archivo descomprimido: `3edc02cbd922f73d0113fed7f162a6a3  Lubuntu.vhd`


## Prerequisitos

Necesitamos tener instalado obivamente virtualbox en nuestra maquina, podemos bajarlo de [aqui](https://www.virtualbox.org/wiki/Downloads).

Tambien necesitamos una imagen de ubuntu/lubuntu. Recomendamos el ultimo, y podemos encontrar el mismo en el siguiente [link](https://lubuntu.net/downloads/) o bajar la version 19.10 directamente de [este link](http://cdimage.ubuntu.com/lubuntu/releases/19.10/release/lubuntu-19.10-desktop-amd64.iso)

## Seteo de la maquina virtual

Una vez que tenemos virtual box instalado con la imagen de lubuntu ya descargada, hay que inicializar virtuabox y crear una nueva maquina virtual. 

![](/img/guias/vm0.jpg)

Hay que crear una imagen de ubuntu x64, con al menos 10/15gb de espacio y la maxima cantidad de procesadores que pueda emular nuestra maquina. Una vez que tenemos creada la maquina virtual vamos a poder verla ya en el menu principal de virtualbox

![](/img/guias/vm1.jpg)

Despues de esto podemos tan solo levantar la VM y nos pedira seguramente el disco de incio, si es asi aceptamos y buscamos el .iso con la imagen de lubuntu.

Sino lo que hay que hacer es ir a **Settings/Storage** y en esa seccion seleccionar un nuevo medio optico para nuestro controlador IDE ya creado por virtualbox para nuestra VM

![](/img/guias/vm2.jpg)

De ahi podemos ya seleccionar el .iso y deberiamos ya poder seleccionar el idioma y despues de eso una vez que estemos en el escritorio de lubuntu, de instalar el sistema operativo en el espacio que reservamos en la maquina virtual, de esa manera no vamos a perder los datos una vez que apaguemos la maquina virtual.

![](/img/guias/vm3.jpg)

Una vez que se haya instalado el sistema operativo, despues vamos a poder reiniciar la maquina y si queremos el de sacar el .iso que puede quedar aun montado en el controlador IDE.

Una vez que reinciamos la VM, ya vamos a poder iniciar la sesion de nuestro usuario

![](/img/guias/vm4.jpg)

Ahora solo necesitamos instalar las dependencias que necesitamos para la practica


## Instalacion de dependencias para cada una de las practicas

### Instalando git, code, atom e insomnia

Como siempre vamos a estar usando git, instalamos ese paquete, junto con curl


Despues de eso, pueden usar cualquier editor o IDE, eso queda sujeto a las preferencias que tengan, dejamos las guias para instalar [VisualStudioCode](https://code.visualstudio.com/docs/setup/linux) y [atom](https://flight-manual.atom.io/getting-started/sections/installing-atom/)

Para algunas practicas tal vez quieran utilizar un cliente para hacer requests como Insomnia, por ejemplo, en el que dejamos las instrucciones para instalarlo [aqui](https://support.insomnia.rest/article/23-installation#linux).

### Ruby

Para ruby vamos a estar utilizando [rvm](https://rvm.io).

dejamos aca algunos pasos para instalarlo

```bash
gpg --keyserver hkp://pool.sks-keyservers.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
\curl -sSL https://get.rvm.io | bash
echo "source $HOME/.rvm/scripts/rvm" >> ~/.bash_profile
```

aunque tambien pueden ver como instalarlo [aca](https://rvm.io/rvm/install)

### Node

Para node pueden ver nuestra guia [aqui](/guias/node).

### Elixir

Para Elixir pueden ver nuestra guia de instalacion [aqui](/guias/elixir).

### Haskell

solo hay que instalar stack, pueden ver la guia de instalacion de stack [aqui](https://docs.haskellstack.org/en/stable/install_and_upgrade/)
