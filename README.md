# React JS Interview Questions.
In this repository, I have listed some React Interview Questions. <br />

1. [What is React JS?](#what-is-react-js) <br />
2. [What is Babel?](#what-is-babel) <br />
3. [What is the feature of React JS?](#what-is-the-feature-of-react-js)  <br />
4. [What are the differences between functional and class components?](#what-are-the-differences-between-functional-and-class-components)  <br />
5. [What is React Router?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
6. [What is the virtual DOM? How does react use the virtual DOM to render the UI?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
7. [Explain Types of Hooks in React.](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
8. [What is useState() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
9. [What is useEffect() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
10. [What is useContext() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
11. [What is useReducer() in React?.](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
12. [What is useMemo() in React?](#what-is-usememo-in-react)  <br />
13. [What is useCallback() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
14. [What is useImperativeHandle() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
15. [What is useDebugValue() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
16. [What is useRef() in React?.](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
17. [What is useLayoutEffect() in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
18. [What is JSX? (JAVASCRIPT XML) in React?](#what-is-jsx-javascript-xml-in-react)  <br />
19. [Explain Strict Mode in React? (JAVASCRIPT XML) in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
20. [How to prevent re-renders in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
21. [What is the use of React.PureComponent in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
22. [What are Higher Order Components in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
23. [What are keys in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
24. [What is the lazyloading in React?](#what-is-the-lazyloading-in-react)  <br />
24. [Explain lazyloading with <Suspense> in React.](#explain-lazyloading-with--in-react)  <br />
25. [What are the differences between controlled and uncontrolled components in React?](#what-are-the-differences-between-controlled-and-uncontrolled-components-in-react)  <br />
26. [What are props in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
27. [What is prop drilling in React?](#what-is-prop-drilling-in-react)  <br />
28. [Name a few techniques to optimize React app performance.](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
29. [How to pass data between react components?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
30. [What are the lifecycle methods of React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
31. [Can React Hook replace Redux?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
32. [Explain conditional rendering in React.](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
33. [How to pass data between sibling components using React router?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
34. [What are Custom Hooks in React?](#what-are-custom-hooks-in-react)  <br />
35. [Why do React Hooks make use of refs?](https://en.wikipedia.org/wiki/Object-relational_mapping)
36. [How to implement User Authentication in React?](#how-to-implement-user-authentication-in-react)
37. [Explain Action’s in Redux.](#explain-actions-in-redux)
38. [Explain Root Reducer in React JS.](#explain-actions-in-redux)


### What is React JS?
React is a free and open-source front-end JavaScript library for building user interfaces based on components. It is maintained by Meta and a community of individual developers and companies. React can be used to develop single-page, mobile, or server-rendered applications with frameworks like Next.js.

### What is Babel?
Babel is a JavaScript compiler that can translate markup or programming languages into JavaScript. With Babel, you can use the newest features of JavaScript (ES6 - ECMAScript 2015). Babel is available for different conversions. <br />
React uses Babel to convert JSX into JavaScript.

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
### What is JSX? (JAVASCRIPT XML) in React?
JSX stands for JavaScript XML. JSX allows us to write HTML in React. JSX makes it easier to write and add HTML in React.
JSX allows us to write HTML elements in JavaScript and place them in the DOM without any createElement()  and/or appendChild() methods. JSX converts HTML tags into react elements.

 ```javascript
const myElement = <h1>I Love JSX!</h1>;

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
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

### Explain lazyloading with <Suspense> in React.
<Suspense> lets you display a fallback until its children have finished loading.

 ```javascript
<Suspense fallback={<Loading />}>
  <SomeComponent />
</Suspense>
```

### What is prop drilling in React?
In React, Props Drilling is a practice in which a prop or data is passed from one parent component to one or lower children's components, resulting in multiple levels of the component tree. 

#### Why We Shouldn't Use Prop Drilling?
Prop drilling refers to the process of passing data from a parent component to deeply nested child components by passing props through intermediate components that do not need the data themselves. While this approach can work for small applications, it becomes problematic as the application grows.

#### Reasons to Avoid Prop Drilling
 -> Maintenance Complexity <br />
 -> Scalability Issues <br />
 -> Code Readability <br />
 -> Bug-Prone <br />
 -> Performance <br />

 #### Fixing the Prop Drilling by Using the Context API
 The Context API in React provides a way to share values between components without having to pass props through every level of the tree. This helps to avoid prop drilling 
 and simplifies state management across deeply nested components.



###  What are Custom Hooks in React?
Custom Hooks are functions that start with the word <b>use</b> and can return any value, including other hooks. <br />
They can be used to encapsulate any common functionality that you need to use in multiple components.

<b>Example:</b> You could create a custom hook to fetch data from an API, to manage state, or to handle form validation.

 ```javascript
// Custom hook
import { useState } from 'react';

export const useFetch = (url) => {
  const [data, setData] = useState(null);
  const [isLoading, setIsLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    fetch(url)
      .then((response) => response.json())
      .then((data) => {
        setData(data);
        setIsLoading(false);
      })
      .catch((error) => {
        setError(error);
        setIsLoading(false);
      });
  }, [url]);

  return { data, isLoading, error };
};

// Component
import { useFetch } from './useFetch';

const MyComponent = () => {
  const { data, isLoading, error } = useFetch('https://api.example.com/users');

  if (isLoading) {
    return <div>Loading...</div>;
  }

  if (error) {
    return <div>Error: {error.message}</div>;
  }

  return (
    <ul>
      {data.map((user) => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
};
```

#### Benefits of using custom hooks
-> Reusability <br />
-> Maintainability  <br />
-> Testability  <br />
-> Performance  <br />


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
		alert(`fULL Name: ${inputRef.current.value}`);
	}

	return (
		<div className="App">
			<h1>ReactInterViewQuestion</h1>
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
		alert(`Full Name: ${name}`);
	}

	return (
		<div className="App">
			<h1>ReactInterViewQuestion</h1>
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


