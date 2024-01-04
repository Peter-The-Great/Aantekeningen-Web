attach - Connect to a running
build - build an image from a docker file
exec - Run a command in a running conatiner 
push - Push an image or a repository to a registry
run -  Run a command in a new container

# docker attach
```c
docker run
```
![[85EBAD34-3A25-4636-9AED-E2920D5A7F70.jpeg]]
# docker composer
![[D1B8A55B-4737-445F-BD1B-DC942B7CF85A.jpeg]]

# yaml

![[202281C9-6430-4CB1-9733-C10B1998804B.jpeg]]

# Build docker file

```dockerfile
FROM node:alphine
COPY . /app
WORKDIR /app
CMD node app.js
```

![[2B0580B8-3EB5-4132-900A-F7F009B360F0.jpeg]]
Om ervoor te zorgen dat we met docker gaan bouwen moeten we dit doen:
```bash
docker build -t application-name
```


### Meer info
De **Docker CLI** is een robuuste tool die je helpt bij het beheren van containers en verschillende aspecten van de containeromgeving direct vanaf de opdrachtregel [1](https://www.docker.com/products/cli/). Met de CLI kun je taken zoals het maken, starten, stoppen en verwijderen van containers efficiënt uitvoeren, evenals het beheren van containerimages, netwerken en volumes [1](https://www.docker.com/products/cli/).

Hier zijn enkele belangrijke onderdelen van de Docker CLI:

- [**docker build**: Hiermee kun je een Docker-image bouwen vanuit een Dockerfile](https://docs.docker.com/engine/reference/commandline/cli/) [2](https://docs.docker.com/engine/reference/commandline/cli/).
- [**docker run**: Hiermee kun je een container starten op basis van een Docker-image](https://docs.docker.com/engine/reference/commandline/cli/) [2](https://docs.docker.com/engine/reference/commandline/cli/).
- [**docker stop**: Hiermee kun je een container stoppen die momenteel wordt uitgevoerd](https://docs.docker.com/engine/reference/commandline/cli/) [2](https://docs.docker.com/engine/reference/commandline/cli/).
- [**docker rm**: Hiermee kun je een container verwijderen die niet langer nodig is](https://docs.docker.com/engine/reference/commandline/cli/) [2](https://docs.docker.com/engine/reference/commandline/cli/).
- [**docker ps**: Hiermee kun je de status van alle actieve containers bekijken](https://docs.docker.com/engine/reference/commandline/cli/) [2](https://docs.docker.com/engine/reference/commandline/cli/).
