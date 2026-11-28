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

<p align="center">
  <a href="https://omnibuf.com"><img src="https://img.shields.io/badge/website-omnibuf.com-111111?style=flat&labelColor=111111&color=D4FF33" alt="Website" /></a>
  <a href="https://omnibuf.com/spec"><img src="https://img.shields.io/badge/OmniBuf%20Spec-v1%20DRAFT--1-FF4F18" alt="OmniBuf Spec: v1 DRAFT-1" /></a>
  <a href="https://github.com/omnibuf/.github/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-Apache--2.0-blue.svg" alt="License: Apache-2.0" /></a>
</p>

---

OmniBuf pairs trailing-zero Prefix-Varints with 16 explicit wire types, packed typed arrays, and length-prefixed containers. Proxies and services read or splice individual fields in place. Optional `Field #0` metadata makes raw packets readable as JSON on their own.

## Runtimes

| Repository | Description | Main | Release |
| :--- | :--- | :--- | :--- |
| [**`omnibuf/omnibuf-go`**](https://github.com/omnibuf/omnibuf-go) | Go runtime | [![CI](https://github.com/omnibuf/omnibuf-go/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-go/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-go/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-go/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-es`**](https://github.com/omnibuf/omnibuf-es) | TypeScript & JavaScript runtime | [![CI](https://github.com/omnibuf/omnibuf-es/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-es/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-es/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-es/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-rs`**](https://github.com/omnibuf/omnibuf-rs) | Rust runtime | [![CI](https://github.com/omnibuf/omnibuf-rs/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-rs/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-rs/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-rs/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-py`**](https://github.com/omnibuf/omnibuf-py) | Python runtime | [![CI](https://github.com/omnibuf/omnibuf-py/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-py/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-py/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-py/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-cpp`**](https://github.com/omnibuf/omnibuf-cpp) | C++ runtime | [![CI](https://github.com/omnibuf/omnibuf-cpp/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-cpp/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-cpp/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-cpp/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-java`**](https://github.com/omnibuf/omnibuf-java) | Java & Kotlin runtime | [![CI](https://github.com/omnibuf/omnibuf-java/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-java/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-java/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-java/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-cs`**](https://github.com/omnibuf/omnibuf-cs) | C# / .NET runtime | [![CI](https://github.com/omnibuf/omnibuf-cs/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-cs/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-cs/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-cs/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-swift`**](https://github.com/omnibuf/omnibuf-swift) | Swift runtime | [![CI](https://github.com/omnibuf/omnibuf-swift/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-swift/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-swift/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-swift/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-dart`**](https://github.com/omnibuf/omnibuf-dart) | Dart runtime | [![CI](https://github.com/omnibuf/omnibuf-dart/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-dart/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-dart/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-dart/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-php`**](https://github.com/omnibuf/omnibuf-php) | PHP runtime | [![CI](https://github.com/omnibuf/omnibuf-php/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-php/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-php/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-php/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-elixir`**](https://github.com/omnibuf/omnibuf-elixir) | Elixir runtime | [![CI](https://github.com/omnibuf/omnibuf-elixir/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-elixir/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-elixir/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-elixir/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-nano`**](https://github.com/omnibuf/omnibuf-nano) | Zero-malloc C99 runtime for embedded targets | [![CI](https://github.com/omnibuf/omnibuf-nano/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-nano/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-nano/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-nano/actions/workflows/release.yml) |

## Tooling

| Repository | Description | Main | Release |
| :--- | :--- | :--- | :--- |
| [**`omnibuf/omnibuf-cli`**](https://github.com/omnibuf/omnibuf-cli) | `jq`-style CLI for OmniBuf packets | [![CI](https://github.com/omnibuf/omnibuf-cli/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-cli/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-cli/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-cli/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-devtools`**](https://github.com/omnibuf/omnibuf-devtools) | Browser DevTools extension for inspecting OmniBuf HTTP, ConnectRPC, and gRPC-Web traffic | [![CI](https://github.com/omnibuf/omnibuf-devtools/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-devtools/actions/workflows/ci.yml?query=branch%3Amain) | [![Release](https://github.com/omnibuf/omnibuf-devtools/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-devtools/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-wireshark`**](https://github.com/omnibuf/omnibuf-wireshark) | Wireshark, `tshark`, and `termshark` Lua 5.4 dissector for OmniBuf, Connect, and gRPC traffic | [![CI](https://github.com/omnibuf/omnibuf-wireshark/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-wireshark/actions/workflows/ci.yml?query=branch%3Amain) | - |
| [**`omnibuf/omnibuf-mitmproxy`**](https://github.com/omnibuf/omnibuf-mitmproxy) | `mitmproxy` ContentView addon for inspecting OmniBuf, Connect, and gRPC HTTP traffic | [![CI](https://github.com/omnibuf/omnibuf-mitmproxy/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf-mitmproxy/actions/workflows/ci.yml?query=branch%3Amain) | - |
| [**`omnibuf/omnibuf-vscode`**](https://github.com/omnibuf/omnibuf-vscode) | VS Code extension for viewing and editing `.obuf` files as JSON and hex | - | [![Release](https://github.com/omnibuf/omnibuf-vscode/actions/workflows/release.yml/badge.svg)](https://github.com/omnibuf/omnibuf-vscode/actions/workflows/release.yml) |
| [**`omnibuf/omnibuf-vim`**](https://github.com/omnibuf/omnibuf-vim) | Vim & Neovim plugin for viewing and editing `.obuf` files as JSON and hex | - | - |
| [**`omnibuf/homebrew-tap`**](https://github.com/omnibuf/homebrew-tap) | Homebrew formulas | [![CI](https://github.com/omnibuf/homebrew-tap/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/homebrew-tap/actions/workflows/ci.yml?query=branch%3Amain) | [![Update Formulas](https://github.com/omnibuf/homebrew-tap/actions/workflows/update-formulas.yml/badge.svg?branch=main)](https://github.com/omnibuf/homebrew-tap/actions/workflows/update-formulas.yml?query=branch%3Amain) |
| [**`omnibuf/omnibuf.com`**](https://github.com/omnibuf/omnibuf.com) | Docs, benchmarks, and wire spec | [![CI](https://github.com/omnibuf/omnibuf.com/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf.com/actions/workflows/ci.yml?query=branch%3Amain) | [![Deploy](https://github.com/omnibuf/omnibuf.com/actions/workflows/deploy-pages.yml/badge.svg?branch=main)](https://github.com/omnibuf/omnibuf.com/actions/workflows/deploy-pages.yml?query=branch%3Amain) |

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
