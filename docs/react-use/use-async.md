# name

useAsync

# reference

https://github.com/streamich/react-use/blob/master/docs/useAsync.md

# description

React hook that resolves an async function or a function that returns a promise;

# hook

```
const useAsync =(fn, args) => {
  const [state, set] = useState({
    loading: true,
  });
  const memoized = useCallback(fn, args);

  useEffect(() => {
    let mounted = true;
    const promise = memoized();

    promise
      .then(value => {
        if (mounted) {
          set({
            loading: false,
            value,
          });
        }
      }, error => {
        if (mounted) {
          set({
            loading: false,
            error,
          });
        }
      });

    return () => {
      mounted = false;
    };
  }, [memoized]);

  return state;
};
```

# usage

```
// Returns a Promise that resolves after one second.
const fn = () => new Promise((resolve) => {
  setTimeout(() => {
    resolve('RESOLVED');
  }, 1000);
});

function Demo() {
  const {loading, value, error} = useAsync(fn);

  return (
    <div>
      {loading
        ? <div>Loading...</div>
        : <div>Value: {value}</div>
      }
    </div>
  );
};
```
