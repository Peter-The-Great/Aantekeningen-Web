Callback-props zijn een essentieel concept in React, waarbij functies worden doorgegeven aan componenten als props om interactie tussen ouder- en kindcomponenten mogelijk te maken.

### Callback-props in React:

1. **Doel:** Het doorgeven van een functie (callback) als prop van een oudercomponent naar een kindcomponent, zodat het kindcomponent deze functie kan aanroepen om bepaalde acties uit te voeren in de oudercomponent.

2. **Waarom gebruiken we ze?** Hiermee kan een kindcomponent communiceren met zijn oudercomponent zonder dat de oudercomponent rechtstreeks de interne staat van het kind hoeft te kennen. Het biedt een manier om gebeurtenissen of acties in een kindcomponent door te geven aan de oudercomponent.

3. **Hoe werkt het?**
   - Een functie wordt gedefinieerd in de oudercomponent.
   - Deze functie wordt doorgegeven aan de kindcomponent als een prop.
   - Het kindcomponent kan de ontvangen functie aanroepen wanneer een bepaalde gebeurtenis plaatsvindt, bijvoorbeeld een klik of een verandering.

4. **Voorbeeld:**
   ```javascript
   // Oudercomponent
   const ParentComponent = () => {
     const handleCallback = (data) => {
       console.log("Callback-functie is aangeroepen met data:", data);
     };

     return <ChildComponent callbackFunction={handleCallback} />;
   };

   // Kindcomponent
   const ChildComponent = ({ callbackFunction }) => {
     const handleClick = () => {
       // Wanneer een bepaalde gebeurtenis plaatsvindt, roepen we de ontvangen functie aan
       callbackFunction("Hallo vanuit het kindcomponent!");
     };

     return (
       <button onClick={handleClick}>
         Klik hier
       </button>
     );
   };
   ```

5. **Belangrijk:** Door het gebruik van callback-props kunnen componenten in React op een georganiseerde manier communiceren zonder directe afhankelijkheden te hebben tussen de ouder- en kindcomponenten, waardoor de code beter onderhoudbaar en herbruikbaar wordt.

Dit patroon van het doorgeven van functies als props tussen componenten in React is een krachtig middel voor het beheren van interacties en het onderhouden van een scheiding van verantwoordelijkheden tussen componenten.