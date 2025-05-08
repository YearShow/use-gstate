---
title: Quick Start
description: Quick Start
---

1. Create a global state from a hook:
```javascript
import { createGStore } from 'create-gstore';
import { useState } from 'react';

// Define a global state from a hook
const useGlobalCounter = createGStore(() => {
  const [count, setCount] = useState(0);
  
  const increment = () => setCount(count + 1);
  const decrement = () => setCount(count - 1);
  
  return { count, increment, decrement };
});
```

2. Use it in any component:
```javascript
function CounterButton() {
  const { count, increment } = useGlobalCounter();
  return <button onClick={increment}>Count: {count}</button>;
}

function CounterDisplay() {
  const count = useGlobalCounter(s => s.count);
  return <div>Current count: {count}</div>;
}
```
