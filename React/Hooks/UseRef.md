Bron: https://www.w3schools.com/react/react_useref.asp
`useRef` is een hook in React die wordt gebruikt om referenties naar DOM-elementen of andere waarden te maken en bij te houden in functionele componenten.

### Wat doet `useRef`?

1. **DOM-elementen:** Met `useRef` kun je referenties maken naar DOM-elementen die worden gemaakt in je componenten. Dit geeft je de mogelijkheid om directe manipulaties of interacties met die DOM-elementen uit te voeren.

2. **Bijhouden van waarden:** Naast DOM-elementen kan `useRef` ook gebruikt worden om andere waarden bij te houden. Het houdt een 'mutable' object bij dat persistent blijft tussen re-renderingen van de component.

### Hoe gebruik je `useRef`?

1. **Creatie van een ref:** Je maakt een ref aan met `useRef` en initialiseert deze met een initiële waarde (optioneel):
   ```javascript
   import React, { useRef } from 'react';

   const myRef = useRef(initialValue);
   ```

2. **Toewijzing aan een DOM-element:** Je wijst de `ref` toe aan een HTML-element in je JSX:
   ```javascript
   <div ref={myRef}>...</div>
   ```

3. **Toegang tot het DOM-element:** Je kunt het DOM-element benaderen via `myRef.current`:
   ```javascript
   myRef.current.style.color = 'red'; // Bijvoorbeeld om de tekstkleur te veranderen
   ```

### Belangrijke punten:

- `useRef` kan worden gebruikt om referenties naar DOM-elementen te maken om directe manipulatie mogelijk te maken zonder dat het React-rendersysteem betrokken hoeft te zijn.
- Het is handig voor het bijhouden van gegevens die niet de oorzaak zijn van een re-rendering, zoals het bijhouden van een laatste waarde tussen renders door.
- Het aanpassen van `ref.current` zal geen re-rendering van de component triggeren, in tegenstelling tot het bijwerken van een state met `useState`.

Het is belangrijk om te onthouden dat hoewel `useRef` lijkt op een state, de updates van `ref.current` geen her-rendering van de component veroorzaken, waardoor het ideaal is voor het bijhouden van dingen die niet het uiterlijk van de component veranderen.