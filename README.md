# Sketch-Programming: A Minimalist Paradigm for Code Design (LLM transpiler)
Ideas, concepts, tools and examples of sketch programming using LLM

### Extention for VS Code WIP
https://github.com/DmitryOlkhovoi/vscode-sketch-programming

## Overview

**Sketch-programming** (or simply "Sketch") is a revolutionary approach to writing software that prioritizes simplicity, readability, and expressiveness. Unlike traditional programming languages or frameworks, Sketch is not a specific language but a **meta-programming paradigm**—a set of principles, conventions, and syntax patterns designed to abstract away boilerplate code, reduce cognitive overhead, and allow developers to focus on the core logic of their applications.

Sketch can be implemented in any programming language, adapted to any domain, and used for projects of any scale—from small scripts to large systems.

The core idea of Sketch is to *"sketch"* the essence of a program using a minimal, intuitive syntax, leaving the underlying language or runtime to handle the details. By stripping away unnecessary complexity, Sketch enables developers to prototype ideas quickly, communicate designs clearly, and build robust systems with less effort.

## Purpose

The primary goal of Sketch is to make programming more **accessible**, **efficient**, and **enjoyable**. It is especially beneficial for:

- **Beginners**: Those who are overwhelmed by verbose syntax or intricate language rules.
- **Experienced Developers**: Professionals seeking a faster way to prototype, experiment, or design systems.
- **Teams**: Groups aiming to enforce consistent, readable, and maintainable coding patterns across projects.

Sketch achieves its goals by:

- **Providing a keyword-based, declarative syntax** that abstracts repetitive patterns.
- **Emphasizing readability and intent**, making code self-documenting and easy to understand.
- **Supporting rapid iteration**, allowing developers to "sketch" ideas before refining them.
- **Enabling language-agnostic design**, so Sketch can be adapted to any programming language or environment.

## React.js example

```javascript
// @sketch:reactComponent
// @ext:tsx

Component Count

props add = 0
state count = 0

effect {
    console.log("Component mounted");
    
    cleanup {
        console.log("Cleanup");
    }
}

<div onclick="count += add"> Will add {add} </div>
<div>
    Current  count: {count}
</div>
```

transforms to

```typescript
import React, { useState, useEffect } from 'react';

interface Props {
    add?: number;
}

const CountComponent: React.FC<Props> = ({ add = 0 }) => {
    const [count, setCount] = useState<number>(0);

    useEffect(() => {
        console.log("Component mounted");

        return () => {
            console.log("Cleanup");
        };
    }, []);

    const handleClick = () => {
        setCount((prev: number) => prev + add);
    };

    return (
        <div>
            <div onClick={handleClick}> Will add {add} </div>
            <div>
                Current count: {count}
            </div>
        </div>
    );
};

export default CountComponent;
```
