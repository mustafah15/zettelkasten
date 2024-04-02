---
tags:
  - goLang
type:
  - literature
related: "[[Go Lang]]"
---
In Go, the functional options pattern is a powerful and flexible design pattern used to configure and customize objects or functions during initialization. It is a cleaner and more idiomatic way to handle configuration parameters, especially when dealing with structs and complex APIs. In this blog post, we'll explore the functional options pattern in Go and provide code examples to help you understand how to implement it effectively.

### The Problem

Imagine you have a struct in Go that represents a configurable entity. Traditionally, you might provide multiple constructors or initialization functions with parameters to set various configuration options. However, this can quickly become unwieldy, especially as the number of configuration options increases.

This is where the functional options pattern comes to the rescue, allowing you to create flexible and readable initialization code.

### The Functional Options Pattern

The functional options pattern leverages Go's support for first-class functions to provide a clean and extensible way to configure objects. Instead of passing a multitude of parameters to a constructor, you pass one or more functions, each responsible for configuring a specific aspect of the object.

Here's the basic structure of how it works:

1. Define a struct to represent your configurable object.
2. Create functions that accept pointers to the struct and return functions that configure specific options.
3. Use these option functions to customize the struct during initialization.


```GO
import (
    "fmt"
)

// ConfigurableService represents a service with configurable options.
type ConfigurableService struct {
    Host    string
    Port    int
    Timeout int
}

// OptionFunc is a type for functions that configure the ConfigurableService.
type OptionFunc func(*ConfigurableService)

// WithHost configures the service's host.
func WithHost(host string) OptionFunc {
    return func(cs *ConfigurableService) {
        cs.Host = host
    }
}

// WithPort configures the service's port.
func WithPort(port int) OptionFunc {
    return func(cs *ConfigurableService) {
        cs.Port = port
    }
}

// WithTimeout configures the service's timeout.
func WithTimeout(timeout int) OptionFunc {
    return func(cs *ConfigurableService) {
        cs.Timeout = timeout
    }
}

// NewConfigurableService initializes a ConfigurableService with provided options.
func NewConfigurableService(options ...OptionFunc) *ConfigurableService {
    service := &ConfigurableService{
        Host:    "localhost",
        Port:    8080,
        Timeout: 30,
    }

    for _, option := range options {
        option(service)
    }

    return service
}

func main() {
    // Create a new ConfigurableService with custom options.
    service := NewConfigurableService(
        WithHost("example.com"),
        WithPort(9000),
        WithTimeout(60),
    )

    // Print the configured service.
    fmt.Printf("Host: %s, Port: %d, Timeout: %d\n", service.Host, service.Port, service.Timeout)
}
```

### Benefits of the Functional Options Pattern

- **Readability**: The functional options pattern makes it clear what each option does, leading to more self-documenting and maintainable code.
- **Flexibility**: You can add new configuration options without changing the function signatures or introducing breaking changes.
- **Default Values**: You can provide default values for configuration options, making it easy to use the object with minimal configuration.
- **Compile-Time Safety**: Configuration options are checked at compile time, reducing runtime errors.
- **Builder Pattern**: It's similar to the builder pattern and allows you to chain configuration options together for more complex setups.