# React Hooks

In React, hooks are special functions that allow you to use state and other React features in functional components. Hooks were introduced in React 16.8 and provide a simpler and more declarative way to write components.

## useState

The useState hook allows you to add state to your functional components. It provides a pair of values: the current state and a function to update that state. Here's an example of how to use useState:

```
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>Counter: {count}</p>
      <button onClick={increment}>Increment</button>
    </div>
  );
}

export default Counter;
```
## useEffect

The useEffect hook allows you to perform side effects in your functional components. You can use it to handle subscriptions, make API calls, update the DOM, and more. Here's a basic example of how to use useEffect:

```
import React, { useEffect } from 'react';

function MyComponent() {
  useEffect(() => {
    // Side effect to perform

    return () => {
      // Clean-up of the side effect (optional)
    };
  }, []);

  return (
    <div>
      <p>Component with side effect</p>
    </div>
  );
}

export default MyComponent;

```
## useRef

The useRef hook allows you to create a mutable reference that can be used to store any value. You can use it to directly access a DOM element, maintain a reference to a mutable value, or save values between renders. Here's an example of how to use useRef:
doesnt run another render.
```
import React, { useRef } from 'react';

function MyComponent() {
  const inputRef = useRef(null);

  const focusInput = () => {
    inputRef.current.focus();
  };

  return (
    <div>
      <input type="text" ref={inputRef} />
      <button onClick={focusInput}>Focus input</button>
    </div>
  );
}

export default MyComponent;

```

## memo
The memo hook allows you to memoize a functional component to avoid unnecessary re-renders. Memo is useful when a component is re-rendered with the same props and states. Here's an example of how to use memo:

```
import React, { memo } from 'react';

const MyComponent = memo((props) => {
  // Component logic and rendering
});

export default MyComponent;


```

## useMemo

The useMemo hook allows you to memoize the result of a function to avoid expensive calculations on every render. You can use it to optimize performance by calculating values that don't change frequently. Here's an example of how to use useMemo:

```
import React, { useMemo } from 'react';

function MyComponent({ value }) {
  const expensiveResult = useMemo(() => {
    // Expensive calculations using the received value
    return /* result */;
  }, [value]);

  return (
    <div>
      <p>Expensive result: {expensiveResult}</p>
    </div>
  );
}

export default MyComponent;

```
## useCallback

The useCallback hook allows you to memoize a function to avoid recreation on every render. It is useful when passing functions as props to child components and you want to prevent unnecessary re-renders. Here's an example of how to use useCallback:

```
import React, { useCallback } from 'react';

function MyComponent({ onClick }) {
  const handleClick = useCallback(() => {
    // Click event logic
  }, []);

  return (
    <div>
      <button onClick={handleClick}>Do something</button>
    </div>
  );
}

export default MyComponent;

```

**These are just some of the hooks available in React! Each hook has its own purpose and advantages, allowing you to write cleaner and more reusable components.**
