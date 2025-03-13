# Sketch-programming
Ideas, concepts, tools and examples of sketch programming

```javascript
Counter component

state count number = 0;

<button onclick="count += 1">
    { count }
</button>
```

Equals to

```typescript
import React, { useState } from 'react';

const Counter: React.FC = () => {
    const [count, setCount] = useState<number>(0);

    return (
        <button onClick={() => setCount((prev: number) => prev + 1)}>
            {count}
        </button>
    );
};

export default Counter;
```