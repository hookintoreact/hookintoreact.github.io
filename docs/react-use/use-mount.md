# name

useMount

# reference

https://github.com/streamich/react-use/blob/master/docs/useMount.md

# description

React lifecycle hook that call mount callback, when component is mounted.

# hook

```
const useMount = (mount) => useEffect(mount, []);
```

# usage

```
function Demo() {
  useMount(() => console.log('MOUNTED'));
  return null;
};
```
