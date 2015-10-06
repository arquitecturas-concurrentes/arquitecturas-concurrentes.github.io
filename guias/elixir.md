#Como instalar Elixir



##Mac OS X

* Homebrew
  
  Update your homebrew to latest: brew update
  Run: brew install elixir

##Macports
  Run: sudo port install elixir

##Unix (and Unix-like)

* Arch Linux (Community repo)
    Run: pacman -S elixir

*openSUSE (and SLES 11 SP3+)
  Add Erlang devel repo: zypper ar -f obs://devel:languages:erlang/ erlang
  Run: zypper in elixir

* Gentoo
  Run: emerge --ask dev-lang/elixir

* Fedora 17 and newer
  Run: yum install elixir

* FreeBSD
  From ports: cd /usr/ports/lang/elixir && make install clean
  From pkg: pkg install elixir

*Ubuntu 12.04 and 14.04 / Debian 7

  Add Erlang Solutions repo: wget https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb && sudo dpkg -i erlang-solutions_1.0_all.deb
  Run: sudo apt-get update
  Run: sudo apt-get install elixir

##Windows

* Web installer
  Download the installer
  Click next, next, …, finish

* Chocolatey
  cinst elixir
