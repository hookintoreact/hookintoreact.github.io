# name

useHover

# reference

https://github.com/streamich/react-use/blob/master/docs/useHover.md

# description

React UI sensor hooks that track if some element is being hovered by a mouse.

- accepts a React element or a function that returns one
- sets react onMouseEnter and onMouseLeave events

# hook

```
const useHover = (element)=> {
  const [state, setState] = useState(false);
  const noop = () => {};
  const onMouseEnter = (originalOnMouseEnter) => (event) => {
    (originalOnMouseEnter || noop)(event);
    setState(true);
  };
  const onMouseLeave = (originalOnMouseLeave) => (event) => {
    (originalOnMouseLeave || noop)(event);
    setState(false);
  };

  if (typeof element === 'function') {
    element = element(state);
  }

  const el = React.cloneElement(element, {
    onMouseEnter: onMouseEnter(element.props.onMouseEnter),
    onMouseLeave: onMouseLeave(element.props.onMouseLeave)
  });

  return [el, state];
};
```

# usage

```
function Demo() {
  const element = (hovered) =>
    <div>
      Hover me! {hovered && 'Thanks!'}
    </div>;
  const [hoverable, hovered] = useHover(element);

  return (
    <div>
      {hoverable}
      <div>{hovered ? 'HOVERED' : ''}</div>
    </div>
  );
};
```
