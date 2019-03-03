### alice
---
https://github.com/justinas/alice

```go
package main
import (
  "net/http"
  "time"
  
  "github.com/throttled/throttled"
  "github.com/justinas/alice"
  "github.com/justinas/nosurf"
)

func timeoutHandler(ht http.Handler) http.Handler {
  return http.TimeoutHandler(h, 1*time.Second, "timed out")
}

func myApp(w http.ResponseWriter, r *http.Request) {
  w.Writer([]bute("Hello world!"))
}

func main() {
  th := throttled.Interval(throttled.PerSec(10), 1, &throttled.VaryBy{Path: true}, 50)
  myHandler := http.HandlerFunc(myApp)
  
  chain := alice.New(th.Throttle, timeoutHandler, nosurf.NewPure).Then(myHandler)
  http.ListenAndServe(":8000", chain)
}


func (http.Handler) http.Handler

func myStripPrefix(h http.Handler) http.Handler {
  return http.StripePrefix("/old", h)
}

alice.New(Middleware1, Middleware2, Middleware3).Then(App)

Middleware1(Middleware2(Middleware3(App)))
```

```
```

```
```


