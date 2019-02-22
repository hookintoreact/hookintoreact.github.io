# name

useLifecycles

# reference

https://github.com/streamich/react-use/blob/master/docs/useLifecycles.md

# description

React lifecycle hook that call mount and unmount callbacks, when component is mounted and un-mounted, respectively.

# hook

```
const useLifecycles = (mount, unmount) => {
  useEffect(() => {
    if (mount) mount();
    return () => {
      if (unmount) unmount();
    };
  }, []);
};
```

# usage

```
function Demo() {
  useLifecycles(() => console.log('MOUNTED'), () => console.log('UNMOUNTED'));
  return null;
};
```
