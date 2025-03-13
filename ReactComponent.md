I want to use simplified syntax to create React components.
Here you can find main ideas:

// Functions
makeItems() {
    return new Array();
}

Equals to

function makeItems() {
    return new Array();
}

or

const makeItems = () => new Array();

// State
state counter = 0;
or
state counter number = 0;

Equals to 
const { counter, setCounter } = useState<number>(0);

This is an example with initializer function
state items () => {
    return new Array()
}

Equals to 

const { counter, setCounter } = useState(() => new Array());

or

makeItems() {
    return new Array();
}

state items makeItems

const { counter, setCounter } = useState(makeItems);

Equals to 
const { counter, setCounter } = useState<number>(0);
//

// JSX

<div onClick="count = count + 1">
    Add count
</div>

or 

<div onclick="count += 1">
    Add count
</div>

Equals to

<div onClick={() => setCount(count + 1)}>
    Add count
</div>

//

Apply the same ideas to other hooks.
Use Typescript to describe types even if they not specified