`useState` is een **React Hook** die het mogelijk maakt om een **state variabele** toe te voegen aan een component. Het is een van de meest gebruikte hooks in React.

De `useState`-hook heeft twee waarden: de huidige waarde van de state en een functie om de waarde van de state te wijzigen. De eerste waarde is de huidige waarde van de state, en de tweede waarde is een functie die de waarde van de state kan wijzigen.

Hier is een voorbeeld van het gebruik van `useState` om een ​​getal bij te houden:

```javascript
import { useState } from 'react';

function MyComponent() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count++)}>Click me</button>
    </div>
  );
}
```

In dit voorbeeld wordt de `count`-state bijgehouden met behulp van `useState`. De `setCount`-functie wordt gebruikt om de waarde van de state te wijzigen wanneer de knop wordt ingedrukt.

Voorbeeld van Pascal:
![[61F41780-6731-4D84-8F97-601529611AA5.jpeg]]

## Opletten:

Bron:
https://react.dev/reference/react/useState#im-getting-an-error-too-many-re-renders

Je kan mogelijk de too many errors krijgen als je dit hebt:
```js
export function App(props) {
const [bericht, setBericht] = useState("Hallo"); 
setBericht("Dag");
return ( <div className='App'> <h1>{bericht} React.</h1> </div> ); }
```

Want bij elke setState (of te wel setBericht) moet react de hele component opnieuw renderen en als je steeds maar erbij zet dat je een state altijd veranderd dan gaat die in een eindeloze loop. Om dit te fixen gebruik je [[UseEffect]], want daarmee geef je aan dat als de state veranderd dat dan ook werkelijk pas het moet gaan veranderen.

#### Fix:
```js
import React, { useState, useEffect } from 'react';

export function App(props) {
  const [bericht, setBericht] = useState("Hallo");

  useEffect(() => {
    setBericht("Dag"); // Dit wordt één keer aangeroepen na de eerste render
  }, []); // lege array als afhankelijkheid betekent dat dit effect alleen bij de eerste render wordt uitgevoerd
  return (
    <div className='App'>
      <h1>{bericht} React.</h1>
    </div>
  );
}
```