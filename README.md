# home-control



## Iniciar Raspberry pi

## Pasos para configurar webServer en Raspberry pi

### Instalar Apache:

Actualizar el sistema, desde la linea de comandos:

```console
sudo apt-get update
sudo apt-get upgrade
```

Instalar apache:

```console
sudo apt-get install apache2
```


### Añadir el grupo www-data

```console
sudo groupadd www-data
```

Es el grupo que usa el webserver. 

```console
sudo usermod -a -G www-data www-data
```


### Asignar IP estática a las Raspberry pi

Editar fichero interfaces:

```console
cd /etc/network
sudo nano interfaces
```

Cambiar:

```bash
iface eth0 inet dhcp
```

por:

```bash
iface eth0 inet static
address [ip estática que queremos asignar a nuestra raspberry pi]
netmask 255.255.255.0
gateway [ip del router]
```

Indicar a la raspberry donde encontrar el DNS:

```console
cd /etc
sudo nano resolv.conf
```

Indicar el nombre del servidor:

```bash
nameserver [ip del router]
```

Reiniciar la raspberry:

```console
sudo reboot 
```

### Cambiar autorizaciones sobre fichero / carpeta

```console
chmod ugo -w [fichero] 
```

"ugo" significa: 
u - Usuario
g - grupo de usuarios
o - Otros

### Cambiar clave a usuario

```console
sudo passwd [usuario] 
```

### Arrancar servicio ssh

Arrancar servicio ssh para conectarse desde otro ordenador a la raspberry.

```console
sudo service ssh start 
```

Para iniciar el servicio:

```console
sudo insserv ssh 
```



