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
| [**`omnibuf/omnibuf-java`**](https://github.com/omnibuf/omnibuf-java) | Java runtime |
| [**`omnibuf/omnibuf-cs`**](https://github.com/omnibuf/omnibuf-cs) | C# / .NET runtime |

## Tooling

| Repository | Description |
| :--- | :--- |
| [**`omnibuf/omnibuf-cli`**](https://github.com/omnibuf/omnibuf-cli) | `jq`-style CLI for OmniBuf packets |
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
