`useReducer` is a **React Hook** that allows you to manage state and state transitions within your components. [It is an alternative to the `useState` hook and provides a way to handle more complex state logic with ease](https://react.dev/reference/react/useReducer) [1](https://react.dev/reference/react/useReducer)[2](https://www.bugpilot.io/guides/en/a-guide-to-the-react-usereducer-hook-f8fb)[3](https://blog.logrocket.com/react-usereducer-hook-ultimate-guide/).

The `useReducer` hook takes three arguments: a `reducer` function, an `initialArg` value, and an optional `init` function. The `reducer` function specifies how the state gets updated based on the action type. [The `initialArg` value is used to calculate the initial state, and the `init` function can be used to further customize the initial state](https://react.dev/reference/react/useReducer) [1](https://react.dev/reference/react/useReducer).

The `useReducer` hook returns an array with two values: the current state and a `dispatch` function. The `dispatch` function is used to update the state by passing an action object to it. When the `dispatch` function is called, the `reducer` function is executed with the current state and the action object as arguments. [The `reducer` function then returns the new state based on the action type](https://react.dev/reference/react/useReducer) [1](https://react.dev/reference/react/useReducer)[3](https://blog.logrocket.com/react-usereducer-hook-ultimate-guide/).

Here is an example of how to use the `useReducer` hook:

JavaScriptAI-generated code. Review and use carefully. .

```javascript
const reducer = (state, action) => {
  switch (action.type) {
    case "INCREMENT":
      return { count: state.count + 1 };
    case "DECREMENT":
      return { count: state.count - 1 };
    default:
      return state;
  }
};

function Counter() {
  const [state, dispatch] = useReducer(reducer, { count: 0 });

  const handleIncrement = () => {
    dispatch({ type: "INCREMENT" });
  };

  const handleDecrement = () => {
    dispatch({ type: "DECREMENT" });
  };

  return (
    <div>
      <h1>Count: {state.count}</h1>
      <button onClick={handleIncrement}>Increment</button>
      <button onClick={handleDecrement}>Decrement</button>
    </div>
  );
}
```

In this example, the `reducer` function takes two arguments: `state` and `action`. If the action type is `"INCREMENT"`, the function returns a new state object with the `count` property incremented by 1. If the action type is `"DECREMENT"`, the function returns a new state object with the `count` property decremented by 1. If the action type is not recognized, the function returns the original state object. The `Counter` component uses the `useReducer` hook to manage the state of the `count` property. It also defines two functions, `handleIncrement` and `handleDecrement`, that dispatch actions to the reducer when called. The `handleIncrement` function dispatches an action object with a type of `"INCREMENT"`, and the `handleDecrement` function dispatches an action object with a type of `"DECREMENT"`. [The component renders the current count value and two buttons that call the `handleIncrement` and `handleDecrement` functions when clicked](https://react.dev/reference/react/useReducer) [1](https://react.dev/reference/react/useReducer)[3](https://blog.logrocket.com/react-usereducer-hook-ultimate-guide/).