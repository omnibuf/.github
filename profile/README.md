<p align="center">
  <a href="https://omnibuf.com">
    <img src="https://raw.githubusercontent.com/omnibuf/.github/main/assets/logo.svg" width="96" height="96" alt="OmniBuf Logo" />
  </a>
</p>

<h1 align="center">OmniBuf</h1>

<p align="center">
  <strong>Fast, self-describing binary wire format for Protocol Buffers, Go, and TypeScript/JavaScript.</strong><br />
  <a href="https://omnibuf.com">Website</a> ·
  <a href="https://omnibuf.com/spec">Wire Specification</a> ·
  <a href="https://omnibuf.com/how-it-works">How It Works</a> ·
  <a href="https://omnibuf.com/go">Go Guide</a> ·
  <a href="https://omnibuf.com/es">TypeScript &amp; JS Guide</a>
</p>

---

OmniBuf replaces multi-branch LEB128 varints and ambiguous wire types with **prefixvarint (`TZCNT`) integers**, **15 distinct wire types**, **packed typed arrays**, and **4-byte little-endian length prefixes** on nested messages.

Every nested sub-message and map entry carries an exact 4-byte byte length (`WireMessage = 9`). Routers, proxies, and stream processors skip or splice nested payloads in $O(1)$ pointer hops. Self-describing packets embed field names in `Field #0`, so CLI tools and debuggers inspect payloads as structured JSON with zero external `.proto` files.

## Language Support

| Repository | Description | Package / Plugin |
| :--- | :--- | :--- |
| [**`omnibuf/omnibuf-go`**](https://github.com/omnibuf/omnibuf-go) | Go implementation, `wire` primitives, and `protoc` / `buf` code generator | `github.com/omnibuf/omnibuf-go` · `protoc-gen-omnibuf` |
| [**`omnibuf/omnibuf-es`**](https://github.com/omnibuf/omnibuf-es) | TypeScript & JavaScript implementation for Node.js, browsers, and edge workers | `@omnibuf/core` · `@omnibuf/node` · `@omnibuf/web` · `@omnibuf/protoc-gen-omnibuf-es` |

## Tooling

| Repository | Description | Install / Binary |
| :--- | :--- | :--- |
| [**`omnibuf/omnibuf-cli`**](https://github.com/omnibuf/omnibuf-cli) | `jq`-style CLI for encoding, decoding, querying, and conformance-testing OmniBuf packets | `brew install omnibuf/tap/omnibuf` · `omnibuf` |
| [**`omnibuf/homebrew-tap`**](https://github.com/omnibuf/homebrew-tap) | Official Homebrew formulas for `omnibuf` and `protoc-gen-omnibuf` | `omnibuf/tap` |
| [**`omnibuf/omnibuf.com`**](https://github.com/omnibuf/omnibuf.com) | Documentation website, interactive benchmarks, and v0.1 wire format specification | [omnibuf.com](https://omnibuf.com) |

## Quickstart

### CLI (`omnibuf`)

Install via Homebrew, `mise`, or the one-line installer, then pipe JSON or `.obuf` packets through `omnibuf`:

```bash
# Install
brew install omnibuf/tap/omnibuf
# or: mise use -g github:omnibuf/omnibuf-cli
# or: curl -fsSL https://omnibuf.com/install.sh | sh

# Encode JSON -> self-describing OmniBuf wire bytes (Field #0 SchemaMeta included automatically)
omnibuf < event.json > event.obuf

# Pretty-print an .obuf packet back to JSON
omnibuf event.obuf

# Query and filter fields directly with jq expressions
omnibuf -r '.neighbors[] | select(.established) | .router' event.obuf
```

### Go (`omnibuf-go`)

```bash
go get github.com/omnibuf/omnibuf-go@latest
```

```go
// Works with protoc-gen-omnibuf generated structs, existing *pb.Message structs, or struct tags:
wireBytes, err := omnibuf.Marshal(msg)
err = omnibuf.Unmarshal(wireBytes, &out)
```

### TypeScript & JavaScript (`omnibuf-es`)

```bash
npm install @omnibuf/core
```

```ts
import { create, toBinary, fromBinary } from '@omnibuf/core';

const bytes = toBinary(PeerUpdateSchema, msg);
const decoded = fromBinary(PeerUpdateSchema, bytes);
```
