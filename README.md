# Go: Getting Started

## Modules
- Initialize module
```shell
go mod init webserver
```
- Add `main.go`
- Run Module
```shell
go run webserver
```

## Primitive Data Types
```go
var i int // declare varible i
i = 42 // initialization

var f float32 = 3.14

firstName := "Arthur" // string

b := true // bool

c := complex(3,4) // complex number
re, im := real(c), imag(c)
```

## Pointers
No Pointer arithmatic!
```go
var firstName *string = new(string)
*firstName = "Arthur"

anotherName := "King"
ptr := &anotherName
```

## Constants
```go
const pi = 3.14151 // intialize on same line
```

## iota and constant expressions
```go
package main
import (
	"fmt"
)
const (
	first = iota
	second
)

const (
	third = iota
)

func main() {
	fmt.Println(first, second, third)
}
```
Result
```
0 1 0
```

## Collection Data Types
- Array
```go
var arr [3]int // arr is int array with 3 elems
arr[0] = 1
arr[1] = 2
arr[2] = 3
fmt.Println(arr)
```

```go
arr := [3]int{1, 2, 3}
fmt.Println(arr)
```
- Slice
```go
arr := [3]int{1, 2, 3}
slice := arr[:] // points to data that arr is keeping
arr[1] = 21
slice[2] = 41
fmt.Println(arr)
fmt.Println(slice)
```

```go
slice := []int{1, 2, 3}
fmt.Println(slice)

slice = append(slice, 4, 42)
fmt.Println(slice)

s2 := slice[1:]
s3 := slice[:2]
s4 := slice[1:2]
fmt.Println(s2, s3, s4)
```

- Maps
```go
m := map[string]int{"foo": 42}
fmt.Println(m)

delete(m, "foo")
fmt.Println(m)
```

- Structs
```go
type user struct {
	ID int
	FirstName string
	LastName string
}

var u user
u.ID = 0
u.FirstName = "Dhananjay"
u.LastName = "Latkar"
fmt.Println(u)

u2 := user(ID: 1, FirstName: "Mihir", LastName: "Latkar")
fmt.Println(u2)
```

## Functions

```go
import "errors"
func startWebServer(port int, numberOfRetries int) (int, error) {
	return port, errors.New("Something went wrong")
}
```

## Flow Control

- Loops
```go
var i int
for i < 5 {
	println(i)
	i++
	if i == 3 {
		break
		// continue
	}
}
```

```go
for i := 0; i < 5; i++ {
	println(i)
}
```
```go
i := 5
for {
	println(i)
}
```
```go
slice := []int{1, 2, 3}
for i, v := range slice {
	println(i, v)
}
```

- Panic
```go
panic("something's wrong, I can feel it")
```

- if/else
```go
if a == b {
	println("a and b are equal")
} else if a > b {
	println("a is greater than b")
} else {
	println("a is less that b")
}
```

- switch
```go
r  := HTTPRequest{Method: "GET"}
case r.Method {
	case "GET":
		println("Get request")
	case "PUT":
		println("Put request")
		fallthrough
	case "HEAD":
		println("Head request")
	default:
		println("Unhandled request")
}
```
