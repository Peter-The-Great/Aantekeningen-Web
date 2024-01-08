The bind() is an inbuilt method in React that is used to pass the data as an argument to the function of a **class based component**.

**Syntax:**

```JS
this.function.bind(this,[arg1...]);
```

**Parameter:** It accepts two parameters, the first parameter is the _**this**_ keyword used for binding and the second parameter is the sequence of arguments that are passed as a parameter and are optional.

**Creating React Application:**

- **Step 1:** Create a React application using the following command:
```c
npx create-react-app foldername
```

- **Step 2:** After creating your project folder i.e. **foldername,** move to it using the following command:
```bash
cd foldername
```

**Example 1:**
```js
import React from 'react'; 
class App extends React.Component { 
// Initialising state 
state = { 
	name: 'GFG', 
}; 

handler = (name) => { 
	// Changing the state 
	this.setState({ name: name }); 
}; 

render() { 
	return ( 
	<div> 
		<h1>Name:{this.state.name}</h1> 
		<h1>Click here to change the name</h1> 

		{/* Passing the name as an argument 
		to the handler() function */} 

		<button onClick={this.handler.bind(this, 'GeeksForGeeks')}> 
		Click Here 
		</button> 
	</div> 
	); 
} 
} 

export default App;
```