# name

useToggle

# reference

https://github.com/kalcifer/react-powerhooks

# description

This is a hook that lets you toggle between boolean values. It needs an initialValue to work with.

# hook

```
const useToggle = initialValue => {
  const [value, setValue] = useState(initialValue);
  const toggler = useCallback(() => setValue(value => !value));
  return [value, toggler];
};
```

# usage

```
function Demo() {
  const [currentValue, toggleAway] = useToggle(true);
  return (
    <div onClick={toggleAway}>
      {currentValue ? '🍎' : '🍏'}
    </div>
  );
};
```
