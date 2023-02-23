# golang-guide

```go
#!title: JSON Demo
import "fmt"
import "context"
import "encoding/json"

type SimpleObject struct {
	Name        string          `json:"name"`
	Description string          `json:"description"`
    Location string `json:"location,omitempty"`
	Context     context.Context `json:"-"` // will be removed by JSON parsing
}

obj := SimpleObject{
    Name: "name",
    Description: "desc",
}
if data, err := json.Marshal(obj); err == nil {
    fmt.Println(string(data))
} else {
    fmt.Println(err)
}
```