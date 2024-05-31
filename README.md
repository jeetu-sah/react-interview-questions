# React JS Interview Questions.
In this repository, I have listed some Interview Questions. <br />
1. [What is React JS?](#what-is-react-js) <br /> 
2. [What is the feature of React JS?](#what-is-the-feature-of-react-js)  <br />
3. [What are the differences between functional and class components?](#what-are-the-differences-between-functional-and-class-components)  <br />
4. [What is React Router?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
5. [What is the virtual DOM? How does react use the virtual DOM to render the UI?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
6. [Explain Types of Hooks in React.](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
7. [What is useState() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
8. [What is useEffect() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
9. [What is useContext() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
10. [What is useReducer() in React?.](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
11. [What is useMemo() in React?](#what-is-usememo-in-react)  <br />
12. [What is useCallback() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
13. [What is useImperativeHandle() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
14. [What is useDebugValue() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
15. [What is useRef() in React?.](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
16. [What is useLayoutEffect() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
17. [What is JSX? (JAVASCRIPT XML) in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
18. [Explain Strict Mode in React? (JAVASCRIPT XML) in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
19. [How to prevent re-renders in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
20. [What is the use of React.PureComponent in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
21. [What are Higher Order Components in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
22. [What are keys in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
23. [What is the lazyloading in React?](#what-is-the-lazyloading-in-react)  <br />
24. [What are the differences between controlled and uncontrolled components in React?](#what-are-the-differences-between-controlled-and-uncontrolled-components-in-react)  <br />
25. [What are props in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
26. [What is prop drilling in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
27. [Name a few techniques to optimize React app performance.](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
28. [How to pass data between react components?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
29. [What are the lifecycle methods of React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
30. [Can React Hook replace Redux?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
31. [Explain conditional rendering in React.](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
32. [How to pass data between sibling components using React router?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
33. [What are Custom Hooks in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
34. [Why do React Hooks make use of refs?](https://en.wikipedia.org/wiki/Object-relational_mapping)
35. [How to implement User Authentication in React?](#how-to-implement-user-authentication-in-react)
36. [Explain Action’s in Redux.](#explain-actions-in-redux)




### What is React JS?
React is a free and open-source front-end JavaScript library for building user interfaces based on components. It is maintained by Meta and a community of individual developers and companies. React can be used to develop single-page, mobile, or server-rendered applications with frameworks like Next.js.

### What is the feature of React JS?
JSX(JavaScript Syntax Extension): <br />
Virtual DOM: <br />
One-way Data Binding: <br />
Performance: <br />
Extension: <br />
Conditional Statements: <br />
Components: <br />
Simplicity: <br />


### What are the differences between functional and class components?
A functional component is just a plain javascript function that returns JSX (javascript XML). <br />
A class component is a javascript class that extends React.



### What is useMemo() in React?
The useMemo Hook only runs when one of its dependencies updates. useMemo is a valuable tool in the React framework, designed to optimize performance by memoizing expensive computations. The React useMemo Hook returns a memoized value.
Memoization is caching a value so that it does not need to be recalculated. <br />
It recalculated the value only when one of its dependencies changed. It is useful to avoid expensive calculations on every render when the returned value is not going to change.

##### Example: <br />
 ```javascript
//App.js
import React, { useState, useMemo } from 'react';
const WithMemo = () => {
	const [count, setCount] = useState(0);
	const [renderCount, setRenderCount] = useState(0);
	const computeExpensiveValue = (num) => {
		console.log("Computing...");
		let result = 0;
		for (let i = 0; i < 1000000000; i++) {
			result += num;
		}
		return result;
	};

	// Using useMemo to memoize the result based on count
	const result = useMemo(() => computeExpensiveValue(count), [count]);

	return (
		<div>
			<h2>With Memo Example</h2>
			<p>Count: {count}</p>
			<p>Result: {result}</p>
			<p>Render Count: {renderCount}</p>
			<button onClick={() => setCount(count + 1)}>Increment Count</button>
			<button onClick={() => setRenderCount(renderCount + 1)}>
				Increment Render Count
			</button>
		</div>
	);
};
export default WithMemo;
```


### What is the lazyloading in React?
Lazy loading is one of the most common design patterns used in web and mobile development. In simple terms, lazy loading is a design pattern. It allows you to load parts of your application on-demand to reduce the initial load time. 
For example, you can initially load the components and modules related to user login and registration. Then, you can load the rest of the components based on user navigation.

#####    Advantages of Lazy Loading.
1. Reduces initial loading time by reducing the bundle size.
2. Reduces browser workload
3. Improves application performance in low bandwidth situations.
4. Improves user experience at initial loading.
5. Optimizes resource usage.

#####   Disadvantages of Lazy Loading.
1. Not suitable for small-scale applications.
2. Placeholders can slow down quick scrolling.
3. Requires additional communication with the server to fetch resources.
4. Can affect SEO and ranking.
   
 ```javascript
// Without React.lazy()
import AboutComponent from './AboutComponent ';

// With React.lazy()
const AboutComponent = React.lazy(() => import('./AboutComponent '));

const HomeComponent = () => (
    <div><AboutComponent /></div>
)

```

### How to implement User Authentication in React?
User authentication is the process of securing user information through the use of some parameters like username, password, and more.
This helps the user to access his perks and features on a particular website. <br />
We will be using React JS, a Javascript frontend library, and Auth0, a framework that will help us in making our authentication user-friendly as well as secure.
   
 ```javascript
//install the authO-react js

npm install @auth0/auth0-react bootstrap

//Create the following files and add codes in these files.
//index.js
 
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';
import { Auth0Provider } from '@auth0/auth0-react';
 
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
    <Auth0Provider
        domain='dev-mf6lqfng.us.auth0.com'
        clientId='5c1HQIOd6HlVEi2CLLfTPO7HCImJ9qZr'
        redirectUri={window.location.origin}>
        <App />
    </Auth0Provider>
);

```

### Explain Action’s in Redux
 Actions are plain JavaScript object that contains information. Action is one of the building blocks of Redux. <br />
 <b>Redux</b> is a state managing library used in JavaScript apps. It is used to manage the data and the state of the application.

<b>Uses of Redux:</b> With the help of redux it is easy to manage state and data. At the start, it is hard to understand but it really helps to build complex applications. In starting, it feels like a lot of work, but it is really helpful.

<b>Action:</b> Actions are JavaScript object that contains information. Actions are the only source of information for the store. It basically carries a payload of information from the application to the store. It only tells us what has happened. Actions have a type property that they must include as type property tells what kind of action to perform. Action can also contain the payload(data field in the action) to describe the action.

This was the small brief about redux. Now, we will discuss the Action object. <br />
<b>Syntax of Action</b> 
 ```javascript

const Actions = {
     type: '',
     payload: ''
}

```


### What are the differences between controlled and uncontrolled components in React?
 In React, Controlled components refer to the components where the state and behaviors are controlled by Parent components. <br />
 while Uncontrolled components are the ones having control of their own state and manage the behaviors on themselves.

<b>Uncontrolled Components:</b> Uncontrolled Components are the components that are not controlled by the React state and are handled by the DOM (Document Object Model). So in order to access any value that has been entered we take the help of refs.

<b>Example:</b> <br />
 ```javascript

// FileName - App.js]

import React, { useRef } from "react";
import "./App.css";

function App() {
	const inputRef = useRef(null);

	function handleSubmit() {
		alert(`Name: ${inputRef.current.value}`);
	}

	return (
		<div className="App">
			<h1 className="geeks">GeeksForGeeks</h1>
			<h3>Uncontrolled Component</h3>
			<form onSubmit={handleSubmit}>
				<label>Name :</label>
				<input
					type="text"
					name="name"
					ref={inputRef}
				/>
				<button type="submit">Submit</button>
			</form>
		</div>
	);
}

export default App;
```
<b>Controlled Components:</b> In React, Controlled Components are those in which form’s data is handled by the component’s state. It takes its current value through props and makes changes through callbacks like onClick, onChange, etc. A parent component manages its own state and passes the new values as props to the controlled component.


<b>Example:</b> <br />
 ```javascript

// FileName - App.js

import { useState } from "react";
import "./App.css";

function App() {
	const [name, setName] = useState("");

	function handleSubmit() {
		alert(`Name: ${name}`);
	}

	return (
		<div className="App">
			<h1 className="geeks">GeeksForGeeks</h1>
			<h3>Controlled Component</h3>
			<form onSubmit={handleSubmit}>
				<label>Name:</label>
				<input
					name="name"
					value={name}
					onChange={(e) =>
						setName(e.target.value)
					}
				/>
				<button type="submit">Submit</button>
			</form>
		</div>
	);
}

export default App;

```


