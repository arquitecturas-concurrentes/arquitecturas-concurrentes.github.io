---
layout: page
description: Guia de Node.js
permalink: /guias/node/
---

# Prerequisitos 

* Tener una máquina con Linux
    - En caso de tener una máquina con Windows, instalar Linux o una VM con Linux.
* Tener instalado git
* Tener instalado curl 


# Instalando Node

Para instalar node se puede hacerlo por medio de la distribución de Linux que uses, por NVM,
o buildeando a partir de los fuentes. La opción mas fácil es la primera. 

## Instalando por medio del administrador de paquetes Linux 

### Para distros basadas en Debian/Ubuntu

> Incluye a Linux Mint, elementaryOS

Las últimas versiones de node (Node >= 0.12) no están en los repositorios principales, por lo
que si quieren tener la última versión, hay que usar el repositorio de nodesource.com

{% highlight bash %}
curl --silent --location https://deb.nodesource.com/setup_0.12 | sudo bash -
{% endhighlight %}

Luego, instalar normalmente con apt-get

{% highlight bash %}
sudo apt-get install --yes nodejs npm build-essential
{% endhighlight %}

En caso de que instalen por nodesource.com node y despues cuando quieran hacer apt-get install npm, les falle, lo que pueden hacer es instalar npm por source haciendo

{% highlight bash %}
curl -L https://www.npmjs.org/install.sh| sh
{% endhighlight %}

### Otras distribuciones

Si tenés Gentoo, Arch, RHEL, Suse... asumimos que sos grande y podés investigar vos mismo como instalarlo :P. 

## Por medio de NVM

<blockquote>
Aclaración: No es necesario este método de instalación para la cursada ya que solo necesitaremos
una versión de Node.js y no es necesario la última.
</blockquote>
 

Que es NVM? Node Version Manager (NVM) es una herramienta para instalar distintas versiones de
Node.JS en una máquina linux. Para usar NVM tenes que tener como requisito git y curl instalados
 
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

## Actualizar npm

A veces no se instala la última versión cuando se usa un administrador de paquetes. Para actualizar
npm ejecutar: 

{% highlight bash %}
npm install -g npm
{% endhighlight %}

# Instalando Mocha

Mocha es un framework de test común en JS. Si bien debería ser una dependencia de tu proyecto, a veces es cómodo tenerlo instalado globalmente para hacer pruebas rápidas. 

{% highlight bash %}
npm install -g mocha
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

#Extra

[Como instalar Node.js con docker](https://programmaticponderings.wordpress.com/2014/11/17/install-the-latest-versions-of-node-js-and-npm-into-a-docker-ubuntu-container-with-or-without-the-need-for-root-access-easily-update-both-applications-to-the-latest-versions/) 

