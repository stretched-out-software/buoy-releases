# v0.19.3

## Bug Fixes
- When buoy is called through the symlink, it now properly resolves its dependencies to wherever it was installed
- VSCode: When building, if the current directory is not writable, builds now go to a user-configurable folder


---

# v0.19.2

## Bug Fixes
- Revert the default path for buoy now that it's installed in the path
- Wait longer for the debugger to become available before throwing an error
- Now uses a better system for finding debugserver
- When running, if the "main" function cannot be found, the plugin no longer guesses if there are multiple candidates available, showing a dialog for the user to choose one instead.

## Changes
- Set the default path for the buoy binary

## Documentation
- Plan for the cache isolation work


---

# v0.19.0

## New Features
- Implement VSCode Debugger
- Add CString as a real language type, fixing the free after use issue for 3rd party libraries
- Add quoted-path Import syntax (§2.4.6)
- Add default hotkeys for build and run in vscode
- Add Global. qualifier to reach a method-shadowed global function
- Bare calls resolve to sibling/inherited instance methods (§4.3/§4.8)

## Bug Fixes
- Promote re-export/package-qualified imports to spec, fix .bui extension casing
- Detect ambiguous module names across quoted-path imports (E208)
- VSCode builds now go into a folder named "Builds" next to the main project file
- Suppress the codesigning warnings about replacing signatures on macos
- Vscode: methods without return types no longer show " as " in the tooltip
- // and /* */ comments are now colored correctly in vscode
- Syntax coloring for classes after the "new" keyword are no longer offset by 4
- Add #if blocks to the things that get indented
- Fix VSCode paste duplication bug

## Documentation
- Document unqualified method calls + Global. qualifier; add sample
- Add implementation plan for unqualified method calls + Global qualifier
- Add design spec for unqualified method calls + Global qualifier


---

# v0.17.1

## Bug Fixes
- Fixed an LSP bug that caused incorrect constructor errors


---

# v0.17.0

## New Features
- Added cross-platform Splitter control
- Added a sema-synthesized read-only property to control instances for referencing their ParentWindow so control definitions don't need to carry that info with them.
- Application folder now has an icon on macOS
- Add Opening/Opened/Shown/Hidden/Activated/Deactivated lifecycle events sample and docs
- Visibility + active window callbacks
- Visibility + active window callbacks
- Wire native visibility/active callbacks; Activated/Deactivated
- Visibility + active window callbacks
- Expose lifecycle hooks in declarative Window blocks
- Control Shown/Hidden on Visible toggle
- Dynamic AddSubview opens new subtree
- Opening/Opened/Shown first-open orchestration

## Bug Fixes
- Fixed a bug in the errors around numeric + string code
- Buoy version should stay consistent with the package now
- Fixed an bug in class destruction which caused only the most derived class to fire its destructor
- Fix a bug in the vscode plugin which caused properties without default values to be treated like blocks
- Connect GTK lifecycle signals only once
- Null lifecycle callbacks before DestroyWindow (teardown parity)
- Dedup Shown/Hidden so each visibility transition fires once on all platforms
- Null lifecycle callbacks before window destroy (teardown Hidden re-entry)
- Remove app hide/unhide observers on unregister/teardown (use-after-free)

## Documentation
- Tutorial updates for features added since last revisions
- Fixed a few notes about how things are implemented
- Warn that RaiseShown/RaiseHidden bypass the visibility dedup gate
- Add TODO(Task 7/8) to widen lifecycle-callback guard
- Window/control lifecycle events spec + implementation plan
- Add ScaleFactorChanged to Window docs


---

# v0.16.1

## Bug Fixes
- Refactored the declare lib linking and resolution code. See ffi-declare.md for more information.


---

# v0.16.0

## New Features
- Added ContextualMenus
- First pass at a cross-platform best-practices preference system using native solutions. Pass 1 is raw, publicly viewable values.

## Bug Fixes
- Fixed some issues with listbox hit testing
- Stop module-level consts from shadowing same-named locals in codegen
- Align LLVM backend CodeGenOptLevel with the -O IR-pipeline level
- Arm64 CodeGenOptLevel::None crash (which turned out to be a buoy codegen defect — an over-wide i64 store into a 4-byte Int32 slot that smashed the saved frame pointer)

## Documentation
- More packaging research
- Add a plan for declare library resolution
- Control to window identity issue
- Bug closed
- More findings
- Crash findings associated with optimization levels
- Bug report


---

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
