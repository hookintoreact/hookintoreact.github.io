# name

useDeviceOrientation

# reference

https://github.com/palmerhq/the-platform/

# description

Detect and retrieve current device orientation.

# hook

```
const useDeviceOrientation = () => {
  const [orientation, setOrientation] = React.useState({
    alpha: null,
    beta: null,
    gamma: null,
    absolute: false,
  });

  const handle = e => {
    setOrientation({
      beta: e.beta,
      alpha: e.alpha,
      gamma: e.gamma,
      absolute: e.absolute,
    });
  };

  React.useEffect(() => {
    window.addEventListener('deviceorientation', handle);

    return () => {
      window.removeEventListener('deviceorientation', handle);
    };
  }, []);

  return orientation;
};
```

# usage

```
function Demo() {
  const value = useDeviceOrientation();
  return (
    <div>
      <p>Absolute: {value.absolute}</p>
      <p>Alpha: {value.alpha}</p>
      <p>Beta: {value.beta}</p>
      <p>Gamma: {value.gamma}</p>
    </div>
  );
}
```
