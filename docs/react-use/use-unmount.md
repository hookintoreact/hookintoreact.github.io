# name

useUnmount

# reference

https://github.com/streamich/react-use/blob/master/docs/useUnmount.md

# description

React lifecycle hook that call unmount callback, when component is un-mounted.

# hook

```
const useUnmount = (unmount) => {
  useEffect(() => () => {
    if (unmount) unmount();
  }, []);
};
```

# usage

```
function Demo() {
  useUnmount(() => console.log('UNMOUNTED'));
  return null;
};
```
