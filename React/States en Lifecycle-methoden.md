Meer info: [[Props en state]]
### States

- **State in React** verwijst naar de gegevens die relevant zijn voor een component en kunnen veranderen tijdens de levensduur ervan.
- **Hoe wordt een state gedefinieerd?** In een React-component wordt de `useState` hook (of voor class-componenten, de `state`-eigenschap) gebruikt om een stukje gegevens binnen een component te houden dat kan veranderen.
- **Voorbeeld van het gebruik van useState:**
  ```javascript
  import React, { useState } from 'react';

  const Counter = () => {
    const [count, setCount] = useState(0); // 'count' is de state en 'setCount' is de functie om de state bij te werken

    const increment = () => {
      setCount(count + 1); // Verhoog de count met 1
    };

    return (
      <div>
        <p>{count}</p>
        <button onClick={increment}>Verhoog</button>
      </div>
    );
  };
  ```
- **Belangrijk om te weten:** Directe manipulatie van de state (bijv. `count++`) wordt afgeraden in React. Gebruik altijd de functie die wordt geleverd door `useState` om de state bij te werken (`setCount` in het bovenstaande voorbeeld), omdat dit React op de hoogte stelt van de verandering en een herrendering van de component veroorzaakt.

### Lifecycle-methoden
[[LevenCyclus]]
- **Lifecycle-methoden** zijn methoden die worden aangeroepen op verschillende punten in de levenscyclus van een component, bijvoorbeeld wanneer het wordt gemaakt, bijgewerkt of vernietigd.
- **Voorbeeld van lifecycle-methoden in een class-component:**
  ```javascript
  import React, { Component } from 'react';

  class LifecycleDemo extends Component {
    constructor(props) {
      super(props);
      console.log('Constructor is aangeroepen');
    }

    componentDidMount() {
      console.log('Component is gemonteerd');
    }

    componentDidUpdate(prevProps, prevState) {
      console.log('Component is bijgewerkt');
    }

    componentWillUnmount() {
      console.log('Component wordt verwijderd');
    }

    render() {
      return <div>Lifecycle-demo</div>;
    }
  }
  ```
- **Belangrijk om te weten:** In functionele componenten zijn lifecycle-methoden vervangen door hooks zoals `useEffect` die vergelijkbare functionaliteit bieden maar op een andere manier werken.

Lifecycle-methoden zijn handig om acties uit te voeren op specifieke momenten in het leven van een component, zoals het initiëren van gegevens, het uitvoeren van netwerkverzoeken, opschonen van resources, etc. Deze methoden maken het mogelijk om de logica van een component te controleren op specifieke tijdstippen tijdens de levenscyclus ervan.