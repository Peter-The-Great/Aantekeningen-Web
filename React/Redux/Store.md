Om de waarde van een **store** te wijzigen in **ReactJS**, moet je een **action** dispatchen. [Een action is een object dat een type en optionele gegevens bevat die de state van de store wijzigen](https://redux.js.org/api/store/) [1](https://redux.js.org/api/store/).

Hier is een voorbeeld van hoe je een action kunt dispatchen om de waarde van een store te wijzigen:

```javascript
import { createStore } from 'redux';

const initialState = {
  count: 0
};

function reducer(state = initialState, action) {
  switch (action.type) {
    case 'INCREMENT':
      return { count: state.count + 1 };
    case 'DECREMENT':
      return { count: state.count - 1 };
    default:
      return state;
  }
}

const store = createStore(reducer);

store.dispatch({ type: 'INCREMENT' });
```

In dit voorbeeld wordt een action gedefinieerd met het type `'INCREMENT'`. De action wordt vervolgens gedispatched naar de store met behulp van de `dispatch()`-methode. [De reducer wordt aangeroepen met de huidige state en de action en retourneert een nieuwe state die wordt opgeslagen in de store](https://redux.js.org/api/store/) [1](https://redux.js.org/api/store/).

[Als je meer wilt weten over het wijzigen van de waarde van een store in ReactJS, dan raad ik je aan om de volgende links te bekijken](https://redux.js.org/api/store/) [1](https://redux.js.org/api/store/)[2](https://stackoverflow.com/questions/54814129/how-to-edit-local-storage-values-react)[3](https://bobbyhadz.com/blog/react-get-textarea-value). Ze bevatten meer informatie over Redux en hoe je het kunt gebruiken in ReactJS.