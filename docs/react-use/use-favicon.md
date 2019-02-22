# name

useFavicon

# reference

https://github.com/streamich/react-use/blob/master/docs/useFavicon.md

# description

React side-effect hook sets the favicon of the page.

# hook

```
const useFavicon = (href) => {
  useEffect(() => {
    const link = document.querySelector("link[rel*='icon']") || document.createElement('link');
    link.type = 'image/x-icon';
    link.rel = 'shortcut icon';
    link.href = href;
    document.getElementsByTagName('head')[0].appendChild(link);
  }, [href]);
};
```

# usage

```
function Demo() {
  useFavicon('https://cdn.sstatic.net/Sites/stackoverflow/img/favicon.ico');

  return null;
};
```
