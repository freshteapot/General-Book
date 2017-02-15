
# Unmarshalling json into multiple structs

http://attilaolah.eu/2014/09/10/json-and-struct-composition-in-go/


# Indent Json

```
package main

import (
	"bytes"
	"encoding/json"
	"log"
	"os"
)

func main() {
	type Road struct {
		Name   string
		Number int
	}
	roads := []Road{
		{"Diamond Fork", 29},
		{"Sheep Creek", 51},
	}

	b, err := json.Marshal(roads)
	if err != nil {
		log.Fatal(err)
	}

	var out bytes.Buffer
	json.Indent(&out, b, "=", "\t")
	out.WriteTo(os.Stdout)
}
```

Taken from [example on the golang playground](https://golang.org/pkg/encoding/json/#example_Indent)
