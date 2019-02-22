# name

useUpdate

# reference

https://github.com/streamich/react-use/blob/master/docs/useUpdate.md

# description

Returns true after a specified number of milliseconds.

# hook

```
const useUpdate = () => useState(0)[1];
```

# usage

```
function Demo() {
  const update = useUpdate();
  return (
    <>
      <div>Time: {Date.now()}</div>
      <button onClick={update}>Update</button>
    </>
  );
};
```
