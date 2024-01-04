De **render-prop pattern** is een ontwerppatroon in React dat wordt gebruikt om code te delen tussen componenten. Het patroon houdt in dat een component een **prop** accepteert die een functie is die een React-element retourneert. De component roept vervolgens deze functie aan in plaats van zijn eigen render-logica te implementeren. Dit stelt de component in staat om inhoud te renderen en tegelijkertijd gegevens of gedrag van de oudercomponent bloot te stellen.

De **render-prop pattern** is nuttig voor het delen van code tussen componenten die vergelijkbare functionaliteit hebben, maar verschillende weergaven. Het patroon kan ook worden gebruikt om cross-cutting concerns te implementeren, zoals authenticatie of routering.

Hier is een voorbeeld van hoe u de **render-prop pattern** kunt gebruiken in React:

JavaScript

```javascript
import React from 'react';

class Mouse extends React.Component {
  constructor(props) {
    super(props);

    this.handleMouseMove = this.handleMouseMove.bind(this);

    this.state = { x: 0, y: 0 };
  }

  handleMouseMove(event) {
    this.setState({
      x: event.clientX,
      y: event.clientY
    });
  }

  render() {
    return (
      <div style={{ height: '100%' }} onMouseMove={this.handleMouseMove}>
        {this.props.render(this.state)}
      </div>
    );
  }
}

class App extends React.Component {
  render() {
    return (
      <div style={{ height: '100%' }}>
        <Mouse render={mouse => (
          <h1>The mouse position is ({mouse.x}, {mouse.y})</h1>
        )} />
      </div>
    );
  }
}
```

In dit voorbeeld wordt de **Mouse**-component gedefinieerd met een **render**-prop die een functie verwacht als argument. De functie wordt gebruikt om de positie van de muis weer te geven in de weergave van de component.

De **App**-component wordt vervolgens gebruikt om de **Mouse**-component te renderen en de **render**-prop te gebruiken om de positie van de muis weer te geven.