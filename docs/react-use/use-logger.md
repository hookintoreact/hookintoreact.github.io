# name

useLogger

# reference

https://github.com/streamich/react-use/blob/master/docs/useLogger.md

# description

React lifecycle hook that logs in console as component transitions through life-cycles.

- `name` &mdash; component name.
- `props` &mdash; latest props.

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

const useLogger = (name, props) => {
  useLifecycles(() => console.log(`${name} mounted`), () => console.log(`${name} un-mounted`));
  useEffect(() => {
    console.log(`${name} props updated`, props);
  });
};
```

# usage

```
function Demo(props) {
  useLogger('Demo', props);
  return null;
};
```
