# Openhab
Servidor web que habilita la conexión a un sistema knx de instalación domótica particular.

## Instalar OpenHab

La instalación que se describe a continuación está optimizada para ser realizada sobre una raspberry pi con el sistema operativo debian

```console
sudo echo "deb http://dl.bintray.com/openhab/apt-repo stable main" |
sudo tee /etc/apt/source.list.d/openhab.list"

sudo apt-get update
```
Si da error por "llave púlica no disponible", hacer:

```console
gpg --keyserver keyserver.ubuntu.com --recv [NO_PUBKEY indicado en el error al actualizar]
```

Instalar openhab:

```console
sudo apt-get install openhab -runtime -y --force-yes
```

Para hacer que arranque openhab en el inicio:

```console
sudo update-rc.d openhab defaults
```

Para arrancar openhab:

```console
sudo /etc/init-d/openhab start
```

## Añadir addons.

Para buscar addons:

```console
sudo apt-cache search openhab
```

Para instalar uno:

```console
sudo apt-get install [nombre del addon que se quiere instalar]
```

Por ejemplo, el addon de KNX: openhab-addob-binding-knx

## Incluir usuarios

Editar el fichero de usuarios con:

```console
sudo nano /etc/openhab/configurations/user.cfg
```

Para añadir un usuario, incluir en una nueva linea:

```bash
[usuario]=[password]
```

Actualizar la seguridad con:

```console
sudo nano /etc/openhab/configurations/openhab.cfg
```

Poner seguridad a ```ON```.
