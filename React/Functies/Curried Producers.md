Bronnen:
https://immerjs.github.io/immer/curried-produce/
https://blog.logrocket.com/immutability-in-react-with-immer/

In React, **curried producers** are a way to simplify the creation of immutable data structures in **useReducer** with the help of the **Immer** library. A **producer** is a function that takes a **draft** object and returns a new **draft** object with the desired changes. A **curried producer** is a function that returns another function that takes a **draft** object and returns a new **draft** object with the desired changes. This allows you to create a function that can be reused with different **draft** objects.

Here is an example of how you can use a **curried producer** in **useReducer** with **Immer**:

```javascript
import React, { useReducer } from 'react';
import produce from 'immer';

function reducer(state, action) {
  switch (action.type) {
    case 'update-email':
      return produce(state, draft => {
        draft.users[action.payload.userID].email = action.payload.email;
      });
    default:
      return state;
  }
}

function App() {
  const initialState = {
    users: [
      { id: 1, name: 'Alice', email: 'alice@example.com' },
      { id: 2, name: 'Bob', email: 'bob@example.com' },
    ],
  };

  const [state, dispatch] = useReducer(reducer, initialState);

  return (
    <div>
      <h1>Users</h1>
      <ul>
        {state.users.map(user => (
          <li key={user.id}>
            {user.name} ({user.email})
          </li>
        ))}
      </ul>
      <button
        onClick={() =>
          dispatch({
            type: 'update-email',
            payload: { userID: 1, email: 'new-email@example.com' },
          })
        }
      >
        Update Email
      </button>
    </div>
  );
}
```

In this example, the **reducer** function uses a **curried producer** to update the email of a user in the **users** array. The **produce** function takes a function that accepts a **draft** object and returns a new **draft** object with the desired changes. The **curried producer** is used to create a function that can be reused with different **draft** objects.