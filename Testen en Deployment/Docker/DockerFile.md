Bronnen:
https://docs.docker.com/engine/reference/builder/
https://docs.docker.com/develop/develop-images/dockerfile_best-practices/
https://learn.microsoft.com/nl-nl/training/modules/intro-to-containers/

Een Dockerfile is een tekstbestand dat alle opdrachten bevat die nodig zijn om een Docker-image te bouwen . Het bevat een reeks instructies die Docker vertellen hoe het een image moet bouwen . Hieronder staan enkele belangrijke opdrachten die je kunt gebruiken in een Dockerfile:
- **FROM**: Hiermee geef je de basisimage op waarop je de nieuwe image wilt bouwen .
- **RUN**: Hiermee voer je opdrachten uit in de image tijdens het bouwproces .
- **COPY**: Hiermee kopieer je bestanden van de host naar de image .
- **ADD**: Hiermee kopieer je bestanden van de host naar de image, maar het ondersteunt ook het downloaden van bestanden vanaf een URL en het uitpakken van tar-archieven .
- **CMD**: Hiermee geef je de standaardopdracht op die moet worden uitgevoerd wanneer een container wordt gestart .
- **ENTRYPOINT**: Hiermee geef je de standaarduitvoerbare opdracht op die moet worden uitgevoerd wanneer een container wordt gestart .
- **EXPOSE**: Hiermee geef je aan welke poorten de container moet openen wanneer deze wordt uitgevoerd .
- **ENV**: Hiermee stel je omgevingsvariabelen in die beschikbaar zijn in de container .
- **WORKDIR**: Hiermee stel je de werkmap in waarin de opdrachten worden uitgevoerd .
Hier is een voorbeeld van een eenvoudige Dockerfile die een Python-applicatie bouwt:

Hier is een voorbeeld van een eenvoudige Dockerfile die een Python-applicatie bouwt:

```dockerfile
# Gebruik de officiële Python-beeld als basis
FROM python:3.7-slim-buster

# Stel de werkmap in op /app
WORKDIR /app

# Kopieer de huidige directoryinhoud naar /app
COPY . /app

# Installeer de vereiste pakketten
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Definieer de standaardopdracht die moet worden uitgevoerd wanneer een container wordt gestart
CMD ["python", "app.py"]
```

In dit voorbeeld wordt een Docker-image gebouwd op basis van de officiële Python 3.7-beeld . Vervolgens wordt de werkmap ingesteld op /app en wordt de inhoud van de huidige directory gekopieerd naar /app . De vereiste pakketten worden geïnstalleerd en de standaardopdracht die moet worden uitgevoerd wanneer een container wordt gestart, wordt gedefinieerd.
