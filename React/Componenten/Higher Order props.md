Bron: https://www.freecodecamp.org/news/higher-order-components-in-react/

Een **hogere orde component (HOC)** is een functie die een component als argument neemt en een nieuwe component retourneert die de oorspronkelijke component omhult. HOC’s zijn een krachtige functie van de React-bibliotheek die u in staat stellen om componentlogica opnieuw te gebruiken over meerdere componenten. HOC’s stellen u in staat om extra functionaliteit aan een component toe te voegen zonder de code van de component te wijzigen. U kunt bijvoorbeeld een HOC gebruiken om authenticatie- of routeringsmogelijkheden aan een component toe te voegen of om een specifieke stijl of gedrag toe te passen op meerdere componenten. HOC’s kunnen extra argumenten aannemen, waarmee u het gedrag van de HOC kunt aanpassen. Dit maakt ze een flexibele en herbruikbare manier om functionaliteit aan uw componenten toe te voegen.

Laten we een voorbeeld bekijken waarbij we een Higher Order Props-functie gebruiken om een `withColor` functie te maken die kleurprops toevoegt aan een component op basis van bepaalde voorwaarden.

Stel je voor dat we een `Button`-component hebben die we willen aanpassen met verschillende kleuren, afhankelijk van bepaalde omstandigheden.

```javascript
import React from 'react';

// Onze originele Button-component
function Button({ text }) {
  return <button>{text}</button>;
}

// Een voorbeeld van een Higher Order Props-functie
function withColor(WrappedComponent) {
  return function ColoredComponent(props) {
    const { condition, ...rest } = props;

    // Voeg een kleurprop toe op basis van een voorwaarde
    const colorProp = condition ? { color: 'green' } : { color: 'red' };

    // Voeg de aangepaste kleurprop toe aan de oorspronkelijke props
    const enhancedProps = {
      ...rest,
      ...colorProp,
    };

    return <WrappedComponent {...enhancedProps} />;
  };
}

// Verkrijg onze aangepaste Button-component met kleurprops
const ColoredButton = withColor(Button);

// Gebruik onze aangepaste Button-component
function App() {
  return (
    <div>
      <ColoredButton text="Regular Button" />
      <ColoredButton text="Conditional Green Button" condition={true} />
      <ColoredButton text="Conditional Red Button" condition={false} />
    </div>
  );
}

export default App;
```

In dit voorbeeld hebben we:

1. Een eenvoudige `Button`-component die een tekst weergeeft in een `<button>`-element.
2. De `withColor` functie, een Higher Order Props-functie, die kleurprops toevoegt aan een component op basis van een voorwaarde. Deze functie accepteert een WrappedComponent (hier: `Button`) en retourneert een nieuwe component (`ColoredComponent`) met aangepaste props.
3. We gebruiken `withColor` om een aangepaste `ColoredButton`-component te maken op basis van onze originele `Button`, die kleuren toevoegt aan de button op basis van de voorwaarden die we hebben doorgegeven.

De `ColoredButton` kan nu verschillende kleuren hebben op basis van de voorwaarden die zijn doorgegeven als props, wat mogelijk is gemaakt door de Higher Order Props-functie `withColor`. Dit is een eenvoudig voorbeeld om het concept van Higher Order Props te illustreren door props dynamisch aan te passen en toe te voegen aan een component.