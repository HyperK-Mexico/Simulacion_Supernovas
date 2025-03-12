# Instalacion de Dockers
Docker es una plataforma que permite crear, distribuir y ejecutar aplicaciones en contenedores, permitiendo su ejecucion en cualquier sistema compatible. https://hub.docker.com/}
Utilizando esta herramienta el usuario podra utilizar las herramientas de simulacion de supernovas en cualquier lugar sin necesidad de tener linux.

# Instalacion en Linux 

Actualizamos los repositorios y requerimientos de linux en la terminal con el siguiente comando.

```sh
$ sudo apt update
$ sudo apt install apt-transport-https ca-certificates curl software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudp apt-key add -
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```
Finalizando, se vuelve actualizar los repositorios.
```sh
$ sudo apt update
```
Para instalar dockers utilizamos lo siguiente:
```sh
$ sudo apt install docker-ce
```
Para checar el estatus de docker, empleamos el siguiente comando.
```sh
$ sudo systemctl status docker
```
Si el estatus te menciona "active (running)", docker funciona de maravilla.

(opcional), si el usurio no requiere que este pidiendo su contraseña cada vez que entra a dockers, se aplican los siguientes comandos:
```sh
$ sudo usermmod -aG docker ${USER}
$ su - ${USER}
$ id -nG
```
Si sale todo bien, para ver si ha funcionado lo que hicimos anteriormente, utilizamos lo siguiente:
```sh
$ docker ps
```
y listo, ya tienes instalado dockers, checa los demas readme par ver la instalacion del contenedor, y el ejemplo de la simulacion.
# Instalacion en Windows
Si el usurio requiere la instalacion en el sistema operativo windows, siga los pasos de la pagina oficial de dockers https://docs.docker.com/desktop/setup/install/windows-install/
