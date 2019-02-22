# name

useDocumentTitle

# reference

https://github.com/rehooks/document-title

# hook

```
function useDocumentTitle(title) {
  useEffect(() => {
    document.title = title;
  }, [title])
}
```

# usage

```
function Demo() {
  useDocumentTitle('Page Title');
  return <div/>;
}
```
