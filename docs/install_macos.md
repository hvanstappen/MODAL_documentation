## **Installatie op MacOS**

Voor macOS zijn twee versies beschikbaar: macos-arm64 en macos-intel. Kies de juiste versie afhankelijk van je architectuur. Om te controleren of je Mac een Apple Silicon (voor arm64) of Intel-chip heeft, ga naar het Apple-menu, klik op "Over deze Mac" en bekijk de naam van de processor.

### **Installatie Docker Desktop**

Zie de [Docker-documentatie voor macOS](https://docs.docker.com/desktop/setup/install/mac-install/) voor meer details.

* Download Docker Desktop for Mac via de officiële Docker-website.  
* Open het gedownloade .dmg-bestand en sleep Docker.app naar de map Programma's (Applications)  
* Open vervolgens Docker vanuit de map Programma's. Mogelijk wordt gevraagd de toepassing te bevestigen of beheerdersrechten te verlenen om de installatie af te ronden.  
* Volg de instructies op het scherm om Docker Desktop te configureren. Mogelijk wordt gevraagd je aan te melden met een Docker-account of de benodigde systeemcomponenten te installeren.

### **Installatie MODAL app**

* Ga naar de [releases pagina](https://github.com/AboutCodingBE/modal-docker-monorepo/releases) van MODAL  
* Klik op het bestand **archive-app-macos-arm64.zip** van de laatste release (bv. 0.0.19) en download het bestand.  
* Ga naar het gedownloade bestand en extraheer (unzip) het. Je ziet een folder `archive-app-macos-arm64` met daarin de volgende bestanden:

        README-RELEASE.md  
        archive-agent.exe  
        config.json  
        diagnostic.ps1  
        docker-compose.prod.yml
