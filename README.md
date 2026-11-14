# promise

[![CI](https://github.com/arbachak/promise/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/arbachak/promise/actions/workflows/ci.yml)

A Go library for asynchronous tasks. Work in progress; no public API yet.

Requires Go 1.25 or later. No external Go module dependencies.

## Development

Use the development toolchain specified in [go.mod](go.mod).

```sh
gofmt -w .
go build ./...
go vet ./...
go test -count=1 -timeout=2m ./...
go mod tidy -diff
```

Keep changes focused and open pull requests into `main`. Run the checks above and wait for [CI](https://github.com/arbachak/promise/actions/workflows/ci.yml) to pass before merging.

## License

[MIT](LICENSE).
