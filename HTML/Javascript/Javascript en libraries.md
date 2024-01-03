Bronnen:
https://www.w3schools.com/js/default.asp
https://javascript.info/

JavaScript is een **scripting- of programmeertaal** die wordt gebruikt om complexe functies op webpagina’s te implementeren. Het is de derde laag van de standaard webtechnologieën, waarvan twee (HTML en CSS) in andere delen van het leerprogramma worden behandeld. HTML is de opmaaktaal die we gebruiken om onze webinhoud te structureren en betekenis te geven, bijvoorbeeld het definiëren van alinea’s, koppen en gegevenstabellen, of het insluiten van afbeeldingen en video’s op de pagina. CSS is een taal van stijlregels die we gebruiken om stijl toe te passen op onze HTML-inhoud, bijvoorbeeld het instellen van achtergrondkleuren en lettertypen, en het rangschikken van onze inhoud in meerdere kolommen. JavaScript is een scripttaal waarmee u dynamisch bijgewerkte inhoud kunt maken, multimedia kunt bedienen, afbeeldingen kunt animeren en nog veel meer. [Het is verbazingwekkend wat je met een paar regels JavaScript-code kunt bereiken!](https://bing.com/search?q=Wat+is+JavaScript%3f)

Het is eigenlijk ook een alles taal aangezien je niet het alleen voor front-end, maar ook voor back-end kan gebruiken. Je kan een hele applicatie maken met JavaScript.

Hieronder zijn nog wat onderdelen die voorkwamen in de proeftoets en ik zal bepaalde antwoorden over JavaScript uitleggen.
## Babel.js en Pollyfill.js
Babel en een polyfill zijn beide tools die helpen bij het ondersteunen van moderne JavaScript-code in oudere browsers, maar ze werken op verschillende manieren:

- **Babel** is een JavaScript-compiler die moderne JavaScript-code (geschreven in de nieuwste standaard, zoals ES6+) omzet in oudere versies die compatibel zijn met oudere browsers die mogelijk die nieuwe functies niet ondersteunen. Het vertaalt bijvoorbeeld ES6+-code naar ES5-code, wat breder wordt ondersteund door oudere browsers.
    
- Een **polyfill** is een stuk code (meestal in de vorm van een JavaScript-bibliotheek) dat ontbrekende functionaliteit in oudere browsers nabootst of aanvult. Als een browser een bepaalde JavaScript-functie niet ondersteunt, kan een polyfill die functionaliteit toevoegen door de ontbrekende methoden of functies na te bootsen, zodat de code werkt in die browser.
    

**Kort gezegd:** Beter gezegd babel is een compiler voor javascript en polyfill is een stuk runtime code die nieuwe JavaScript functies in oude browsers doet.
