# Buoy - DRAFT

**A cross-platform, compiled programming language and UI framework with a BASIC-like syntax.**

Buoy compiles to native binaries for macOS, Windows, and Linux. It pairs a modern, clean dialect of BASIC with a native UI framework, a full language server, and remote debugging — so you can write desktop applications once and ship real native executables on every platform.

> ⚠️ **Status: pre-release / in active development.** Buoy is not yet at v1. APIs, file formats, and the ABI are still subject to change between releases. This repository is the public home for **releases, release notes, and issue tracking** — see below.

---

## Why Buoy

- **Compiled and native.** Buoy lowers your source to machine code through an LLVM backend and links real native binaries — `.app` bundles on macOS, `.exe` on Windows, ELF executables on Linux. No interpreter, no bundled VM.
- **Readable, BASIC-like syntax.** Familiar `Sub` / `Function` / `Dim` structure, with modern conveniences like `Var` and type inference.
- **One source tree, every platform.** A "project" is just a folder of `.bui` files. There is no project manifest to maintain or merge.
- **True cross-compilation.** Any host can target any platform. Build a macOS app from Linux, or a Windows `.exe` from a Mac — no target-platform SDK required on your machine.
- **First-class tooling.** A Language Server (LSP) drives completion, hover, go-to-definition, and live diagnostics in any LSP-capable editor. A VSCode extension and DAP-based remote debugger are part of the toolchain.
- **Xojo migration path.** Buoy's syntax is Xojo-inspired and aims for source compatibility as a migration route, while deliberately departing from Xojo where its design choices have proven to be friction points.

---

## A quick taste

```basic
Sub Main()
    Var name As String = "world"
    Print "Hello, " + name + "!"
End Sub
```

Variable declaration uses `Dim` or `Var` (they are exact synonyms), with type inference when an initializer is present:

```basic
Dim count As Integer = 0
Var total          = 0.0          ' inferred as Double
Var label          = "Untitled"   ' inferred as String
```

Documentation comments use a triple apostrophe and attach to the declaration that follows:

```basic
''' Returns the area of a circle with the given radius.
Function Area(r As Double) As Double
    Return Pi * r * r
End Function
```

Optional chaining lets you guard member access without an explicit nil check:

```basic
Var name = user?.Profile?.DisplayName   ' Nil if user or Profile is Nil
```

---

## Supported platforms

Buoy produces and runs applications on:

| Platform | Minimum target                                  | Native UI toolkit |
|----------|-------------------------------------------------|-------------------|
| macOS    | macOS 12 (Monterey), Apple Silicon or Intel     | AppKit            |
| Windows  | Windows 10 22H2, x64 or ARM64                   | comctl v6         |
| Linux    | A distro providing GTK 4.10+ (e.g. Ubuntu 22.04, Fedora 38, Debian 12) | GTK 4 |

Universal macOS binaries (Apple Silicon + Intel in one bundle) are supported. On Windows and Linux, ARM64 and x64 are shipped as separate builds.

---

## Installing

> The official download location and the package-manager channels (Homebrew, WinGet, and a Linux PPA/COPR/AUR) are **not finalized yet** and will be announced here. For now, grab a build directly from the [Releases](../../releases) page.

1. Download the toolchain build for your operating system and architecture from [**Releases**](../../releases).
2. Unpack it and put the `bin/` directory on your `PATH`.
3. Verify the install:

   ```sh
   buoy --version
   ```

A minimal first build:

```sh
buoy main.bui -o MyApp
```

To build for a specific target, pass `--target`:

```sh
buoy --target arm64-darwin        main.bui -o MyApp.app
buoy --target x86_64-pc-windows   main.bui -o MyApp.exe
buoy --target x86_64-linux        main.bui -o myapp
buoy --target universal-darwin    main.bui -o MyApp.app
```

The default target is your host platform.

---

## Editor support

Buoy ships a Language Server (`buoy-lsp`) usable from any LSP-compatible editor — VSCode, Neovim, Emacs, JetBrains, Sublime, Helix, and others.

- **VSCode:** install the Buoy extension (link from the release notes). It bundles the language client, build tasks, and the DAP-based debugger.
- **Other editors:** point your editor's LSP client at the `buoy-lsp` binary included in the toolchain. No per-editor language code is needed.

Current LSP capabilities include live diagnostics, completion, signature help, hover, go-to-definition, find-references, document outline, and target-aware filtering under conditional compilation.

---

## Releases & release notes

- **Latest builds:** the [Releases](../../releases) page.
- **What changed:** each release carries its own notes there. Because Buoy is pre-1.0, read the notes before upgrading — breaking changes are called out per release.

If you want notification of new builds, use GitHub's **Watch → Custom → Releases** on this repository.

---

## Reporting issues

Bug reports and feature requests are welcome in the [Issues](../../issues) tab.

A good report includes:

- Your Buoy version (`buoy --version`) and host OS/architecture.
- The **target** you were building or running (`--target ...`), if different from your host.
- A minimal `.bui` snippet that reproduces the problem.
- The exact command you ran and the full output, including any diagnostic codes (e.g. `E1502`, `W310`).
- What you expected to happen versus what actually happened.

Please search existing issues first to avoid duplicates. For questions that aren't bugs, use [Discussions](../../discussions) if it's enabled on this repo.

---

## What's in a Buoy install

A toolchain install contains everything needed to compile for every supported target from your one machine:

- `buoy` — the compiler driver (host-native).
- `buoy-lsp` — the language server (host-native).
- Pre-built per-target runtimes (a shared core, a shared UI runtime, and dead-strippable feature modules).
- Per-target SDK stubs, so the linker is satisfied without a full platform SDK.

The complete cross-target toolchain is well under 100 MB.

---

## Roadmap (high level)

Buoy is being built in stages. Broad direction, subject to change:

- **Now:** the compiler, language server, and per-platform native runtimes; a full object-oriented language with generics, async/await, optional chaining, file I/O, date/time, and HTTP/HTTPS networking built in.
- **Next:** the `.buipkg` library-packaging format so plugin authors can ship first-class bindings; a visual layout editor.
- **Later:** automated binding generation from native headers, richer debugger features (watches, conditional breakpoints), and distribution through OS package managers.

Dates are not promised; follow the releases for what has actually shipped.

---

## License

> License terms are not finalized for this pre-release. The applicable license will be stated here and in a `LICENSE` file once set.

---

*Buoy is a work in progress. Thanks for trying it early — your issue reports directly shape what ships.*
