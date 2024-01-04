Bron: https://www.freecodecamp.org/news/higher-order-components-in-react/

Een **hogere orde component (HOC)** is een functie die een component als argument neemt en een nieuwe component retourneert die de oorspronkelijke component omhult. HOC’s zijn een krachtige functie van de React-bibliotheek die u in staat stellen om componentlogica opnieuw te gebruiken over meerdere componenten. HOC’s stellen u in staat om extra functionaliteit aan een component toe te voegen zonder de code van de component te wijzigen. U kunt bijvoorbeeld een HOC gebruiken om authenticatie- of routeringsmogelijkheden aan een component toe te voegen of om een specifieke stijl of gedrag toe te passen op meerdere componenten. HOC’s kunnen extra argumenten aannemen, waarmee u het gedrag van de HOC kunt aanpassen. Dit maakt ze een flexibele en herbruikbare manier om functionaliteit aan uw componenten toe te voegen.

Hier is een voorbeeld van hoe u een HOC kunt definiëren in React:

```javascript
import React from 'react';

function withData(WrappedComponent) {
  return class extends React.Component {
    constructor(props) {
      super(props);

      this.state = {
        data: [],
      };
    }

    componentDidMount() {
      fetch(this.props.url)
        .then(response => response.json())
        .then(data => this.setState({ data }));
    }

    render() {
      return <WrappedComponent data={this.state.data} {...this.props} />;
    }
  };
}
```

In dit voorbeeld wordt de **withData**-functie gedefinieerd als een HOC die een component als argument neemt en een nieuwe component retourneert die de oorspronkelijke component omhult. De HOC haalt gegevens op van een API en geeft deze door aan de oorspronkelijke component als een **prop**.

De HOC wordt gebruikt om de **WrappedComponent** te omhullen en de gegevens van de API op te halen. De gegevens worden vervolgens doorgegeven aan de oorspronkelijke component als een **prop**. De oorspronkelijke component kan de gegevens vervolgens gebruiken om de weergave te renderen.