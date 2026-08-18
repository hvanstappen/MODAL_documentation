### **Installatie Docker Desktop**

Zie [https://docs.docker.com/desktop/setup/install/windows-install/](https://docs.docker.com/desktop/setup/install/windows-install/) voor meer details

* Download Docker Desktop Installer.exe via [deze link](https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe?utm_source=docker&utm_medium=webreferral&utm_campaign=docs-driven-download-win-amd64)  
* Dubbelklik op Docker Desktop Installer.exe om het installatieprogramma te starten.   
  Docker Desktop wordt standaard geïnstalleerd in C:\\Program Files\\Docker\\Docker.  
* Volg de instructies in de installatiewizard om het installatieprogramma te autoriseren en de installatie te starten.  
* Wanneer de installatie is voltooid, klik op 'Sluiten' om het installatieproces af te ronden.

### **Installatie MODAL app**

* Ga naar de [releases pagina](https://github.com/AboutCodingBE/modal-docker-monorepo/releases) van MODAL  
* Klik op het bestand **archive-app-windows.zip** van de laatste release (bv. 0.0.19) en download het bestand  
  * Ga naar het gedownloade bestand en pak het uit (unzip). Je ziet een folder `archive-app-windows` met daarin de volgende bestanden:

        README-RELEASE.md  
        archive-agent.exe  
        config.json  
        diagnostic.ps1  
        docker-compose.prod.yml

### **Troubleshooting** 

* Het is mogelijk dat je het Windows subsystem for Linux moet updaten of installeren. Voer daarvoor het volgende commando in je je Terminal:

```shell
wsl --update
```

	Meer informatie vind je op de [Docker installatie handleiding](https://docs.docker.com/desktop/setup/install/windows-install/#wsl-verification-and-setup)