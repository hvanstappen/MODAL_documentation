## **Installatie op Linux** 

### **Installatie Docker** 

* Installeer [Docker Engine](https://docs.docker.com/engine/install/ubuntu/%20) of [Docker Desktop](https://docs.docker.com/desktop/setup/install/linux/) voor Linux

### **Installatie MODAL app** 

* Ga naar de [releases pagina](https://github.com/AboutCodingBE/modal-docker-monorepo/releases) van MODAL  
* Klik op het bestand **archive-app-linux.zip** van de laatste release (bv. 0.0.19) en download het bestand  
* Ga naar het gedownloade bestand en extraheer (unzip) het. Je ziet een folder `archive-app-windows` met daarin de volgende bestanden:

        README-RELEASE.md  
        archive-agent.exe  
        config.json  
        diagnostic.ps1  
        docker-compose.prod.yml

### **Troubleshooting** {#troubleshooting-1}

Mogelijk verschijnt een foutmelding bij het opstarten van de app, bv.:  
```Failed to start services```

De MODAL applicatie werkt niet out of the box als Docker enkel beschikbaar is als root user. Het is ook beter om de app niet op te starten als root user.

Test dit door volgende commandos in te voeren in je Terminal:

```shell
docker ps # geeft mogelijk foutmeldingen
```

```shell
sudo docker ps # geeft een lijst met Docker images
```

Als dit het geval is, kan je dit oplossen door de gebruiker aan de Docker group toe te voegen:

```shell
sudo groupadd docker # controleer of de group al bestaat
```

```shell
sudo usermod -aG docker $USER # voeg de huidige gebruiker toe
```
