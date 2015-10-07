---
layout: page
description: Guia de Elixir
permalink: /guias/elixir/
---

#Como instalar Elixir

##Mac OS X

### Homebrew

Update your homebrew to latest: 

{% highlight bash %}
brew update
{% endhighlight %}


Run 

{% highlight bash %}
brew install elixir
{% endhighlight %}
  

##Macports

Run 

{% highlight bash %}
sudo port install elixir
{% endhighlight %}

##Unix (and Unix-like)

###Arch Linux (Community repo)

Run 

pacman -S elixir

###OpenSUSE (and SLES 11 SP3+)
  
Add Erlang devel repo: 

{% highlight bash %}
zypper ar -f obs://devel:languages:erlang/ erlang
{% endhighlight %}

Run: 

{% highlight bash %}
zypper in elixir
{% endhighlight %}

###Gentoo

Run: 

{% highlight bash %}
emerge --ask dev-lang/elixir
{% endhighlight %}

###Fedora 17 and newer
  
Run:

{% highlight bash %}
yum install elixir
{% endhighlight %}

###FreeBSD

From ports: 

{% highlight bash %}
cd /usr/ports/lang/elixir && make install clean
{% endhighlight %}

From pkg: 

{% highlight bash %}
pkg install elixir
{% endhighlight %}

###Ubuntu 12.04 and 14.04 / Debian 7

Add Erlang Solutions repo: 

{% highlight bash %}
wget https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb && sudo dpkg -i erlang-solutions_1.0_all.deb
{% endhighlight %}

Run: 

{% highlight bash %}
sudo apt-get update
{% endhighlight %}
  
Run: 

{% highlight bash %}
sudo apt-get install elixir
{% endhighlight %}


##Windows

###Web installer

Download the installer
Click next, next, …, finish

###Chocolatey
  
cinst elixir
