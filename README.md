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
23. [What is the lazyloading in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
24. [What are the differences between controlled and uncontrolled components in React?](https://en.wikipedia.org/wiki/Object-relational_mapping)  <br />
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




