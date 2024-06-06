# React JS Interview Questions.
In this repository, I have listed some Interview Questions. <br />
1. [What is React JS?](https://en.wikipedia.org/wiki/Object-relational_mapping) <br /> 
2. [What is the feature of React JS?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
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
24. [What are the differences between controlled and uncontrolled components in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
25. [What are props in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
26. [What is prop drilling in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
27. [Name a few techniques to optimize React app performance.](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
28. [How to pass data between react components?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
29. [What are the lifecycle methods of React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
30. [Can React Hook replace Redux?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
31. [Explain conditional rendering in React.](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
32. [How to pass data between sibling components using React router?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
33. [What are Custom Hooks in React?](#what-are-custom-hooks-in-react)  <br />
34. [Why do React Hooks make use of refs?](https://en.wikipedia.org/wiki/Object-relational_mapping) 




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

#####    Disadvantages of Lazy Loading.
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

####  What are Custom Hooks in React?
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


