# KOSL Support

Syntax highlighting, formatting, validation, and tooling for Krait Object Serialization Language (KOSL).

KOSL is a modern human-readable serialization and configuration language designed to combine:

* `.env` simplicity
* JSON-style structure
* TOML-style usability

while avoiding:

* YAML complexity
* indentation-based parsing
* implicit magic behavior

## Features

* Syntax highlighting
* Auto formatting
* Validation diagnostics
* File icons for `.kosl`
* `Cargo.kosl` support
* Comment support
* Bracket matching
* VS Code snippets
* TOML transpilation tooling
* Cargo integration helpers

## KOSL Example

```kosl
name=my_project
version=0.1.0
edition=2021

supported=windows10,ubuntu24.04,macOS14

dependencies=(
  serde=1.0,
  rand=0.8.5
)

features=(
  default=[std],
  full=[serde,tokio]
)
```

## Arrays

Implicit arrays:

```kosl
targets=linux,windows,macOS
```

Explicit arrays:

```kosl
targets=[
  linux,
  windows,
  macOS
]
```

Nested arrays:

```kosl
matrix=[
  [1,2,3],
  [4,5,6]
]
```

## Objects

Objects use parentheses:

```kosl
build=(
  release=(
    optimize=true
  )
)
```

Inline objects:

```kosl
dependencies=(serde=1.0,rand=0.8.5)
```

## Comments

```kosl
# This is a comment

// This also works
```

## Cargo Compatibility

KOSL includes optional TOML transpilation tooling for Rust projects.

Example:

```text
Cargo.kosl
   ↓
KOSL transpiler
   ↓
Cargo.toml
   ↓
cargo build
```

Example:

```kosl
package=(
  name=my_project,
  version=0.1.0,
  edition=2021
)

dependencies=(
  serde=(
    version=1.0,
    features=[derive]
  )
)
```

---

## Commands

### Format File

```bash
kosl format file.kosl
```

### Validate File

```bash
kosl validate file.kosl
```

### Transpile to TOML

```bash
kosl transpile Cargo.kosl
```

## File Icons

KOSL files include custom file icons for:

* `.kosl`
* `Cargo.kosl`

## Installation

Install from the VS Code Marketplace:

1. Open Extensions
2. Search for `KOSL Support`
3. Install

Or install manually:

```bash
vsce package
```

## Extension Development

```bash
npm install
npm run compile
```

Launch Extension Development Host:

```bash
F5
```

## License

MIT
