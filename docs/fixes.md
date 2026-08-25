## **Diagnostic**

Diagnostic.sh is een troubleshooting tool om te zien wat er draait en om alles netjes op te ruimen als de app vastloopt of niet goed start. Het biedt volgende functies:

1. Poorten controleren : voor elke poort toont het of deze vrij of in gebruik is en welk proces (naam \+ PID) de poort gebruikt.  
2. Docker status: controleert of Docker draait  
3. Container status: toont alle draaiende Docker Compose containers van de app

Na de diagnose krijg je een menu met de mogelijkheid om processen op alle app poorten en/of Docker te stoppen.

Je start de tool in een terminal:

```shell
./diagnostic.sh
```

## **Poort is al ingenomen**

Dit kan voorkomen als een van de onderdelen (bv. TIKA, Ollama) al werd geïnstalleerd. 
Het bestand docker-compose-prod.yml voorziet al in redirects naar andere poorten, maar je kan dit verder aanpassen:

1. Open het bestand docker-compose-prod.yml  
2. Zoek naar het fragment  
    `tika:`  
       `image: apache/tika:latest-full`  
       `ports:`  
         `- "7777:9998"`   
3. Pas het poortnummer aan  
    `tika:`  
       `image: apache/tika:latest-full`  
       `ports:`  
         `- "7778:9998"` 

## **Zenity is niet ondersteund of geïnstalleerd**

Sommige Linux-varianten ondersteunen de dialoog met het bestandsysteem niet via Zenity. Je kan dit testen met:

```shell
zenity --file-selection --directory --title="Test Dialog"
```

Als dit geen venster opent, kan je Zenity installeren met:

```shell
sudo apt update
sudo apt install zenity
```

## **Verbose optie**
Gebruik deze fix wanneer je de lees/schrijfacties naar de database live wil volgen.

1. Sluit de applicatie
2. Open het bestand 'docker-compose.prod.yml'
3. Pas het volgende stukje aan:

```shell
    db:
    image: postgres:16-alpine
    command: ["postgres", "-c", "log_statement=all"] # <-- VOEG DEZE LIJN TOE
    environment:
      - POSTGRES_USER=archiveuser
      - POSTGRES_PASSWORD=archivepass
      - POSTGRES_DB=modaldb
      ...
```

4. Start de applicatie weer op
5. Ga in jet terminal naar de folder met het bestand 'docker-compose.prod.yml'
6. Geef het volgende commando:

```shell
docker compose -f docker-compose.prod.yml logs -f db
```