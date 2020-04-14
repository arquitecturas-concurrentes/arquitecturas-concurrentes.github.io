---
layout: guia
description: Guia para instalar python 3 con virtual env
resource: false
---

## Requisitos

- Tener instalado python 3 

## Instalacion 

### Instalar **pip** primero

```bash
  sudo apt-get install python3-pip
```

### Despues instalamos **virtualenv** con pip3

```bash
  sudo pip3 install virtualenv 
```

### Ahora creamos un entorno virtual con python 3

```bash
    virtualenv -p python3 myenv
```

>En vez de **venv**, se puede utilizar cualquier nombre

### Despues solo hay que activar el entorno    

```bash    
    source venv/bin/activate
```

### Para salir o desactivar el entorno:

```bash
    deactivate
```

### En vez de activar el entorno podemos utilizar el siguiente comando una vez que tenemos listo el virtualenv
    python -m venv myenv
