---
created: 2024-12-09T14:29
updated: 2024-12-09T14:29
---
#javascript

use `controller.abort()` to abort a fetch (mid call)

caveats
- can only be used once
therefore,
- the abort controller should be created (`new`) and consumed in the same block / scope


 refactor this below, should be a function that returns two functions
 
 ```ts
 const [ fetch, abort ] = abortableFetch()
 ```

```tsx

const App = () => {
  const [state, setState] = useState({})

  useEffect(() => {
    const controller = new AbortController()

    fetch("/some_url", {
      signal: controller.signal,
    })
      .then(res => res.json())
      .then(json => setState(json))
  
    return () => {
      controller.abort()
    }
  }, [])

  return (
    <div>
    </div>
  )
}

```