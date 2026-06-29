# v0.15.2

## Bug Fixes
- Move LSP background thread to a pthread so it can use a bigger heap
- Fixed a bug in the LSP that was causing crashes in VSCode

## Documentation
- Prefs design spec
- Toolbar changes


---

# v0.15.1

## Bug Fixes
- Fixed two Windows regressions around the hidpi change, listbox and cross-screen dragging.

## Documentation
- Add specs for preferences and the splitter control


---

# v0.15.0

## New Features
- Hidpi support for all platforms
- MacOS hidpi

## Bug Fixes
- HTMLView dlls are no longer copied into every windows app


---

# v0.14.0

## New Features
- feat: expand drag and drop to text controls and views

## Bug Fixes
- fix: Added a --generate-manifest option to help buipkg developers generate correctly formatted packages
- fix: Fixed a few buipkg bugs that showed up on unit tests
- fix: make it so the package loader looks in the link folder first and then moves to the runtime because on macOS and Linux, the files would be the same. Doing this makes packages ~32% smaller.
- fix: added an option to buoy for specifying the install name when building a library
- fix: When libraries are built with buoy, we no longer just overwrite the header that's there. The compiler is now smart enough to combine the declares into groups as necessary with #if pragmas.
- fix: When building buoy libraries for a package there's now a new option named "--emit-declares"  which will also create a .bui file containing the declares for accessing each of the public methods that's needed for the packaging process.


---

# v0.13.1

## Bug Fixes
- fix: Standardized the macOS minimum deploy target across all libraries
- fix: Strings stored in records and arrays are now initialized with ""
- fix: strings are now initialized with ""


---

# v0.13.0


---

# v0.13.0

## New Features
- feat: Now using dmg for macOS distribution
- feat: Canvas Drag and Drop
- feat: make Point a built-in type and fix all the previous uses

## Bug Fixes
- fix: defensively copy FFI `As String` returns into owned buffers


---

# v0.12.1

## Bug Fixes
- fix: LSP now gets its word list from the token list


---

# v0.12.0

## New Features
- feat: Added HTMLView
- feat: add Int8, UInt8, UInt32 and UInt64

## Bug Fixes
- fix: linker no longer points at files on a developer machine


---

# v0.11.2

## Bug Fixes
- fix: the run command in VSCode now correctly detects when the project was built as an app bundle


---

# v0.11.1

## Bug Fixes
- fix: rewrote lsp caching code
- fix: Autocomplete now works in VSCode for projects that are not in the buoy directory


---

# v0.11.0

## New Features
- feat: make it so modules can be embedded in packages, which ultimately lets us create controls
- feat: add some more compiler directives. TargetDesktop, TargetConsole and TargetLibrary feat: if unspecified, the compiler now attempts to auto-detect if an app is a desktop or a console app so TargetDesktop and TargetConsole can be set correctly.
- feat: Added a class for dealing with JSON.
- feat: Added BinaryStream, TextInputStream, TextOutputStream
- feat: Added Bytes class for dealing with raw data

## Bug Fixes
- fix: fixed an issue where if the LSP needed to guess what to do with an open #if statement, it would always choose mac/arm. Now it will choose the platform/cpu combination of the LSP.
- fix: fixed a frontend compiler bug that caused autocompletion failures in LSP and therefore VSCode
- fix: add icon and readme to the vscode extension
- fix: Bytes now throws an OutOfBoundsException if you try to access something outside instead of crashing


---

# v0.10.0

## New Features
- feat: Structures may now be placed inside classes
- feat: Enums can now be embedded in structures

## Bug Fixes
- fix: fix enum and struct scoping inside a class


---

# v0.9.0

## New Features
- feat: Namespace

## Bug Fixes
- fix: fix a compile crash for Select Case with a string variable that's inside a method
- fix: bug fixes


---

# v0.8.2


---

# v0.6.1

## Bug Fixes
- fix: fix a signing/notarization issue
- fix: make it so we sign any binaries we will be shipping
- fix: remove another sample that is causing problems


---

# v0.6.0

## New Features
- feat: add buipkg for packaging 3rd party libraries and bui projects into cross-platform reusable code
- feat: add release & retain to object

## Bug Fixes
- fix: repair regex patterns and fix line endings
- fix: buoy now detects an invalid target and shows an appropriate error
- fix: update the sqlite and zip packages are cross platform vendored
- fix: wrapping a class reference in an Optional or Result no longer returns the wrong value
- fix: make `Then` optional on `#If` and `#ElseIf` directives


---

# v0.5.0

## New Features
- feat: add partial methods to partial classes


---

# v0.4.4

## New Features

- Partial Classes
- VSCode 
  - now has a Run File command with a play button in the editor title bar
  - added a `buoy.compiler.path` setting to specify compiler binary path
  - macOS VSCode extension now resolves to the `Darwin-universal` LSP so we don't have to ship two different builds

## Fixes

- Update system requirements

---

# V0.2.0

## New Features

- macOS builds are now notarized
- First x86-64 build of Buoy compiler
- Cross-platform intrinsic control sizes
- StackView control
- Basic URLConnection class
- BBEdit CLM

## Fixes

- Removed duplicate library warnings
- Fix missing library issue

---

# 2026.06.19

### First Public Release
