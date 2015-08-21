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

Para instalar node se puede hacerlo por medio de la distribución de Linux que uses, por NVM,
o buildeando a partir de los fuentes. 

<blockquote>
Aclaración: Para la materia no es necesario instalarse NVM, lo recomendado es mediante
la instalación de acuerdo a la distribución Linux que tengas. Los otros dos métodos son 
adicionales que pueden ser interesantes si queres saber otras maneras de instalar node 
o incluso de instalarlo cuando se quiere instalar múltiples versiones de Node.js o 
la última existente.
</blockquote>

# Instalando por medio del administrador de paquetes Linux 

## Para distros basadas en Debian/Ubuntu

#### Incluye a Linux Mint, elementaryOS

Las últimas versiones de node (Node >= 0.12) no están en los repositorios principales, por lo
que si quieren tener la última versión, hay que usar el repositorio de nodesource.com

###En ubuntu:

{% highlight bash %}
curl --silent --location https://deb.nodesource.com/setup_0.12 | sudo bash -
{% endhighlight %}

Después instalar con apt:

{% highlight bash %}
sudo apt-get install --yes nodejs
{% endhighlight %}

###En Debian y derivados

{% highlight bash %}
apt-get install curl
curl --silent --location https://deb.nodesource.com/setup_0.12 | bash -
{% endhighlight %}

Despues instalar con apt

{% highlight bash %}
apt-get install --yes nodejs
{% endhighlight %}

Opcional: install build tools

###En el caso que se quiera usar la versión 0.10

En Ubuntu o Debian:

{% highlight bash %}
sudo apt-get git curl nodejs npm
{% endhighlight %}

####Instalando build essential

Para instalar addons nativos de npm se necesita instalar también build tools:
 
tanto en Debian como en Ubuntu hacer:

{% highlight bash %}
apt-get install --yes build-essential
{% endhighlight %}

##Enterprise Linux and Fedora

####Incluyendo a Red Hat® Enterprise Linux® / RHEL, CentOS y Fedora.

Node.js esta disponible en el repositorio de binarios de Fedorea y en NodeSource Enterprise 

Correr como root en RHEL, CentOS o Fedora:

{% highlight bash %}
curl --silent --location https://rpm.nodesource.com/setup | bash -
{% endhighlight %}

Y luego con yum

{% highlight bash %}
yum -y install nodejs 
{% endhighlight %}

Para instalar addons nativos de npm se necesita instalar build tools:

{% highlight bash %}
yum install gcc-c++ make
{% endhighlight %}

#Para Fedora >= 18 

Hay un Node.js y npm oficial en el repositorio ofical. Instalar haciendo: 

{% highlight bash %}
sudo yum install nodejs npm
{% endhighlight %}

En caso de que quieran la última versión instalar de updates-testing.

Gente que usa RHEL y CentOD pueden instalar Node.js y npm de EPEL haciendo:

{% highlight bash %}
sudo yum install nodejs npm --enablerepo=epel
{% endhighlight %}

En caso de que quieran la última versión instalar de epel-testing.


##Gentoo

Node.js esta disponible en emerge

{% highlight bash %}
emerge nodejs
{% endhighlight %}

##OpenSUSE and SLE

Disponible en paquetes RPM packages para openSUSE 11.4, 12.1, 12.2, 12.3, 13.1, 
Factory y Tumbleweed.

Instalando en openSUSE 13.1:

{% highlight bash %}
sudo zypper ar \
  http://download.opensuse.org/repositories/devel:/languages:/nodejs/openSUSE_13.1/ \
  Node.js
sudo zypper in nodejs nodejs-devel
{% endhighlight %}

##Arch Linux

Node.js y npm estan disponibles en pacman

{% highlight bash %}
pacman -S nodejs npm
{% endhighlight %}

##FreeBSD and OpenBSD

Node.js esta disponible a traces del sistema ports

{% highlight bash %}
/usr/ports/www/node
{% endhighlight %}

Instalando por medio de pkg_add en FreeBSD:

{% highlight bash %}
pkg_add -r node-devel
{% endhighlight %}

O usando pkg-ng en FreeBSD

{% highlight bash %}
pkg install node
{% endhighlight %}

##OSX

###Mediante el último binario en nodejs.org:

{% highlight bash %}
curl "https://nodejs.org/dist/latest/node-${VERSION:-$(wget -qO- https://nodejs.org/dist/latest/ | sed -nr 's|.*>node-(.*)\.pkg</a>.*|\1|p')}.pkg" > "$HOME/Downloads/node-latest.pkg" && sudo installer -store -pkg "$HOME/Downloads/node-latest.pkg" -target "/"
{% endhighlight %}

###Homebrew:

{% highlight bash %}
brew install node
{% endhighlight %}

#Buildeando del último release

Si bien no es necesario para la materia tener la última versión de Node.js aparte de la que podríamos
tener de un binario de nuestra disto linux, aca esta el script para instalarlo de los fuentes

{% highlight bash %}
echo 'export PATH=$HOME/local/bin:$PATH' >> ~/.bashrc
. ~/.bashrc
mkdir ~/local
mkdir ~/node-latest-install
cd ~/node-latest-install
curl http://nodejs.org/dist/node-latest.tar.gz | tar xz --strip-components=1
./configure --prefix=~/local
make install 
curl https://www.npmjs.org/install.sh | sh
{% endhighlight %}

# Por medio de NVM

Que es NVM? Node Version Manager (NVM) es una herramienta para instalar distintas versiones de
Node.JS en una máquina linux. Para usar NVM tenes que tener como requisito git y curl instalados
 
<blockquote>
Aclaración: No es necesario este método de instalación para la cursada ya que solo necesitaremos
una versión de Node.js y no es necesario la última.
</blockquote>
 
Una vez instalado git y curl ejecutar

{% highlight bash %}
curl https://raw.github.com/creationix/nvm/master/install.sh | sh
{% endhighlight %}

Para probar que nvm funciona tipear nvm en la terminal. Si no se obtiene un 
error del tipo *command not found*, entonces no se instalo correctamente NVM.

Una vez instalado NVM hacer:

{% highlight bash %}
nvm install 0.10.38
{% endhighlight %}

Luego hacer un node -v y les debería mostrar esta misma versión que instalaron


# Actualizar npm

A veces no se instala la última versión cuando se usa un administrador de paquetes. Para actualizar
npm ejecutar: 

{% highlight bash %}
npm install -g npm
{% endhighlight %}

# Como iniciar un proyecto Node.js + Express

Para crear un proeycto simple en Express, hay que hacer algo como lo siguiente:

{% highlight bash %}
mkdir pepita-express
cd pepita-express
npm init
{% endhighlight %}

A partir de este punto se va a crear un package.json que contiene toda la metadata, incluyendo
las dependencias que tendrá nuestra aplicacion Express, estas preguntas estan enmarcadas entre
paréntesis que en caso de que no se complete nada será tomado como el valor por defecto.
Se puede dar todos los valores por defecto a excepción de *entry point* al que le daremos el valor
de app.js, porque esto? Porque es el nombre por convención que se le da a una aplicación Express

entonces:

*entry point: (index.js) app.js*

Ahora falta instalar Express y guardarlo en la lista de dependencias, para hacer ambas cosas
ejecutar:

{% highlight bash %}
npm install express --save
{% endhighlight %}

Si queremos instalar otras dependencias podemos hacerlo por medio de npm o modificando directamente
el package.json, si lo hacemos de esta segunda manera siempre tendremos que luego ejecutar en el 
directorio raiz:

{% highlight bash %}
npm install
{% endhighlight %}

Con esto instalará localmente las dependencias de nuestro proyecto

Para más referencias ir a la página de [Express.js](http://expressjs.com/starter/installing.html)


Un ejemplo base en Node.js y Express esta en este [repo](https://github.com/arquitecturas-concurrentes/iasc-expressstub-nodejs).





