# Common React Native Components
## `<View>`
- It is a container that holds together all other components inside it.
- `<View><SomeComponent/></View>`

## `<Text>`
- It is used to display text with specified properties.
- `<Text>Hello World!</Text>`

## `<TextInput>`
- It is used to take input from the user.
- `<TextInput defaultValue="Enter what you want to display before the user enters any data"></TextInput>`

## `<Image>`
- It is used to display images.
- `<Image source={{uri:'enter your image uri here'}}/>`

## `<ScrollView>`
- It is a container of components but scrollable.
- `<ScrollView><SomeComponent/></ScrollView>`

# Hooks

## useState

- The **useState** is used to define a state to your component.
- `const [something,setSomething] = useState(initialState);`. This code sets and initial state and returns a function element *setSomething* and current state value *something*.
- The **useState** is used at the top level of the component to declare state variables. It can't be used inside loops or conditions.
- The `setSomething(nextState)` function, returned by the **useState** hook, is used to update the state of a component. However, calling this function doesn't immediately change the state in the current code. Instead, it schedules the state update to happen during the next execution of the component.
- For example, the below function when added to a button increases the count when clicked.
```javascript
export default function Counter() {
  const [count, setCount] = useState(0);

  function handleClick() {
    setCount(count + 1);
  }
}
```

## useEffect

- useEffect is a React Hook that lets you run code when things in your component change, like React states.
- You use it like this: useEffect(setup, dependencies);
- **setup** is a function where you put your code, and **dependencies** is a list of variables that your code depends on.

### How it works:

1. The setup function runs the first time your component shows on the page.


2. Whenever the values in the dependencies list change, React will:

Run a cleanup function (if you return one in setup) to handle old data.

Then, run the setup function again with the new data.




### Important rules:

> You can only use useEffect at the top level > of your component, not inside loops or if > > statements.

- For example, the below function shows the connections and disconnections to a chat room.
```javascript
const [serverUrl, setServerUrl] = useState('https://localhost:1234');

useEffect(() => { //setup function
    const connection = createConnection(serverUrl, roomId);
    connection.connect();
    return () => { //this is the clean up function
      connection.disconnect();
    };
  }, [roomId, serverUrl]); // [roomId,serverUrl] are the dependencies

```

## Few more react hooks
- [useContext](https://react.dev/reference/react/useContext)
- [useReducer](https://react.dev/reference/react/useReducer)
- [useRef](https://react.dev/reference/react/useRef)
- [more](https://react.dev/reference/react/hooks)