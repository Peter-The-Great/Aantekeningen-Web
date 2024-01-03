React maakt gebruik van JSX, een syntactische uitbreiding van JavaScript waarmee je HTML-achtige code in je JavaScript kunt schrijven. Dit maakt het gemakkelijker om componenten te maken door HTML-achtige syntax te gebruiken binnen je JavaScript-code.

```js
import React from 'react';

// Een voorbeeld van JSX in een React-component
const Hello = () => {
  const name = 'Wereld';
//Dit gedeelte hier zorgt voor dat JSX Werkt.
  return (
    <div>
      <h1>Hallo, {name}!</h1>
      <p>Dit is een voorbeeld van JSX in React.</p>
    </div>
  );
};

export default Hello;
```

In dit voorbeeld zie je hoe JSX wordt gebruikt binnen de `Hello`-component:

- De code tussen de `return`-statements lijkt sterk op HTML, maar het is eigenlijk JSX.
- JSX kan JavaScript-expressies bevatten, zoals de variabele `{name}` die tussen de accolades wordt geplaatst. Dit wordt gebruikt om de variabele `name` binnen de JSX weer te geven.
- Het lijkt op HTML, maar het wordt uiteindelijk vertaald naar JavaScript door een proces genaamd "transpiling", waardoor browsers het kunnen begrijpen.