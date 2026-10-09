# Masala Programming Language (MVP)

Masala is an experimental, Node.js-based interpreter for `.masala` files. This repository is a starting MVP, not yet a production-ready language or web framework.

## Requirements
- Node.js 20 or newer for development
- Windows, macOS, or Linux for source development

## Run from source
```bash
npm install
node bin/masala.js examples/hello.masala
```

## Try the CLI
```bash
node bin/masala.js --version
node bin/masala.js new my-app
cd my-app
node ../bin/masala.js run src/main.masala
```

## Install the command locally
```bash
npm link
masala --version
masala examples/hello.masala
```

Windows PowerShell may require running `npm link` in an elevated shell depending on npm configuration. If command shims are not on PATH, reopen the terminal and inspect `npm config get prefix`.

## Current syntax
- `bol(expression)` prints values
- `maan name = expression` declares a variable
- `agar condition { ... } warna { ... }` conditional
- `kaam name(args) { ... }` function declaration
- `wapas expression` returns from a function
- numbers, strings, `sach`, `jhooth`, `khaali`
- arithmetic, comparisons, `&&`, `||`, unary `!` and `-`
- `range(end)`, `range(start, end)`, `range(start, end, step)` can be used as a function, but loop syntax is not implemented yet

## Known MVP limitations
No `for`/`har ek` loop syntax yet; no imports/modules; no async/await; no objects/arrays literals; no browser UI compiler; no built-in web server; no package registry; no debugger or language server. Do not use this MVP for untrusted code or production workloads.

## Build a Windows executable (experimental)
```bash
npm install
npx pkg . --targets node20-win-x64 --output dist/masala.exe
```

Packaging tools and target runtimes change over time. If packaging fails, use the source CLI while developing, and follow the current packaging tool documentation. A compiled executable does not by itself create a polished installer or automatic PATH setup.

## Public release plan
1. Put this repository on GitHub.
2. Add tests and a clear roadmap; tag `v0.1.0`.
3. Build and smoke-test Windows binaries on a clean Windows VM.
4. Publish binaries and SHA-256 checksums in GitHub Releases.
5. Later create a signed installer (WiX Toolset or Inno Setup) that installs `masala.exe`, adds its install folder to PATH, and supports uninstall/upgrade.
6. Publish docs, examples, security policy, contribution guide, license, and a compatibility policy.

## License
MIT. Review third-party dependency licenses before redistributing packaged binaries.
"# masala" 
