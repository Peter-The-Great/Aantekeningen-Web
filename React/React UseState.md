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