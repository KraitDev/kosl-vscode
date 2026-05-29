# Security Policy

## Supported Versions

| Version | Supported |
| ------- | --------- |
| 0.3.x   | Yes ✅   |
| < 0.2.x | No ❌    |

## Reporting a Vulnerability

Do not open public GitHub issues for security vulnerabilities.

Instead, report vulnerabilities privately through:

* GitHub Security Advisories
* repository security reporting features

Include:

* affected version
* reproduction steps
* proof of concept if applicable
* impact description

## Scope

This repository contains the Visual Studio Code extension for KOSL.

Security-sensitive areas include:

* parsing logic
* formatter behavior
* TOML transpilation
* workspace file access
* extension command execution

## Security Goals

The extension aims to:

* avoid arbitrary code execution
* avoid unsafe workspace access
* avoid unsafe shell execution
* avoid malicious regex patterns
* avoid parser crashes on malformed input
* avoid excessive memory consumption

## Parsing Security

KOSL tooling should:

* reject malformed syntax safely
* avoid recursive parser overflows
* avoid catastrophic regex backtracking
* validate UTF-8 input
* enforce deterministic parsing behavior

## Workspace Trust

This extension disables support for:

* untrusted workspaces
* virtual workspaces

because parsing and transpilation features require trusted local workspace access.

## Dependency Policy

Dependencies should remain:

* minimal
* audited
* actively maintained

Avoid adding unnecessary runtime dependencies.

## Responsible Disclosure

Please allow reasonable time for fixes before public disclosure.
