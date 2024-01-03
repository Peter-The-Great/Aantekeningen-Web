Bron: https://www.w3schools.com/react/react_useeffect.asp
`useEffect` is een **React Hook** die het mogelijk maakt om een component te synchroniseren met een externe systeem. Het wordt gebruikt om de **side effects** van een component te beheren, zoals het ophalen van data van een API, het bijwerken van de DOM, enzovoort.

Het heeft twee parameters: `setup` en `dependencies`. `setup` is de functie die de logica van de effect bevat. `dependencies` is een optionele array van waarden waarvan de effect afhankelijk is. Als een van de waarden in de array verandert, wordt de effect opnieuw uitgevoerd. Als `dependencies` leeg is, wordt de effect alleen uitgevoerd bij het monteren van de component.

Hier is een voorbeeld van het gebruik van `useEffect` om een ​​API op te roepen:

```javascript
import { useState, useEffect } from 'react';

function MyComponent() {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => setData(data));
  }, []);

  if (!data) {
    return <div>Loading...</div>;
  }

  return <div>{data}</div>;
}
```

In dit voorbeeld wordt de `fetch`-functie aangeroepen wanneer de component wordt gemonteerd, en wordt de geretourneerde data opgeslagen in de `data`-state. De `if`-statement zorgt ervoor dat er “Loading…” wordt weergegeven totdat de data is opgehaald.