# hello-go

A **Go** application built with Go 1.23 — cross-compiled to multi-platform binaries by GitHub Actions.

## Run locally

```bash
go run .
```

This requires a working [Go](https://go.dev) installation (1.23+).

## CI pipeline

On every push and pull request, the [CI workflow](.github/workflows/ci.yml) runs:

- Format check (`gofmt -l .`)
- Linting (`go vet ./...`)
- Unit tests (`go test ./... -v`)
- Smoke build

When a tag (`v*`) is pushed, a **release job** cross-compiles standalone binaries for **5 platforms** and publishes them to the [Releases](https://github.com/TEgor1212/hello-go-bin/releases) page:

| Platform       | Binary suffix          |
|----------------|------------------------|
| Linux amd64    | `hello-go-linux-amd64` |
| Linux arm64    | `hello-go-linux-arm64` |
| macOS amd64    | `hello-go-darwin-amd64`|
| macOS arm64    | `hello-go-darwin-arm64`|
| Windows amd64  | `hello-go-windows-amd64.exe` |

Head to the **Releases** tab to download the right binary for your system.