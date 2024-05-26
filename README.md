# `text` - String Utilities Package

The purpose of `text` is to provide string utilities, but with special considerations relating to web-service(s),
cloud providers, and external APIs.

Interfacing with packages such as AWS and Stripe GO SDKs often require pointer inputs, or working with functions that
return reference values. These cases can result in undesired, unexpected behavior.

The [variadic options](./options.go) the `text` package provides is perhaps the most notable; configurations
can be set that will log unexpected nil or zeroth input arguments.

## Usage

Please see [examples](./example_test.go) for implementation details and usage.

## Documentation

Tool `godoc` is required to render the documentation, which includes examples.

- See [`doc.go`](./doc.go) for code-specific package documentation.

Installation Steps:

1. Install `godoc`.
    ```bash
    go install golang.org/x/tools/cmd/godoc@latest
    ```
1. Backup shell profile and update `PATH`.
    ```bash
    cp ~/.zshrc ~/.zshrc.bak
    printf "export PATH=\"\${PATH}:%s\"\n" "$(go env --json | jq -r ".GOPATH")/bin" >> ~/.zshrc
    source ~/.zshrc
    ```
1. Start the `godoc` server.
    ```bash
    godoc -http=:6060
    ```
1. Open the webpage.
    ```bash
    open "http://localhost:6060/pkg/"
    ```
