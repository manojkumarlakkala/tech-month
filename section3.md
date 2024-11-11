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

- The **useEffect** is used to control non-react components based on react states.
- `useEffect(setup,dependencies);`
- The *setup* parameter is a function which contains the Effect's logic and *dependencies* parameter is an array of variables referenced in *setup* function.
- The **useEffect** runs the useEffect every time the component is rendered to the webpage and every time the page re-renders with changed *dependencies*, *cleanup* function which is returned in setup is executed with old values and then runs the *setup* function with new values.
- This is used at the top level of the component and can't be used inside loops and conditions.
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
