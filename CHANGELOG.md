# v0.23.0

## New Features
- Add default parameter values and named arguments (§9.4.3/§9.4.4) (#29)
- Add Shell class - persistent shell subprocess with sync Execute() and async DataAvailable (#24)
- Ad Currency type

## Bug Fixes
- Calling a method on a Nil property no longer SegFaults
- Bytes.ToString() no longer just returns "(NULL)"


---

# v0.22.0

## New Features
- Networking sockets — TCPSocket, UDPSocket, IPCSocket, ServerSocket (#23)
- Support Boolean <-> Numeric conversion via CType (#22)
- Add Closure type and Lambda expressions for value-capturing closures
- Start shipping packages with Buoy

## Bug Fixes
- Putting multiple statements on the same line is now a compile error
- Add a method to the compiler for extracting the internal class name(s)


---

# v0.21.0

## New Features
- Add HashPasswordScrypt/Bcrypt/Pbkdf2, unify VerifyPassword across all four algorithms
- Add Crypto.KdfAlgorithms and the 5-arg DeriveKey overload
- Add KDF algorithm dispatch, Scrypt/PBKDF2/bcrypt native shim functions
- Add Bytes.ToHex/ToBase32/ToBase64/ToBase58 and their Shared decode counterparts
- Add hex/Base32/Base64/Base58 encoding to the Bytes native runtime
- Add HotpGenerator/TotpGenerator (RFC 4226/6238)
- Add HOTP/TOTP native shim (RFC 4226/6238)
- Add CFStringRef for macOS declare toll-free bridging with NSString

## Bug Fixes
- Str() now converts Int32 values instead of silently returning empty string
- Add time() to the Linux libc cross-compile stub
- Package declares/*.bui unreachable for zero-Import consumers
- ParseOtpCode rejects non-digit codes; add TOTP live-time test coverage
- Bui_crypto_totp_verify caps driftSteps upper bound
- Bui_crypto_totp_verify hangs on negative driftSteps
- Finish String api
- Buipkgs no longer include source from binary packages.
- Unhandled exceptions in subclass destructors no longer leak
- Byref in non-declare settings no longer crash

## Documentation
- Extend index.md's bytes.md row with the new encoding methods
- Fix stale sample header, file 2 follow-up bug reports from final review
- Commit revised design spec and implementation plan for password/KDF phase
- Document Scrypt/bcrypt/PBKDF2 password hashing and the new KDF algorithms
- Add HotpGenerator/TotpGenerator to the crypto index.md row
- Document HotpGenerator/TotpGenerator
- Add HotpGenerator/TotpGenerator sample demonstration


---

# v0.20.0

## New Features
- Redirect console output to log sink on Windows (§28.8)
- Redirect console output to log sink on Unix (§28.8)
- Add UnsupportedOperationException sample; close README gaps
- Reject programs that reach both RunAsService and the UI runtime (E2801)
- Add UnsupportedOperationException and the headless UI-control guard
- Wire Application.RunAsService to the Windows SCM backend
- Add Windows SCM backend for buoy_service (Application.RunAsService)
- Add Application.RunAsService and the five Service* events
- Add buoy_service native runtime (macOS + Linux) for Application.RunAsService
- Main() function now supports returning an integer exitcode which is sent back to the OS
- Add Treat...As...Else Treat...End Treat narrowing statement
- Add T(x) cast-constructor sugar for classes and interfaces
- Add IllegalCastException for failed checked downcasts
- Add IllegalCastException for failed checked downcasts
- Add Toolbar demo sample on macOS
- Add SystemIcon via SF Symbols for Toolbar icons on macOS
- Add Toolbar structural items (Separator/Space/FlexibleSpace) on macOS
- Add Toolbar CustomView on macOS
- Add Toolbar SearchField on macOS
- Add Toolbar MenuButton on macOS
- Add Toolbar Group with SelectionMode enforcement on macOS
- Add Toolbar ToggleButton on macOS
- Add Toolbar foundation (Button) on macOS

## Bug Fixes
- Re-point Windows std handles after redirect; harden service-test signal timing
- Block signals before spawning the log-reader thread on Unix
- Reconcile E2801 docs with actual buoy_ui-link-breadth behavior
- Address Task 3 review findings (stale comment, hardcoded /tmp path)
- Address final whole-branch review findings for Windows SCM support
- Url_connection.bui now connects to ipify
- Rename result variable in service.bui (Result is a reserved keyword)
- Synchronize Windows SCM status reporting and honor checkpoint/wait-hint
- Name buoy_service as its own library in the Stage A addendum
- LSP now merges Partial Class fragments across stdlib files
- Correct review findings on runtime/stdlib/service.bui
- Add Linux pre-built buoy_service binaries; fix third_party ignore pattern
- VSCode extension is now smarter about what main() file it should be building when you Run or Debug
- Remove duplicate Treat entry from keyword-other-buoy grammar group
- Correct misleading IfStmt-scoping comment in Treat desugaring
- Bui_ui_window_content_height excludes the toolbar band
- Consolidate toolbar band positioning into one helper
- Rebuild macOS/Linux runtimes so they land in Git LFS properly
- VSCode now reports less things as errors that are not.
- Toolbar SF Symbol icons render solid black instead of adaptive
- Correct 2x-oversized Toolbar SF Symbol/Picture icons on Retina
- Add Visible round-trip test coverage for ToolbarItem

## Documentation
- File bug report for Windows CRT fd-table initialization gap
- Document console-to-log-sink redirect (§28.8)
- Add Stage D implementation plan (console-to-log-sink redirect, §28.8)
- Api consistency skill
- Document UI/service mutual exclusion and UnsupportedOperationException
- Document Application.RunAsService Windows SCM support (Stage B)
- Document Application.RunAsService (Stage A: macOS + Linux)
- Mention T(x) cast sugar and Treat narrowing in README status section
- Document T(x) cast sugar, IllegalCastException, and Treat narrowing
- Mention IllegalCastException in exception hierarchy references
- Narrow the older-macOS verification gap to confirmed arm64 13+
- Correct Toolbar macOS plan after Task 1/7 implementation findings
- Note older-macOS visual verification as a known gap
- Document the duplicate-Identifier InvalidArgumentException
- Document Toolbar (macOS core increment)
- Add TODO at bui_ui_toolbaritem_set_toggled for Group direct-assign gap
- Add Toolbar macOS implementation plan


---

# v0.19.4

## Bug Fixes
- Fixed a bug that caused stdlib linking to fail
- Re-add lib/runtime binaries as proper LFS pointers
- Add --app-type console to window-block/window-events/counter_window_fixture tests


---

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
