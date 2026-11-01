# promise

[![CI](https://github.com/arbachak/promise/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/arbachak/promise/actions/workflows/ci.yml)

A Go library for asynchronous tasks, under development.

**Status:** stage 1 provides the project scaffold, development configuration, and CI. There is no public API yet.

## Requirements

- Go **1.25.0 or later** for the library.
- Go **1.27.3** for development and the quality checks.
- No external Go module dependencies in the library or its tests.

The `go` directive in `go.mod` defines the minimum version. The `toolchain` directive recommends Go 1.27.3 when working in this repository; it does not raise the minimum version for consumers.

## Development

Build and check the package with ordinary Go commands:

```sh
go version
go build ./...
go vet ./...
go test -count=1 -timeout=2m ./...
go mod tidy -diff
```

To list files that need formatting, then format them:

```sh
gofmt -l .
gofmt -w .
```

`gofmt -l` lists differences but does not fail solely because files need formatting. CI explicitly checks that its output is empty.

When checking compatibility with an installed Go 1.25.0 toolchain, set `GOTOOLCHAIN=local` so Go does not switch to the recommended development toolchain. CI also sets `GOWORK=off` to check this module independently.

## Development tools

Use Go 1.27.3 and these pinned tool versions:

- **golangci-lint v2.15.0:** download the official binary for your platform from the [release page](https://github.com/golangci/golangci-lint/releases/tag/v2.15.0) and make it available on `PATH`.
- **govulncheck v1.9.0:** install the CLI separately:

```sh
go install golang.org/x/vuln/cmd/govulncheck@v1.9.0
```

Make sure the Go binary installation directory (`GOBIN`, or `GOPATH/bin` when unset) is on `PATH`. These tools are not dependencies of the library's module and are not required by consumers.

Run the quality checks:

```sh
golangci-lint config verify
golangci-lint run --timeout=2m ./...
govulncheck ./...
```

The linter configuration enables `errcheck`, `govet`, `ineffassign`, `staticcheck`, `unused`, and `errorlint`, including analysis of test files.

## Continuous integration

GitHub Actions runs on pushes to `main`, pull requests, and manual dispatches.

- **Compatibility:** Ubuntu jobs on Go 1.25.0, the latest 1.26.x, and the latest stable Go run build, vet, and `go test -race -count=1 -timeout=2m ./...`. They also verify that the module has no external dependencies.
- **Quality:** a separate job on Go 1.27.3 checks formatting, the linter configuration, static analysis, module tidiness, and known vulnerabilities.

The race detector requires cgo and a supported C compiler. It runs in Ubuntu CI; local Windows users without a configured compiler can run the ordinary test command above.

At this stage, `go test` reports `[no test files]`. Passing CI validates the scaffold and tooling; behavioral tests and race coverage will accompany the implementation.

## License

[MIT](LICENSE).
