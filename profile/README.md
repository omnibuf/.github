<p align="center">
  <a href="https://omnibuf.com">
    <img src="https://raw.githubusercontent.com/omnibuf/.github/main/assets/logo.svg" width="96" height="96" alt="OmniBuf Logo" />
  </a>
</p>

<h1 align="center">OmniBuf</h1>

<p align="center">
  <strong>Self-describing binary wire format for Protocol Buffers and native types.</strong><br />
  <a href="https://omnibuf.com">Website</a> ·
  <a href="https://omnibuf.com/spec">Wire Specification</a> ·
  <a href="https://omnibuf.com/how-it-works">How It Works</a> ·
  <a href="https://omnibuf.com/cli">CLI</a>
</p>

---

OmniBuf pairs trailing-zero Prefix-Varints with 16 explicit wire types, packed typed arrays, and length-prefixed containers. Proxies and services read or splice individual fields in place. Optional `Field #0` metadata makes raw packets readable as JSON on their own.

## Runtimes

| Repository | Description |
| :--- | :--- |
| [**`omnibuf/omnibuf-go`**](https://github.com/omnibuf/omnibuf-go) | Go runtime |
| [**`omnibuf/omnibuf-es`**](https://github.com/omnibuf/omnibuf-es) | TypeScript & JavaScript runtime |
| [**`omnibuf/omnibuf-rs`**](https://github.com/omnibuf/omnibuf-rs) | Rust runtime |
| [**`omnibuf/omnibuf-py`**](https://github.com/omnibuf/omnibuf-py) | Python runtime |
| [**`omnibuf/omnibuf-cpp`**](https://github.com/omnibuf/omnibuf-cpp) | C++ runtime |
| [**`omnibuf/omnibuf-java`**](https://github.com/omnibuf/omnibuf-java) | Java & Kotlin runtime |
| [**`omnibuf/omnibuf-cs`**](https://github.com/omnibuf/omnibuf-cs) | C# / .NET runtime |
| [**`omnibuf/omnibuf-swift`**](https://github.com/omnibuf/omnibuf-swift) | Swift runtime |
| [**`omnibuf/omnibuf-dart`**](https://github.com/omnibuf/omnibuf-dart) | Dart runtime |
| [**`omnibuf/omnibuf-php`**](https://github.com/omnibuf/omnibuf-php) | PHP runtime |
| [**`omnibuf/omnibuf-elixir`**](https://github.com/omnibuf/omnibuf-elixir) | Elixir runtime |
| [**`omnibuf/omnibuf-nano`**](https://github.com/omnibuf/omnibuf-nano) | Zero-malloc C99 runtime for embedded targets |

## Tooling

| Repository | Description |
| :--- | :--- |
| [**`omnibuf/omnibuf-cli`**](https://github.com/omnibuf/omnibuf-cli) | `jq`-style CLI for OmniBuf packets |
| [**`omnibuf/omnibuf-devtools`**](https://github.com/omnibuf/omnibuf-devtools) | Browser DevTools extension for inspecting OmniBuf HTTP, ConnectRPC, and gRPC-Web traffic |
| [**`omnibuf/omnibuf-wireshark`**](https://github.com/omnibuf/omnibuf-wireshark) | Wireshark, `tshark`, and `termshark` Lua 5.4 dissector for OmniBuf, Connect, and gRPC traffic |
| [**`omnibuf/omnibuf-mitmproxy`**](https://github.com/omnibuf/omnibuf-mitmproxy) | `mitmproxy` ContentView addon for inspecting OmniBuf, Connect, and gRPC HTTP traffic |
| [**`omnibuf/omnibuf-vscode`**](https://github.com/omnibuf/omnibuf-vscode) | VS Code extension for viewing and editing `.obuf` files as JSON and hex |
| [**`omnibuf/omnibuf-vim`**](https://github.com/omnibuf/omnibuf-vim) | Vim & Neovim plugin for viewing and editing `.obuf` files as JSON and hex |
| [**`omnibuf/homebrew-tap`**](https://github.com/omnibuf/homebrew-tap) | Homebrew formulas |
| [**`omnibuf/omnibuf.com`**](https://github.com/omnibuf/omnibuf.com) | Docs, benchmarks, and wire spec |

## CLI Quickstart

```bash
# Install via Homebrew, mise, or shell script
brew install omnibuf/tap/omnibuf
# mise use -g github:omnibuf/omnibuf-cli
# curl -fsSL https://omnibuf.com/install.sh | sh

# Encode JSON to a self-describing OmniBuf packet
omnibuf < event.json > event.obuf

# Decode back to JSON or query fields with jq expressions
omnibuf event.obuf
omnibuf -r '.neighbors[] | select(.established) | .router' event.obuf
```

Language guides and benchmarks live on [omnibuf.com](https://omnibuf.com).
