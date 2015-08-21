---
layout: page
description: Guia de Node.js
permalink: /guias/node/
---

# Prerequisitos 

* Tener una máquina con Linux
    - En caso de tener una máquina con Windows, instalar Linux o una VM con Linux
* Tener instalado git
* Tener instalado curl (solo para aquellos que quieran instalar Node.JS por medio de NVM, 
vamos a explicar que es esto más adelante)


# Instalando Node

Para instalar node se puede hacerlo por medio de la distribución de Linux que uses o por NVM

# Instalando por medio del administrador de paquetes Linux 

## Para distros basadas en Debian/Ubuntu

#### Incluye a Linux Mint, elementaryOS

Las últimas versiones de node (Node >= 0.12) no están en los repositorios principales, por lo
que si quieren tener la última versión, hay que usar el repositorio de nodesource.com

###En ubuntu:

```
curl --silent --location https://deb.nodesource.com/setup_0.12 | sudo bash -
```

Después instalar con apt:

```
sudo apt-get install --yes nodejs
```

###En Debian y derivados

```
apt-get install curl
curl --silent --location https://deb.nodesource.com/setup_0.12 | bash -
```

Despues instalar con apt

```
apt-get install --yes nodejs
```

Opcional: install build tools

###En el caso que se quiera usar la versión 0.10

En Ubuntu o Debian:

```
sudo apt-get git curl nodejs npm
```

####Instalando build essential

Para instalar addons nativos de npm se necesita instalar también build tools:
 
tanto en Debian como en Ubuntu hacer:

```
apt-get install --yes build-essential
```

##Enterprise Linux and Fedora

####Incluyendo a Red Hat® Enterprise Linux® / RHEL, CentOS y Fedora.

Node.js esta disponible en el repositorio de binarios de Fedorea y en NodeSource Enterprise 

Correr como root en RHEL, CentOS o Fedora:

```
curl --silent --location https://rpm.nodesource.com/setup | bash -
```

Y luego con yum

```
yum -y install nodejs 
```

Para instalar addons nativos de npm se necesita instalar build tools:

```
yum install gcc-c++ make
```

#Para Fedora >= 18 

Hay un Node.js y npm oficial en el repositorio ofical. Instalar haciendo: 

```
sudo yum install nodejs npm
```

En caso de que quieran la última versión instalar de updates-testing.

Gente que usa RHEL y CentOD pueden instalar Node.js y npm de EPEL haciendo:

```
sudo yum install nodejs npm --enablerepo=epel
```

En caso de que quieran la última versión instalar de epel-testing.


##Gentoo

Node.js esta disponible en emerge

```
emerge nodejs
```

##OpenSUSE and SLE

Disponible en paquetes RPM packages para openSUSE 11.4, 12.1, 12.2, 12.3, 13.1, 
Factory y Tumbleweed.

Instalando en openSUSE 13.1:

```
sudo zypper ar \
  http://download.opensuse.org/repositories/devel:/languages:/nodejs/openSUSE_13.1/ \
  Node.js
sudo zypper in nodejs nodejs-devel
```

##Arch Linux

Node.js y npm estan disponibles en pacman

```
pacman -S nodejs npm
```

##FreeBSD and OpenBSD

Node.js esta disponible a traces del sistema ports

```
/usr/ports/www/node
```

Instalando por medio de pkg_add en FreeBSD:

```
pkg_add -r node-devel
```

O usando pkg-ng en FreeBSD

```
pkg install node
```

##OSX

###Mediante el último binario en nodejs.org:

```
curl "https://nodejs.org/dist/latest/node-${VERSION:-$(wget -qO- https://nodejs.org/dist/latest/ | sed -nr 's|.*>node-(.*)\.pkg</a>.*|\1|p')}.pkg" > "$HOME/Downloads/node-latest.pkg" && sudo installer -store -pkg "$HOME/Downloads/node-latest.pkg" -target "/"
```

###Homebrew:

```
brew install node
```

# Por medio de NVM

Que es NVM? Node Version Manager (NVM) es una herramienta para instalar distintas versiones de
Node.JS en una máquina linux. Para usar NVM tenes que tener como requisito git y curl instalados
 
Una vez instalado git y curl ejecutar

``` 
curl https://raw.github.com/creationix/nvm/master/install.sh | sh
```

Para probar que nvm funciona tipear nvm en la terminal. Si no se obtiene un 
error del tipo *command not found*, entonces no se instalo correctamente NVM.

Una vez instalado NVM hacer:

```
nvm install 0.10.38
```

Luego hacer un node -v y les debería mostrar esta misma versión que instalaron


# Actualizar npm

A veces no se instala la última versión cuando se usa un administrador de paquetes. Para actualizar
npm ejecutar: 

```
npm install -g npm
```

# Instalando Express

Express es un framework web para Node. Es minimalista y flexible. Para instalar Express
hay que instalar la dependencia por medio de npm, simplemente hay que ejecutar:

```
npm install -g express
```

# Como iniciar un proyecto Node.js + Express

Para crear un proeycto simple en Express, hay que hacer algo como lo siguiente:

```
mkdir pepita-express
cd pepita-express
npm init
```

A partir de este punto se va a crear un package.json que contiene toda la metadata, incluyendo
las dependencias que tendrá nuestra aplicacion Express, estas preguntas estan enmarcadas entre
paréntesis que en caso de que no se complete nada será tomado como el valor por defecto.
Se puede dar todos los valores por defecto a excepción de *entry point* al que le daremos el valor
de app.js, porque esto? Porque es el nombre por convención que se le da a una aplicación Express

entonces:

*entry point: (index.js) app.js*

Ahora falta instalar Express y guardarlo en la lista de dependencias, para hacer ambas cosas
ejecutar:

```
npm install express --save
```

Si queremos instalar otras dependencias podemos hacerlo por medio de npm o modificando directamente
el package.json, si lo hacemos de esta segunda manera siempre tendremos que luego ejecutar en el 
directorio raiz:

```
npm install
```

Con esto instalará localmente las dependencias de nuestro proyecto

Para más referencias ir a la página de [Express.js](http://expressjs.com/starter/installing.html)


Un ejemplo base en Node.js y Express esta en este [repo](https://github.com/arquitecturas-concurrentes/iasc-expressstub-nodejs).





