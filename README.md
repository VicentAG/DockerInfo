# Docker
![DockerImage](./Images/Docker.png)
## Que es docker?

Docker es un sistema operativo (o runtime) para contenedores. El motor de Docker se instala en cada servidor en el que desee ejecutar contenedores y proporciona un conjunto sencillo de comandos que puede utilizar para crear, iniciar o detener contenedores.

## Indice

- [Instalación](#instalación)
- [Uso](#uso)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Contribución](#contribución)
- [Licencia](#licencia)

## Instalación

Para instalar dockerejecutaremos los siguentes comandos:

- Primero, actualice su lista de paquetes existente:
```bash
sudo apt update
```

- A continuación, instale algunos paquetes de requisitos previos que permitan a apt usar paquetes a través de HTTPS:
```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

- Luego, añada la clave de GPG para el repositorio oficial de Docker en su sistema:
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

- Agregue el repositorio de Docker a las fuentes de APT:
```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```

- A continuación, actualice el paquete de base de datos con los paquetes de Docker del repositorio recién agregado:
```bash
sudo apt update
```

- Asegúrese de estar a punto de realizar la instalación desde el repositorio de Docker en lugar del repositorio predeterminado de Ubuntu:
```bash
apt-cache policy docker-ce
```

- Si bien el número de versión de Docker puede ser distinto, verá un resultado como el siguiente:
```bash
docker-ce:
  Installed: (none)
  Candidate: 5:19.03.9~3-0~ubuntu-focal
  Version table:
     5:19.03.9~3-0~ubuntu-focal 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
```

- Observe que docker-ce no está instalado, pero la opción más viable para la instalación es del repositorio de Docker para Ubuntu 20.04 (focal).

- Por último, instale Docker:
```bash
sudo apt install docker-ce
```

- Con esto, Docker quedará instalado, el demonio se iniciará y el proceso se habilitará para ejecutarse en el inicio. Compruebe que funcione:
```bash
sudo systemctl status docker
```

- El resultado debe ser similar al siguiente, y mostrar que el servicio está activo y en ejecución:
```bash
Output
● docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2020-05-19 17:00:41 UTC; 17s ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 24321 (dockerd)
      Tasks: 8
     Memory: 46.4M
     CGroup: /system.slice/docker.service
             └─24321 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
```