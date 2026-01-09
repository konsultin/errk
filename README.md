# errk - Error Handling Library

🔴 Custom Konsultin error handling with tracing, metadata, and error wrapping support.

## Installation

```bash
go get github.com/konsultin/errk
```

## Quick Start

```go
import "github.com/konsultin/errk"

// Create a new error
err := errk.NewError("USER_NOT_FOUND", "User does not exist")

// With namespace
err := errk.NewError("VALIDATION_FAILED", "Email is invalid",
    errk.WithNamespace("auth"),
)

// Add trace information
err = err.Trace()

// Wrap existing error
err = errk.NewError("CONFIG_ERROR", "Failed to load config").Wrap(originalErr)

// Add metadata
err = err.AddMetadata("user_id", 123)
```

## Features

- **Structured Errors** - Organize errors with namespace and code
- **Error Wrapping** - Wrap underlying errors while maintaining context
- **Tracing** - Automatic trace collection showing error origin
- **Metadata** - Attach arbitrary data for debugging
- **Error Comparison** - Works with Go's standard `errors.Is()`

## License

MIT License - see [LICENSE](LICENSE)
