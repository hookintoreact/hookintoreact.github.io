# name

useState

# reference

https://reactjs.org/docs/hooks-reference.html#usestate

# description

Returns a stateful value, and a function to update it.

# usage

```
function Demo({initialCount = 0}) {
  const [count, setCount] = useState(initialCount);
  return (
    <>
      Count: {count}
      <button onClick={() => setCount(0)}>Reset</button>
      <button onClick={() => setCount(prevCount => prevCount + 1)}>+</button>
      <button onClick={() => setCount(prevCount => prevCount - 1)}>-</button>
    </>
  );
}
```
