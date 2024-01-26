Om de temperatuur van het weer asynchroon weer te geven zodra een gebruiker op een knop drukt in React en het in een `useEffect`-hook te zetten, kun je de Fetch API gebruiken om gegevens op te halen van een weer-API. Vervolgens kun je de opgehaalde gegevens weergeven zodra de gebruiker op de knop drukt. Hier is een voorbeeld van hoe je dit kunt doen:

```javascript
import React, { useState, useEffect } from 'react';

const WeatherComponent = () => {
  const [temperature, setTemperature] = useState(null);

  useEffect(() => {
    // Functie om gegevens op te halen van de weer-API
    const fetchWeatherData = async () => {
      try {
        const response = await fetch('WEER_API_URL');
        const data = await response.json();
        setTemperature(data.main.temp); // Stel de temperatuur in van de opgehaalde gegevens
      } catch (error) {
        console.error('Fout bij het ophalen van weer gegevens', error);
      }
    };

    // Roep de fetch-functie aan zodra de component is gemonteerd
    fetchWeatherData();
  }, []); // Lege array zorgt ervoor dat dit effect slechts eenmaal wordt uitgevoerd

  return (
    <div>
      <button>Krijg temperatuur</button>
      {temperature && <p>De temperatuur is: {temperature} °C</p>}
    </div>
  );
};

export default WeatherComponent;
```

In dit voorbeeld wordt de `fetchWeatherData`-functie aangeroepen zodra de component is gemonteerd met behulp van de `useEffect`-hook. Vervolgens wordt de opgehaalde temperatuur weergegeven zodra deze beschikbaar is, nadat de gebruiker op de knop heeft gedrukt.

Dit voorbeeld maakt gebruik van de `useState`- en `useEffect`-hooks van React om de weer-API-gegevens asynchroon op te halen en weer te geven zodra de component is gemonteerd.

Citations:
[1](https://stackoverflow.com/questions/71303917/parsing-json-values-in-react-js-and-mapping-to-component)
[2](https://thenewstack.io/why-http-caching-matters-for-apis/)
[3](https://thenewstack.io/strategies-to-build-react-apps-in-a-client-side-architecture/)
[4](https://www.reddit.com/r/learnjavascript/comments/15jktbm/what_is_an_api_in_reality/)
[5](https://james-priest.github.io/udacity-nanodegree-react/course-notes/react-fundamentals.html)