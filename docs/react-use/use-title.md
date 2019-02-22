# name

useFavicon

# reference

https://github.com/streamich/react-use/blob/master/docs/useTitle.md

# description

React side-effect hook that sets title of the page.

# hook

```
const useTitle = (title) => {
  useEffect(() => {
    document.title = title;
  }, [title]);
};
```

# usage

```
function Demo() {
  useTitle('Hello world!');

  return null;
};
```
