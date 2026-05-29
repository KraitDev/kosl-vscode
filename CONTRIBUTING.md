# Contributing to the KOSL VS Code Extension

Welcome and thanks for showing interest contributing to the KOSL VS Code Extension.

This repository contains the Visual Studio Code extension for Krait Object Serialization Language (KOSL), including:

* syntax highlighting
* formatting integration
* file icons
* language configuration
* snippets
* diagnostics tooling

## Development Setup

Requirements:

* Node.js 20+
* npm
* Visual Studio Code

Clone the repository:

```bash
git clone https://github.com/KraitDev/kosl-vscode.git
cd kosl-vscode
```

Install dependencies:

```bash
npm install
```

Compile:

```bash
npm run compile
```

Launch the extension development host:

```bash
F5
```

## Repository Structure

```text
assets/         Icons and branding
syntaxes/       TextMate grammars
snippets/       VS Code snippets
src/            Extension source
out/            Compiled extension output
```

## Coding Guidelines

* Keep implementations minimal and deterministic
* Avoid unnecessary dependencies
* Maintain formatter consistency
* Keep syntax scopes compatible with major VS Code themes
* Prefer explicit parsing behavior over implicit behavior

## Pull Requests

Before opening a pull request:

* Run formatting
* Ensure the extension compiles
* Test syntax highlighting
* Test file icon behavior
* Verify no broken scopes exist
* Verify `Cargo.kosl` support still works

Recommended checks:

```bash
npm run compile
npm run lint
npm run test
```

## Grammar Contributions

When editing:

```text
syntaxes/kosl.tmLanguage.json
```

ensure:

* scopes remain stable
* highlighting works across themes
* regex patterns are efficient
* catastrophic regex backtracking is avoided

## File Icon Contributions

Icons must:

* be SVG or optimized PNG
* remain readable at small sizes
* support dark/light themes
* follow minimalistic developer-tool aesthetics

## Commit Style

Recommended:

```text
feat: add semantic token support
fix: improve number parsing scopes
docs: update README examples
refactor: simplify grammar patterns
```

## Reporting Issues

Please include:

* VS Code version
* extension version
* operating system
* sample `.kosl` file
* screenshots if highlighting/icons are incorrect

## Roadmap

Planned:

* semantic highlighting
* LSP integration
* formatter improvements
* TOML transpiler integration
* parser diagnostics
* AST visualization

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
