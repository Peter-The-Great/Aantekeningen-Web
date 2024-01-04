**Clean Architecture** is een softwareontwerppatroon dat is voorgesteld door Robert C. [Martin (Uncle Bob) om schaalbare, testbare en onderhoudbare software te bouwen](https://betterprogramming.pub/the-clean-architecture-beginners-guide-e4b7058c1165)[1](https://betterprogramming.pub/the-clean-architecture-beginners-guide-e4b7058c1165). Het is een bundel van organisatieprincipes voor webontwikkelingsprojecten die de kernmodel, use cases, interfaces en externe interfaces in lagen scheidt en ze van elkaar isoleert. [Het helpt bij het testen, implementeren en onderhouden van software](https://www.freecodecamp.org/news/a-quick-introduction-to-clean-architecture-990c014448d2/)[2](https://www.freecodecamp.org/news/a-quick-introduction-to-clean-architecture-990c014448d2/).

De architectuur bestaat uit vier lagen: **Interface Adapters**, **Application Business Rules**, **Enterprise Business Rules** en **Frameworks and Drivers**. De Dependency Rule stelt dat de broncode-afhankelijkheden alleen naar binnen kunnen wijzen. Dit betekent dat niets in een binnenste cirkel iets kan weten over iets in een buitenste cirkel. [De Dependency Rule is de belangrijkste regel die deze architectuur doet werken](https://betterprogramming.pub/the-clean-architecture-beginners-guide-e4b7058c1165)[1](https://betterprogramming.pub/the-clean-architecture-beginners-guide-e4b7058c1165).


Hier is een voorbeeld van hoe het **Model-View-Controller (MVC)** patroon kan worden geïmplementeerd in een React-applicatie. Dit voorbeeld is afkomstig van Test Double en illustreert hoe het MVC-patroon kan worden gebruikt om de presentatielaag van een React-applicatie te scheiden van de domeinlaag.

In dit voorbeeld is de `Model` component verantwoordelijk voor het beheren van de taken. Het zou bijvoorbeeld een lijst van taken bijhouden en methoden bieden om taken toe te voegen of te verwijderen. De `View` component zou verantwoordelijk zijn voor het weergeven van de taken aan de gebruiker. Het zou bijvoorbeeld een lijst van taken weergeven en knoppen bieden om taken toe te voegen of te verwijderen. De `Controller` component zou fungeren als een tussenpersoon tussen het `Model` en de `View`. Het zou bijvoorbeeld de invoer van de gebruiker ontvangen en vervolgens de juiste methode van het `Model` aanroepen om de taken toe te voegen of te verwijderen. Vervolgens zou het de `View` bijwerken om de wijzigingen weer te geven.

Hier is een voorbeeld van hoe de code voor onze applicatie eruit zou kunnen zien in React:

JavaScript

```javascript
import React, { Component } from 'react';

class Task extends Component {
  render() {
    return (
      <li>{this.props.description}</li>
    );
  }
}

class TaskList extends Component {
  constructor(props) {
    super(props);
    this.state = {
      tasks: []
    };
  }

  addTask(task) {
    this.setState({
      tasks: [...this.state.tasks, task]
    });
  }

  removeTask(task) {
    this.setState({
      tasks: this.state.tasks.filter(t => t !== task)
    });
  }

  render() {
    return (
      <div>
        <ul>
          {this.state.tasks.map(task => (
            <Task key={task} description={task} />
          ))}
        </ul>
        <button onClick={() => this.addTask('New Task')}>Add Task</button>
        <button onClick={() => this.removeTask('New Task')}>Remove Task</button>
      </div>
    );
  }
}

class TaskListController extends Component {
  render() {
    return (
      <TaskList />
    );
  }
}

export default TaskListController;
```

In dit voorbeeld is de `TaskList` component het `Model`, de `Task` component is de `View` en de `TaskListController` component is de `Controller`. De `TaskList` component houdt een lijst van taken bij en biedt methoden om taken toe te voegen of te verwijderen. De `Task` component is verantwoordelijk voor het weergeven van de taken aan de gebruiker. De `TaskListController` component fungeert als een tussenpersoon tussen het `Model` en de `View`. Het rendert de `TaskList` component en geeft deze door aan de `View`.