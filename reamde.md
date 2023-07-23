## Datos previos
``````
cat /etc/os-release
``````
VPS "Ubuntu 22.04.1 LTS"
``````
docker --version
``````
Docker version 24.0.4,
``````
kubectl version --output=json --client
``````
Client Version: v1.27.4
``````
Minikube version
``````
minikube version: v1.31.1


Clonar repo



## Levantar un container de jenkins, sonarqube y nexus

``````
docker compose up -d
`````` 
Habilitar un shell interactivo dentro de un contenedor Docker.

````` 
docker exec -it --user=root jenkinsdocker /bin/bash
`````` 

E instalar kubectl al interior de este

Install kubectl from https://k8s-docs.netlify.app/en/docs/tasks/tools/install-kubectl/
````` 
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
````` 
````` 
chmod +x ./kubectl
````` 
````` 
sudo mv ./kubectl /usr/local/bin/kubectl
````` 
````` 
kubectl version --client
````` 

## Acceder a Jenkins 

Ahora se puede acceder a Jenkins desde la ruta de Minikube: 

http://localhost:8080

Instalación inicial. Necesitamos poner la clave inicial: 
Ruta var/jenkins_home/secrets/initialAdminPassword 

Si este archivo no se ha creado en la ruta en cuestión, obtenerlo utilizando los siguientes comandos (dentro del contenedor, donde aún estamos): 
```console
cat var/jenkins_home/secrets/initialAdminPassword
```
Instalar plugins predefinidos. 

Salir del contenedor: 
```console
exit
```
Una vez la instalación este completa. Instalar el plugin Kubernetes

![Alt text](images/PLUGIN.PNG) 