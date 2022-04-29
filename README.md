# golang-modules

log:
```go
package main

import (
	"errors"
	"os"

	"github.com/fatslug/golang-modules/log"
)

func main() {
	log.SetLevel(log.DEBUG)
	log.SetFormat("15:04:05")

	errMessage := errors.New("(Err) - golang generated message")

	log.Print("Print - message without formatting")
	log.Info("Info - message")
	log.Warn("Warn - (warning) message")
	log.Error("Error - message")
	log.Err(errMessage)
	log.Debug("Debug - debug log message")

	log.SetLevel(log.OFF)
	errMessage = errors.New("you will see this message")

	log.Info("")
	log.Warn("you will not see")
	log.Error("these messages")
	log.Err(errMessage)
	log.Debug("or this one")

	log.Fprintf(os.Stdout, "Fprintf - message to stdout")
	log.Print("Print - another print message to highlight fprintf example")
}
```
