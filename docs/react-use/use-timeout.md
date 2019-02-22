# name

useTimeout

# reference

https://github.com/streamich/react-use/blob/master/docs/useTimeout.md

# description

Returns true after a specified number of milliseconds.

# hook

```
const useTimeout = (ms = 0) => {
  const [ready, setReady] = useState(false);

  useEffect(() => {
    let timer = setTimeout(() => {
      setReady(true);
    }, ms);

    return () => {
      clearTimeout(timer);
    };
  }, [ms]);

  return ready;
};
```

# usage

```
function Demo() {
   const ready = useTimeout(2000);

  return <div>Ready: {ready ? 'Yes' : 'No'}</div>;
};
```
