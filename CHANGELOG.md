# v0.71.0

## New Features
- WebSocket server support (HTTPServer 1.1.0)
- Websocket-chat sample with ctest compile and cross registration
- WebSocket registry, CloseAllWebSockets, cross-thread/TLS/scale tests
- WebSocket keepalive pings and idle close 1001
- WebSocket close handshake and exactly-once OnClose
- WebSocket receive loop, message callbacks, serialized send
- WebSocket route registration and upgrade handshake
- WebSocket frame codec, UTF-8 and close-code validation
- Pure-Buoy SHA-1 and WebSocket accept key
- Shim uses core text style members (TextControl Bold/Italic/Underline/TextColor/Multiline, Graphics styles)
- Window layout properties (Minimum/Maximum size, Changed, FullScreen, chrome flags) and Refresh
- Graphics Bold/Italic/Underline/FontUnit (stored) plus API 1 ForeColor/PenWidth/StringWidth aliases
- Rebuild DesktopToolbar around the API verified in real Xojo
- DesktopToolbarButton wrapper with DesktopToolbar.Add/Dispatch (DBKit pattern)
- RectControl base with Open/Close/CreatePane events (event list inferred, unverified)
- Graphics short forms copy Xojo's pixel geometry (probe 17): w+1 fills, pixel-center strokes and lines
- MemoryBlock.Compress levels copy Xojo's observed behavior (Normal stores; None/Fast/Best deflate alike; XFL bytes)
- Ambient Graphics DrawingColor/PenSize/FontName/FontSize and Xojo's short draw forms
- Global Quit([exitCode]) in the shim (converter-emitted Xojo global)
- DesktopApplication Opening/Closing events with RaiseOpening/RaiseClosing
- Global WindowCount() in the shim (converter-emitted Xojo global)
- DatabaseException() and DatabaseException(message, errorNumber) constructors (Xojo's three forms)
- Variant.Type and Variant.Type* constants with values read from real Xojo (probes 11-12)
- URLConnection.RequestHeader(name) = value (Xojo's assignment form)
- Shim matches real Xojo for CString/WString/PString edge cases and ToString(format) (probes 8-10)
- Decompress throws on corruption/bad CRC like real Xojo (probes 7-8)
- MemoryBlock.Decompress is lenient like real Xojo (probe 6)
- MemoryBlock.Compress/Decompress emit and read gzip, per real-Xojo probe 4
- DesktopWindow members (Left/Top/Handle/Hide/ShowModal/Show) as extensions on Window
- Shim String.Length/Middle count codepoints, not bytes (STR-1, shim-only)
- Shim UInt64.ToString(locale, format) keeps all 64 bits (STR-10 follow-up)
- Zlib.Compress/Decompress in the zip package + MemoryBlock.Compress/Decompress in the shim (COL-12)
- JSONItem.Constructor(jsonString) parses at construction (COL-10)
- Shim Double/Integer.ToString(locale, format) number patterns + Locale.Raw (STR-10)
- Shim JSONException.Offset as 0-based Position (COL-11)
- Shim Dictionary(keyComparison) with KeyComparisonDelegate (COL-2)
- Shim ParseJSONTree + GenerateJSON(Variant) over Dictionary/VariantArray trees (COL-9)
- Shim MemoryBlock BooleanValue/Long/CString/PString/WString + CType to String (COL-13)
- Shim byte-wise String methods LeftBytes..ChrByte (STR-5)
- Shim Dictionary keys are Variants; add Variant.StringValue (COL-1)
- Shim DesktopListBox.AddRow/AddRowAt use ParamArray (unlimited arity)
- ParamArray on class methods, Shared methods and constructors (LANG-11)
- Color = / <> compare by value (all four channels, exact)
- Width/Height are content size on Windows too; add Window.TitleBarHeight and MenuBarHeight
- Xojo shim uses core Rect (drop XojoRect), Window.Bounds= validates fields
- Core Rect class in stdlib geometry; rename user-declared Rect structure in structures sample/docs
- Xojo shim Keyboard members (Shared extensions on core Keyboard)
- Live keyboard state, Linux runtime (GDK modifiers, X11 XQueryKeymap)
- Live keyboard state, Windows runtime (GetAsyncKeyState)
- Live Keyboard.Modifiers / Keyboard.IsKeyDown API (macOS runtime + stdlib)
- Xojo shim XojoRect (Xojo Rect) and Window.Bounds, B3/B4 review leftovers
- Xojo shim SortWith (1-3 companion arrays) and a real RandomizeSeed
- Core in-place stable Array.Sort (optional comparator) and Random.Randomize
- Xojo shim global CDbl (locale-aware ParseNumber with lenient Val fallback)
- THR-10 - Xojo Timer.CancelCallLater(AddressOf Foo) cancels by delegate identity (LANG-15)
- LANG-13 - Super.<member> = value (all assignment forms) parses and runs
- LANG-12 Xojo shim — FolderItem.Path/Extension (FS-3), IPCSocket.Path (NET-18)
- LANG-12 docs, sample and additive sweep (0 DIFF)
- LANG-12 tooling — formatter keeps keyword-named fields/members, member-name highlighting, reserved-words note
- LANG-12 keywords as member names — parser member-name positions, Structure/Enum lookahead, grammar
- LANG-10 Xojo shim - XojoThread retired, Thread extensions, THR-1/THR-2
- LANG-10 docs, sample and additive sweep (0 DIFF)
- LANG-10 instance Thread.Start — keep-alive, start-once, never-started guards, Run dispatch
- LANG-10 Thread subclass declaration — Inherits/IsA/CType Thread, gated Run event, Start built-in, LSP
- LANG-9 Xojo shim payoff (NUM-1, COL-14, FS-13 Single)
- LANG-9 Single members, extensions, BinaryStream, editor support, docs and sample
- LANG-9 Single across the C ABI (Declare, float Structures, variadic)
- LANG-9 Single text, hashing, sorting and String.Format
- LANG-9 Single arithmetic, comparison, literal adaptation, Select Case, folding
- LANG-9 Single type, conversions and declaration sites
- LANG-8 Xojo shim payoff (NUM-3, NUM-4, THR-13 Enter/Leave)
- LANG-8 editor support, docs and sample
- LANG-8 Shared extensions on Currency and the sized integers
- LANG-8 rule B for Mutex/Atomic/Condition/Thread/Task and Currency built-ins
- LANG-8 Currency and sized-int extension receivers with Integer fallback
- Xojo shim uses generic extensions (LANG-7 task 4)
- LANG-7 LSP completion/hover for generic extensions, docs, sample
- LANG-7 generic class receivers, generic Assigns setters, concrete-beats-generic ranking
- LANG-7 generic-receiver extensions — templates, on-demand instantiation, Array receivers
- RowSet is Iterable — For Each row In rs
- Xojo shim uses For Each protocol (Dictionary, RowSet.Rows(), XQL pin) (LANG-6 task 4)
- LSP hover for inferred For Each variables, docs and sample (LANG-6 task 3)
- Stack/Queue/Set/Map iterable via For Each (LANG-6 task 2)
- For Each over Iterable / Iterator (LANG-6 task 1)
- Xojo shim implicit conversions via LANG-5 (Variant, MemoryBlock, FolderItem)
- LANG-5 task 4 — LSP hover unwraps conversion plumbing, docs, sample
- Converting overload tier — user conversions at call arguments (LANG-5 task 3)
- User conversions at every assignment-like site, outgoing first (LANG-5 task 2)
- Incoming Shared Operator CType declaration and explicit CType (LANG-5 task 1)
- Xojo shim uses LANG-4 overloads (Read(count, enc), IndexOf order, Write(addr, data), Connect(), DrawLine/Rotate)
- Never-callable extension warning, overload-aware completion, docs and sample (LANG-4 task 5)
- Shared extensions overload real Shared methods and builtin namespace members (LANG-4 task 4)
- Builtin String/Array methods compete with same-named extensions by signature (LANG-4 task 3)
- Rule B overloads between real members and extensions on class/interface receivers (LANG-4 task 2)
- Extension member-call visibility follows imports (LANG-4 task 1)
- Xojo shim uses LANG-3 extension setters (BytePosition, RawData, AllowCertificateValidation, Timer.RunMode/Enabled, DatabaseFile)
- Property/Assigns collision errors and Private instance Assigns-extension visibility (LANG-3 task 5)
- T.Foo = v / T.Foo(k) = v Shared extension setters on class, Structure, Enum and primitive targets (LANG-3 task 4)
- X.Foo(k) = v indexed extension setters incl. interface receivers; resolveAssignsSetter takes precomputed types (LANG-3 task 3)
- X.Foo = v dispatches to paren-less Assigns Subs and extension setters (LANG-3 task 2)
- Register Assigns extensions, keep them out of ordinary dispatch (LANG-3 task 1)
- Extensions dispatch through subclass and interface receivers (LANG-2)
- Xojo API 2.0 compatibility shim package (Import Xojo)
- Shared extensions (LANG-1) — attach Shared members to existing types

## Bug Fixes
- BuoyScript JIT crashes on arrays, Throw/Try and trapping operations
- BuoyScript JIT rejects the stdlib prelude (Iterable/Iterator reserved-name error)
- Guard the WebSocket 101 write, reject HTTP/1.0 upgrades
- Base WebSocket idle close on elapsed time, resync late ticks
- Report 1006 when the peer drops TCP after our close
- Close 1002 on 64-bit frame length with top bit set
- Member access and method calls on literal and parenthesized receivers
- Bump markdown-it to 14.3.3 (alert #75)
- Bump ip-address to 10.7.4 (alerts #65, #76, #78, #79)
- Bump brace-expansion to 1.1.21 / 2.1.7 / 5.0.12 (alerts #84-#92)
- Bump fast-uri override to 3.1.8 (alerts #62, #63, #77, #80, #83, #93)
- Bump undici to 7.30.1 (alerts #64, #66-#74)
- Bump @modelcontextprotocol/sdk to 1.31.0 (alert #82)
- Bump proxy-addr to 2.0.8 (alert #81)
- Every codegen diagnostic fails the build instead of dropping code
- PagePanel/TabView pages fill their container on Linux; Windows late-added and resized pages too
- Lazy property first access is thread-safe (once-guard)
- Reject Print of Enum/Delegate/Closure/Nil in Sema; fatal codegen for Print and unknown method
- A ''' doc comment inside an Enum body is a comment, not a phantom member
- Class Assigns setters pick the best-matching overload, not the first assignable one
- Handle blocks in generic classes override the base event
- HashCode of a Double or Single canonicalizes signed zero
- Constant-folded Double division by zero yields the IEEE result, not 0
- UInt64 ordering compares unsigned and unsigned kinds convert to Double as magnitudes
- Sqlite3 binds and reads integers through SQLite's 64-bit API
- Double <> is the unordered not-equal, so NaN <> NaN is True
- Reject method-only modifiers on Property (E426) and property redeclaration (E427); add @Shadows
- Reject = / <> and Select Case on Arrays and Structures in Sema
- Ambient Graphics state is saved/restored by SaveState/RestoreState; FontSize 0 reads back 0 (real Xojo probe 13)
- Sub-int enum Declare parameters/results get signext/zeroext by their backing type
- Declares aliasing one C symbol keep their own prototype (wrapper per signature); drop XojoZip import-order rule
- Shim JSON error offsets and malformed-number rejection match real Xojo (COL-11)
- Shim JSON numbers typed by source text; JSONException.Offset counts characters
- Shim EncodeURLComponent encodes ~; DecodeURLComponent passes malformed escapes through (STR-12)
- With subject owned for the whole block (borrowed subject use-after-free)
- Cast-sugar paren-less member call segfault; live Weak Lambda capture read segfault
- Assigns setters convert key/index arguments through user conversions
- Pin decided by the accessor called; Block bodies capture nothing (E162)
- E171 once-per-site dedupe keyed by file, never while diagnostics are held
- Array.First / Array.Last results are Heap borrows, so they get pinned
- Pin a Heap-rooted receiver around hand-written property accessors
- Writes to uncaptured outer locals in a Lambda are E171; captures owned
- Case Nil arms are Nil tests; ?. on Optional names ?.; doc fixes
- = Nil / <> Nil and Nil receivers never call a user Operator =/<>
- Is/IsNot are identity or Nil tests, never a user Operator =/<>
- For Each tracks the live array; pin marks are per-function
- Pin borrowed operands of operators and builtin calls
- Own a Heap-rooted method receiver for the whole call
- Pin an array-property element argument against later arguments
- The array For Each loop variable owns its element
- Get-only computed Structure property used as storage
- MacOS Toolbar Group NSToolbarItemGroup was stored without a retain
- MacOS 27+ Toolbar.Size=Small leaves icons unchanged
- MacOS Toolbar.Size=Small also switches the window to UnifiedCompact
- Toolbar Small icons - MRC ownership of base image, symbol configuration, leak
- MacOS Toolbar.Size=Small visibly shrinks toolbar icons
- Geometry setters round 1 - Linux set_frame no-op for same-size/maximized windows, stale comments, docs, tests
- Single-axis geometry setters keep live native geometry for the other axes
- Round 2 minors - Windows finished-Resized carries final size, macOS keeps X/Y and content across toolbar changes (incl. Size/DisplayMode), Linux skips maximized/fullscreen and keeps content on DisplayMode, docs
- Keep content size across MenuBar/Toolbar changes; DPI-safe placement; review minors
- Single-placement Bounds= via bui_ui_window_set_content_frame; Windows l2p floors negatives; Linux comment fix
- Exact content-origin placement via bui_ui_window_set_content_origin; internal helpers; Windows minimized fallback
- Confine None/Ok/Err wildcard to call-argument matching; pin If(); statement guard
- Check cairo surface status in Linux draw_picture_rect; single setFrame for macOS window placement
- DesktopWindow.Left/Top and Bounds Left/Top are the content-area origin
- None/Some/Ok/Err as call arguments type from the parameter; Array.Sort If() comparator
- Window X/Y, Screen.Top, mouse screen Y use top-left global space; set_frame_d content-size semantics
- Keyboard.IsKeyDown on Wayland via GTK key-event tracking
- Signature-check built-in callback AddressOf; raw AddressOf through If and comparisons; located error for untyped AddressOf
- Type AddressOf operator operands and Some() args; codegen backstop for untyped AddressOf
- Signature-check AddressOf at any depth (nested Append/Insert, mixed literals, If of arrays); Optional hint
- AddressOf placeholder cannot escape via Array/Optional; type array literals from context
- Cap canvas side at 32767, guard GTK cairo surfaces, SetMaxSize <=0 means no limit on macOS
- Reject inferred AddressOf locals; pin AddressOf in If/CType/Array.Append/Insert
- Sanitize splitter/window size inputs, overflow-check Picture canvas
- Review round 3 - Block literal Double return uses the exact sized-integer range
- Review round 2 - checked Double to sized integer for ParamArray elements, Lambda returns and Optional.Or
- Review round 1 - exact Double-to-sized-integer range on args/returns/setters/delegates, generic shadowing only by callable symbols
- Parked Lows - generic diagnostics once per declaration, Array lookup message, XojoRegEx end re-seek, harness/vendor/sqlite3 hygiene
- Reject + - * / \ Mod on two same-typed non-numeric operands (Boolean/Ptr/Structure/Class/DateTime/Enum/String) with a located error
- A call through a same-named local/parameter delegate is never inferred as a user generic function
- Double/Single to integer/Currency conversion raises OverflowException on NaN, Inf and out-of-range values
- Clamp window/control geometry in all runtimes (macOS NSException abort, Win/GTK garbage)
- Builtin-method sync checker recognises Array.LastIndex's 1..2 arity from merged multidim arrays
- G1 review round 1 (run line, Sort hover, stale shim comments, exact collision diagnostics in rect/keyboard docs)
- String Sort/Sorted/SortOrder order case-insensitively (like <), Sorted is stable
- Keyboard review round 1 (non-flaky tests, doc caveats, comments, sample test pattern)
- Sort/Sorted/SortOrder accept sized ints and Currency; SortWith key errors land on the call line; internal comparator type names
- Array.Sort review round 1 (closure ARC over-retain, comparator writes, throw leaks), SortOrder, anonymous comparator types
- Stack-probe checker bounds look-back at function boundaries, handles non-PE input, self-test; vendor scripts delete stale tree only after download; gate build-runtime-windows
- C1 review round 1 - timer harness accepts ticking title; E406 recovery; generic-instantiation diagnostics; docs example
- Build Windows minizip/plutovg/zlib/libyaml/libpng with stack probes; symbol-independent probe checker as a CTest gate; reseal zip + sqlite3, rebuild buoy_system/buoy_picture
- CType/TryCast/IsA accept any Type as the target (generic instantiations, multi-arg generics, arrays)
- Redeclaring an inherited method without Overrides is a compile error (E425)
- Str() supports Int8/UInt8/Int16/UInt16/UInt32/UInt64; unsupported arg types are a Sema error with a location
- Generic inference types arithmetic like checkExpr (Integer / Integer is Integer; And/Or on ints; sized-int arithmetic)
- Build Windows PCRE2 with stack probes (regex.dll + static lib); reseal regex package
- Integer / Integer lowers to exact sdiv/udiv (and folds exactly)
- Random/Shuffle use a per-thread xoshiro256** generator, OS-seeded; add Random.Seed
- Allow ByRef String in Buoy-to-Buoy Delegates; E1509 only where a delegate statically crosses the C boundary (user ruling)
- Reject MenuItem/Menu reuse with InvalidArgumentException; macOS uncaught-NSException hardening; Linux detached TabView teardown double free
- Bare For with no existing variable is E812 (spec 8.4 restored, user ruling)
- For round 2 - rotated unit-step latch, counter mutation, implicit counter scope, E801 message, counter hover
- Selector Boolean arguments pass as 1-byte BOOL (i8 zeroext arm64 / signext x86_64)
- Reject ByRef String in Export and Delegate signatures (E1509); document CString return lifetimes
- For review follow-ups - narrow start, loop-scoped counter, Step 0 (E801), Int64 max, spec/docs, LSP counter
- Int8/Int16/UInt8/UInt16 FFI arguments and results carry signext/zeroext
- An Export with a String parameter exports the copying C-ABI entry
- Selector sends pass and return by-value Structures with the C ABI (objc_msgSend_stret on x86_64)
- Numeric Select Case widens, handles Currency and unsigned UInt64, and checks Range bounds (B9)
- Typed For loops - the counter, bounds and Step use the declared type (B8)
- UInt64 mixed with a signed variable keeps signed \ and Mod; suppress Const cascade; docs
- User-declared Release/Retain/Hash/TypeName wins over the Object builtin
- Integer division by zero throws DivideByZeroException; reject Double operands to IntDiv/And/Or/Xor in Sema
- System V byval and AArch64 HFAs for large by-value Structures; register exhaustion
- Classify every small by-value Structure for the C ABI (Declare, Delegate, callbacks, Export)
- A computed (Get/Set) property passed ByRef is copy-in/copy-out
- Pin a borrowed argument that a later argument of the same call may free
- Delegate calls use the C ABI for Structure arguments and results
- A Shared property owns its Optional/Result/Structure value
- New passes constructor arguments through emitCallArg (ByRef params)
- Lambda/AddressOf/Block literals survive generic instantiation
- A by-value Closure parameter is owned by the callee
- Builtin-method sync check and String namespace signatures know the caseSensitive flag
- Thread.Join(ms) clamps its remaining time, uses a monotonic deadline, and self-joins return at once on every platform
- Release fresh Optional/Result/Structure temporaries passed to compiled callees or used as receivers
- Closure/Delegate calls with Structure and ByRef parameters use the shared call-argument lowering
- Lambda parameters are owned like Function parameters (adoptObjectParam)
- Thread join - failed pthread_join (self-join) no longer marks consumed; timed loser uses remaining time; Windows Join is CAS-guarded against racing Detach; IsRunning during Join never probes
- Array Of Optional/Result owns its payloads; by-value aggregate params are callee-owned copies; ByRef aggregate assignment owns; Closure property initializer claimed (B3d)
- Thread join/detach state changes are atomic (CAS); Join on borrowed Current() box is a no-op; Windows Id() 0 after Detach; internal state field renamed; stale Xojo comments
- Lambda Using (o) of an Optional/Result local owns the payload
- Optional/Result/Structure holders own what they store (class property, Some(<Structure>), nested Structure, Stack.Pop/Queue.Dequeue)
- Structure class/array fields follow the closure-field ownership rule (copy, assign, Return, array, capture, For Each)
- Thread handle ownership - Current()/Main() release no longer detaches the live thread; Join/Detach consume the handle; Windows Id() is the OS thread id
- Await / RaiseEvent pass-throughs inherit their operand's freshness; re-scope Structure-closure and temporary-argument reports
- Fail-safe Optional/Result/Structure ownership - fresh is a whitelist, If arms normalised to +1, element loads borrowed
- Lift declaration-time ByRef-receiver rejections (Currency/sized ints/Single/Assigns); docs and negative tests updated
- By-value large-Structure extension receiver is passed through a temp copy in method-call form
- Balance Optional/Result property-getter results (claim in Dim/assign/Return, release unclaimed reads)
- Structure Closure fields own their env (literal, Dim, copy, assign, Return, arrays, Lambda capture)
- Optional/Result locals with class or closure payloads are ARC-balanced on Dim-copy, assignment, Return and inline .Value
- Lambda Using (x) retains and releases captured Array and Closure values
- Array.Reversed retains String (and every ARC) element via emitElemRetain
- Extension method-call form honors ByRef/byval-indirect parameters (receiver and args)
- Retain/release closures stored in arrays and Optional/Result payloads (use-after-free of the closure env)
- Select Case / With / SyncLock keep their subject temporaries alive until the end of the statement (adopted into a statement scope, released once on every exit path)
- Array element stores convert the value to the element type and size the slot by it (arr(i)=v, obj.Prop(i)=v, Append, Insert); docs; bug reports to done/
- Integer-backed Enum converts numerically (sitofp/trunc) into Double/sized-int/Single stores; hand-rolled store sites use coerceNumericStore
- Windows link uses /OPT:SAFEICF + COFF addrsig so distinct functions keep distinct delegate identity
- LANG-15 - Select Case on Delegate/CString/class selectors uses the = lowering and Sema checks; shim comment, spec Boolean wording, Windows-only function-folding note
- LANG-15 - delegate/CString/CFStringRef equality compares pointers; Sema rejects mismatched-delegate comparison and non-ordered </>/<=/>= operands
- LANG-13 - reject Super in Shared methods and non-capturing Lambdas in Sema
- LANG-12 final review — With-shorthand formatter guard, doc/comment fixes, reseal Xojo pkg
- LANG-12 Structure field takes a keyword name only when As follows; FuncName grammar
- LANG-10 reject Shared members named like Thread built-ins; document generic caveat
- LANG-10 shim - Stop() wakes a worker blocked in CheckPaused
- LANG-10 publish the thread handle before Run starts
- LANG-9 final-review findings — round Single text, ByRef Single Declare, Double vs Single/Integer overloads, order-independent array literals
- LANG-9 Windows arm64 variadic HFA params, reject Single-struct Export by value off AArch64 HFA
- LANG-9 Print of Single released its string; pin NaN/-0.0 to Double behavior
- LANG-9 user operators returning Single, IEEE division throughout adapted Single literals
- LANG-9 Integer-backed Enum converts to Single by value
- LANG-8 final-review minors — ByRef value receivers rejected, hover id lookup, Join row, docs, negative ToHex padding
- LANG-8 sized-int namespace head in statement position
- LANG-8 keep Retain/Release/Hash/TypeName off Object extensions on built-in classes
- LANG-7 re-review — speculative late generic classes for unpicked candidates
- LANG-7 final-review findings (I-1..I-4, M-1..M-5)
- LANG-7 generic Assigns extensions get LANG-3's receiver-kind and ByRef checks at declaration
- LANG-7 receiver-fixed type parameters accept assignable args; one diag per generic body
- Reserve Iterable/Iterator, guard duplicate generic interfaces, LSP walkers descend Try/With/Lambda (LANG-6 final fix)
- Key class itables by Sema's mangled interface name (LANG-6 task 1 fix 1)
- Copy OperatorDecl::isShared in generic-class instantiation clone
- LANG-5 final review — outgoing self-recursion guard, incoming operator visibility, Assigns ByRef, docs
- Apply argument conversions on interface-dispatch calls (LANG-5 task 3 fix 1)
- No implicit conversion into C inside C's incoming operator; one type spelling for E909/trace (LANG-5 task 2 fix 1)
- Interface source implemented by the target or any subclass keeps the downcast in explicit CType (LANG-5 task 1 fix 1b)
- Incoming CType from unrelated class/interface sources, Shared-outgoing and Optional-param errors, injective operator names (LANG-5 task 1 fix 1)
- Always filter inaccessible real members, with or without an extension (LANG-4 follow-up round 1)
- Inaccessible real members don't compete with extensions (LANG-4 follow-up)
- LANG-4 final-review fixes (Xojo IndexOf case rule, UDP port validation, real-miss visibility hint, iface named-arg diagnostic, pinned builtin param types)
- UDPSocket.Write(address, data) raises on a bare host with no peer port; docs and ParamArray wording (LANG-4 task 6 fix 1)
- Completion offers extensions only where Sema's visibility allows (LANG-4 task 5 fix 1)
- Shared extensions hide farther same-signature ones; union builtin ties defer to the builtin chain (LANG-4 task 4 fix 1)
- LANG-3 final-review findings — navigable setter write sites, ByRef Assigns receiver rejected, With compound-assign crash, plain-Sub write message, setter completion detail
- Xojo shim side tables validate owner identity via weak refs; document Timer limits
- Reject ordinary calls to setter-only Shared Assigns extensions on every target kind (LANG-3 task 4 review)
- Keep free-function duplicate error and enforce Assigns Sub visibility for x.Foo = v (LANG-3 task 2 review)

## Changes
- Rebuilt buoyscript package
- Rebuild and test the buoyscript package on every compiler change
- Rebuild and reseal the buoyscript package from current compiler sources
- Remove HTTPServer-1.0.0.buipkg; 1.1.0 is the only shipped package
- Bump HTTPServer package to 1.1.0 and seal HTTPServer-1.1.0.buipkg
- Bounded waits for server-side state in websocket-server
- Docs/tests: STR-1 verified against Xojo; STR-2 findings recorded
- Keyboard members match real Xojo 2024r4.2 (MenuShortcutKey; no MenuKey/AsyncCapsLock)
- Introspection matches real Xojo 2024r4.2 where names allow
- Legacy RSA (PKCS#1 v1.5/SHA-1, OAEP/SHA-1, 512+ bit keys); shim: XojoCrypto.RSA*
- XojoCrypto matches real Xojo 2024r4.2 (enum numbers, SHA3, edge cases)
- Dictionary and AddUserInterfaceUpdate take ParamArray Pair Of Variant, Variant
- TextEncoding/Encodings and ConvertEncoding match real Xojo 2024r4.2
- XojoRegEx matches real Xojo 2024r4.2 on groups, replacement escapes and error text
- Select Case over a temporary String selector (report already fixed); close report
- Merge main into feat/xojo-shim (TextControl style props); rebuild all buoy_ui runtimes from merged sources
- DesktopToolbar handlers work from a subclass of a subclass (converter shape)
- Drop Graphics.FontUnit / FontUnits; font sizes are always points
- Probe 15 (real Xojo) pins corrupt/trailing/multi-member gzip behavior; shim already matched
- Merge main (string UTF-8 invariant, PR #587) into feat/xojo-shim; move XojoText/XojoCore/XojoData to the new string API
- Hiding accessors, Block captures, self-freeing closure (red / guard)
- Lambda outer-local writes, accessor receivers, First/Last borrows (red)
- Case Nil / Case Is = Nil arms and ?. on Optional (red)
- = Nil / <> Nil, Nil receivers and synthesized guards skip user operators (red)
- Is/IsNot must be identity/Nil tests, never user Operator = (red)
- Color = / <> must compare by value (red)
- Docs,test: For Each mutation is E803 by spec; live-count loop is current behaviour only
- Red - For Each over an array that shrinks or grows mid-loop
- Red tests - borrowed values freed by a later operand, argument or callee
- For Each ownership test - expect live element reads per iteration
- Red test - For Each loop variable must own its array element
- Red tests - Get-only computed Structure property used as storage
- Red test - Toolbar Group NSToolbarItemGroup must survive pool drain
- Red test - Small must not shrink toolbar icons on macOS 27+
- Red test - Toolbar.Size=Small must switch the window to UnifiedCompact
- Red test - macOS Toolbar.Size=Small must shrink item icons
- Failing regression test for stale-cache single-axis geometry setters (red)
- Window-chrome demo gains Toolbar/MenuBar toggles, toolbar size/mode cycling and a Resized log
- Width/Height preserved when a MenuBar/Toolbar is attached (red: Windows menu 260->241, macOS toolbar 260->292)
- Window content-size and chrome-height tests (red: Windows Width is outer; TitleBarHeight/MenuBarHeight missing)
- Negative content origin round trip; macOS Move clamps to Min/MaxSize (red on macOS min/max)
- Xojo-rect exact content-origin asserts, plain Window coverage, no Windows tolerance
- Docs/test: raw-Ptr callback note, screen/window/pointer coordinate wording; drop tautological window-topleft assertion
- None/Some/Ok/Err call arguments and Array.Sort If() comparator (red)
- Xojo DesktopWindow.Top/Bounds.Top are content-area top (red)
- Window X/Y and Screen.Top are top-left space; set_frame_d content-size semantics (red on macOS)
- Built-in callback AddressOf must be signature-checked; raw AddressOf via If/compare keeps working; Print AddressOf is a located error (red)
- AddressOf operator operands and Some() arguments must be typed and checked (red)
- AddressOf in nested-array Append/Insert and mixed literals must be signature-checked (red)
- AddressOf placeholder escapes through arrays/Optional; typed array literal forms (red)
- Picture side cap 32767, tighten WinHugeSize (red)
- Inferred AddressOf local must be a located error (red)
- Splitter NaN sizes, oversized Picture, Window min/max extremes (red)
- Fix round 3 - Block literal Double return into a sized integer uses the exact range (IR pin, red)
- Fix round 2 - Double to sized integer through ParamArray elements, Lambda returns and Optional.Or (red)
- Fix round 1 - sized Double conversion through args/returns/setters/delegates, generic inference with non-callable same-named symbols (red)
- Parked Lows - generic E404/E425 once per declaration + 'Box Of String' spelling, Array lookup element-type message, XojoRegEx end re-seek, UInt64/Int8 sort coverage (red)
- Arithmetic on two Booleans/Ptrs/Structures/Classes/DateTimes must be a located Sema error (red)
- A same-named local/param/property delegate call must not be captured by a user generic function (red)
- Double/Single to integer conversion of NaN/Inf/out-of-range must raise OverflowException (red)
- Window/control geometry setters must clamp extreme and NaN values (red)
- Pin rank-2 rejection of Sort/SortOrder/Sorted after merging multidim arrays
- Failing tests for core Rect and case-insensitive String sort (red)
- Docs+sample: keyboard state page, UI sample, tests registration, Xojo docs
- Keyboard-state unit test (red, API not yet implemented)
- Deep-stack tests for Windows minizip/plutovg stack probes (red: svg-image x64+arm64, zip-read arm64)
- Shared-ext-from-union uses an enum as the String.From-unsupported argument (Int32 is now supported)
- Red - CType/TryCast/IsA reject generic and array targets at parse time
- Red - Str() on sized ints exits in codegen with no location; String.From/StdOut reject them
- Red - generic inference types Integer / Integer, And/Or and sized-int arithmetic wrong (also corrects E425 test line)
- Fix round: PCRE2 Windows vendor stamp + probe gate; split regex-deep-stack into package and builtin tests
- Red - redeclared base method without Overrides is not diagnosed (E425 pending)
- Red - regex-deep-stack crashes 0xC0000005 on Windows (PCRE2 built without stack probes)
- B3 fix round - Introspection.GetType(Variant), BOM-free/unit-safe/bounds-checked StringValue(enc), read-only Encodings, test+sample coverage; reseal Xojo
- XojoCrypto (Hash/MD5/SHA1/SHA2/HMAC/PBKDF2/GenerateRandomBytes), MemoryBlock EncodeHex/EncodeBase64, sample; reseal Xojo
- Red tests for XojoCrypto (hash, HMAC, PBKDF2, random, MemoryBlock Encode*)
- Add LEGACY MD5/SHA1 to HashAlgorithms (hash + HMAC), rebuilt all 6 targets, resealed
- Red tests for MD5/SHA1 hash + HMAC (RFC 2202)
- Encodings sample, Pair/encodings/introspection docs, gap-decision rows
- TextEncoding/Encodings, String.ConvertEncoding/DefineEncoding, MemoryBlock encoding StringValue, name-only Introspection; reseal
- Red tests for Encodings/TextEncoding, Introspection, Pair of Variant
- RegEx fix round - snap mid-char offsets, clamp SearchStartPosition, document import leak and regex requirement
- Bug report: object TypeName/Hash on Nil fixed, move to urgent/done
- Variant KindName/ToString Nil-object guard, BooleanValue pin test, docs, reseal
- Builtin TypeName()/Hash() use codegenCheckedReceiver so Nil raises NilObjectException
- Object-typename-hash-nil (red) — TypeName()/Hash() on Nil must raise NilObjectException
- Xojo-regex sample (4-test), examples copy, docs, gaps update, STR-11 done
- XojoRegEx/XojoRegExMatch/XojoRegExOptions/XojoRegExException over PCRE2
- Xojo-regex (red) — XojoRegEx/XojoRegExMatch/XojoRegExOptions/XojoRegExException
- Random follow-ups: refresh stale unseeded/rand() comments, 4-test pattern for random-seed sample, document RandomizeSeed no-op reason; reseal Xojo package
- Variant.KindName names the concrete class for object payloads; refresh stale menu-reuse/TabView/TypeName comments and docs
- Drop redundant LCase/case-insensitive workarounds now that Buoy string builtins ignore case; docs
- Rename Semaphore.GiveBack to Release (compiler bug fixed); docs, tests, resealed package
- Pin Xojo shim case-insensitive helper behavior before cleanup (green)
- Docs+shim: Random seeding docs, Random.Seed sample, XojoRandom.Seed forwards to Random.Seed; move 3 reports to done/
- Failing tests for Random range/bounds/seed and exact Integer / (red)
- Fixes for pair
- Red - ByRef String delegates allowed Buoy-to-Buoy, E1509 only at the C boundary (user ruling)
- Red - menu reuse throws InvalidArgumentException, detached TabView teardown, macOS uncaught NSException aborts
- Red - bare For with no existing variable must be E812 (spec 8.4, user ruling)
- Red - For round 2 (counter mutation near Int64 max, implicit counter scope, E801 message, counter hover)
- Red - Selector Boolean arguments travel as 1-byte BOOL
- Red - ByRef String rejected in Export and Delegate signatures (E1509)
- Red - For review follow-ups (narrow start, Step 0, Int64 max, counter scope)
- Test/docs: FFI Structure review follow-ups (R1-R3)
- Red - Int8/Int16/UInt8/UInt16 FFI arguments and results are extended
- Red - Export String parameter called through the exported symbol
- Red - Selector sends with by-value Structure arguments and results
- Red - Select Case numeric widening, Currency, unsigned UInt64 and Range-bound diagnostics
- Red - typed For loops (Double/Single/sized/unsigned/Currency counters, Sema rejections)
- Red - UInt64 mixed with a signed variable must keep signed \ and Mod
- Red - user methods named Release/Retain/Hash/TypeName replaced by the Object builtin
- Red - integer division by zero unchecked (SIGFPE on x86_64); Double operands to IntDiv/And/Or/Xor accepted by Sema
- Red - > 16-byte by-value Structures and register exhaustion cross the C ABI wrongly
- Red - small by-value Structures cross the C ABI wrongly (params, Delegates, callbacks, Export)
- Test+docs: Delegate C-ABI review follow-ups (I1, I2, I3, I5, I6)
- Red - a computed (Get/Set) property passed ByRef aborts codegen
- Red - a borrowed argument is freed by a later ByRef argument in the same call
- Red - Delegate calls to/from C use Buoy's Structure lowering, not the C ABI
- Red - overwriting a Shared Optional/Result/Structure property leaks
- Red - New with a ByRef constructor parameter
- Red - Lambda/AddressOf inside a generic body is dropped
- Red - Closure parameter reassignment frees the caller's closure env
- Update branch tests for main's case-insensitive String search
- Merge Github/main (string comparison and search ignore case by default, #573) into feat/xojo-shim
- Red - Thread.Join(ms) with a negative timeout blocks like an infinite Join()
- Red - Xojo shim global CDbl (undefined function)
- Red - Thread.Join timing and self-join edges (Windows negative remaining timeout, self-join deadlock vs owner Join, POSIX nap-count drift)
- Red - fresh Optional/Result/Structure temporaries (call arguments, HasValue/IsOk receivers) leak
- Red - Closure/Delegate calls with Structure and ByRef parameters
- Red - Lambda parameter reassignment releases the caller's reference
- Red - self-join marks thread consumed, timed loser re-waits full timeout, Windows Detach during Join, IsRunning during Join
- Red - Array Of Optional ownership, setter-argument forwarding (B3c r1), ByRef aggregate assignment, Structure parameter field stores, Closure property initializer
- Red - concurrent Join/Detach on one Thread, Join on a borrowed Current() box, Windows Id() after Detach
- Red - Lambda Using (o) of an Optional/Result local does not retain the payload
- Red - Optional/Result/Structure holders (class property, Some(<Structure>), nested Structure, Stack.Pop/Queue.Dequeue) don't own what they store
- Red - Structure class field not retained by Dim copy / assign / Return / array push / Lambda capture (double release)
- Red - Thread.Current()/Main() release detaches the real thread; Join/Detach leave a stale handle (Join early/hang, double detach of recycled handle)
- Red - Dim/Return of Await <Optional/Result> leaks the payload (+1 per evaluation)
- Red - Optional/Structure ownership: mixed If getters/returns/Dims and builtin element loads (use-after-free / double release)
- Share per-argument ByRef/byval-indirect lowering across call paths (emitIndirectArg/emitCallArg); IR identical on 9 tests x 3 targets
- Red - by-value large-Structure extension receiver (IR verify failure) and lifted ByRef receivers on sized ints/Currency/Single/Assigns
- Share the array element store helpers (consumeElemValue, storeArcElemSwap); fix RemoveValue/Lambda-literal wording in closure docs and test
- Red - Structure Closure fields do not own their env (NilObjectException / use-after-free)
- Red - Optional/Result local Dim-copy, assign, Return and inline .Value are ARC-unbalanced
- Red - Lambda Using (x) does not retain a captured Array or Closure (segfault / NilObjectException)
- Red - Array.Reversed on Array Of String does not retain the elements (use-after-free)
- Red - extension method-call form ignores ByRef params (IR verify failure, receiver/String/class segfault or bus error)
- Red - closures stored in arrays are not retained (Append/Insert/index-assign/literal/property, release coverage)
- B2 minors - unconditional statement-scope release for Select/With/SyncLock, drop no-op flushTemps, test Return/Exit/Continue out of SyncLock-on-temp and body dropping the subject's source
- B1 minors - accurate array-store comments/naming, drop dead Integer->Double arms, element-store type assert, zip Deflate regression assertion
- Red - Select Case / With / SyncLock subject temporaries are released before the statement uses them
- Red - array element stores of a different numeric type write raw bits at the value's width/stride
- Red - Integer-backed Enum to Double/Int32/Single stores raw bits; Some(enum) aborts IR verifier
- Red - Windows lld ICF folds identical-bodied functions (AddressOf A Is AddressOf B True; CancelCallLater cancels twin)
- LANG-15 red - Select Case on Delegate/CString/class selector aborts codegen (fcmp ptr); Case Is </Range on non-ordered selectors has no Sema diagnostic
- LANG-15 red - delegate/CString equality aborts codegen (fcmp ptr); ordering of non-ordered operands has no Sema diagnostic
- LANG-13 red - Super in Shared method / non-capturing Lambda must be rejected in Sema (currently passes --check and asserts in Codegen)
- LANG-13 red - Super.<member> = value tests (fail with E418 on current parser)
- Merge Github/main into feat/xojo-shim
- LANG-12 red — FolderItem.Path/Extension, IPCSocket.Path
- LANG-12 red — formatter on keyword-named fields and enum members
- LANG-12 red — Structure keyword field needs As; LSP completion test checks parse errors
- LANG-12 red tests — keyword member names, guards, LSP
- LANG-10 red - Shared members named like Thread built-ins must be rejected
- LANG-10 red - Pause then Stop must not deadlock CheckPaused
- LANG-10 red - Xojo threading on Buoy's own Thread
- LANG-10 red test — Run sees its own published thread handle
- LANG-10 receiver-shape test + codegen no-unknown-method checks
- LANG-10 red tests — Thread subclass runtime on all lanes
- LANG-10 red tests — Thread subclass declaration, negatives, LSP
- LANG-9 final-review red — round Single text, ByRef Single Declare, Double vs Single/Integer overloads, array literal inference, @Serializable Single message
- LANG-9 red — Xojo shim Single members, MemoryBlock Single/Double/CurrencyValue, BinaryStream Single
- LANG-9 red — Single members, extensions, Shared, BinaryStream, LSP
- LANG-9 red — Windows arm64 variadic HFA params, Single-struct Export ABI, variadic diagnostic
- LANG-9 red — Single across the C ABI (Declare, float Structures, variadic)
- LANG-9 red — Single text, hashing, sorting and String.Format
- LANG-9 red — user operators returning Single, nested IEEE division, float IR
- LANG-9 red — Single arithmetic, comparison, literal adaptation, Select Case, folding
- LANG-9 red — Integer-backed Enum to Single at every store site
- LANG-9 red tests — Single declarations and conversions
- LANG-8 final-review red tests — ByRef value receivers, negative ToHex padding
- LANG-8 red tests — Xojo shim NUM-3/NUM-4/THR-13 mappings
- LANG-8 red tests — LSP completion/hover for built-in receivers and Shared targets
- LANG-8 red tests — Shared extensions on Currency and sized ints
- LANG-8 red tests — thread classes and Currency built-ins under rule B
- LANG-8 red tests — Currency/sized-int receivers and Integer fallback
- LANG-7 re-review red tests — dead instances naming late generic classes
- LANG-7 final-review red tests (I-1..I-4, M-1, M-2)
- LANG-7 fix round 1 — generic interface receiver pin; generic Assigns on value receiver rejected (red)
- LANG-7 generic class receivers, Assigns, ranking, visibility (red)
- LANG-7 fix round 1 — receiver-fixed T accepts assignable args; one diag per generic body (red)
- LANG-7 generic-receiver extensions — Array receivers (red)
- Docs/test/sample: RowSet For Each resume semantics, HasMoreRows wording, README, sample
- RowSet For Each (red)
- Reserved Iterable/Iterator names, duplicate generic interface, LSP walker descent (LANG-6 final fix, red)
- Pin Stack order, empty collections, class-valued Map, Entries order (LANG-6 task 2 fix)
- Register for-each-collections (LANG-6 task 2) (red)
- For Each over Stack/Queue/Set/Map (LANG-6 task 2) (red)
- Iterable with Array / Int32 / nested-generic type args crashes on itable lookup (LANG-6 task 1 fix 1) (red)
- For Each over Iterable / Iterator (LANG-6 task 1) (red)
- Incoming CType on generic class loses Shared after instantiation (red)
- LANG-5 final-review guards — outgoing self-recursion, incoming visibility, Assigns ByRef (red)
- Interface method call with a converted argument (LANG-5 task 3 fix 1, red)
- Converting overload tier — user conversions at call arguments (LANG-5 task 3, red)
- No implicit conversion into C inside C's own incoming operator (LANG-5 task 2 fix 1, red)
- User conversions at every assignment-like site, outgoing first, trace (LANG-5 task 2, red)
- Interface source implemented by a subclass of the target keeps the downcast (LANG-5 task 1 fix 1b, red)
- Incoming CType from unrelated class/interface sources, Shared outgoing and Optional-param errors, E909/Assignable/Nil pins (LANG-5 task 1 fix 1, red)
- Incoming Operator CType declaration and explicit CType (LANG-5 task 1, red)
- Always filter inaccessible real overloads (with or without extension), Super pin, red
- Shared Assigns case for inaccessible real vs extension, red
- Inaccessible real members don't compete with extensions, red (LANG-4 follow-up)
- LANG-4 final-review fixes, red (Xojo IndexOf case, UDP port parse, real-miss visibility hint, iface named arg, builtin param types, Super pin)
- Xojo shim LANG-4 shapes (Read(count, enc), IndexOf order, Write/Read datagram, Connect(), DrawLine/Rotate) (LANG-4 task 6, red)
- Never-callable extension warning, overload-aware completion (LANG-4 task 5, red)
- Shared extension hiding per signature, String.From union diagnostic, paren-less pin (LANG-4 task 4 fix 1, red)
- Shared extensions overload real Shared methods and builtins (LANG-4 task 4, red)
- Builtin String/Array methods overload with same-named extensions (LANG-4 task 3, red)
- Extension overloads beside real members, rule B (LANG-4 task 2, red)
- Pin selective-import and Public Import chain extension visibility (LANG-4 task 1)
- Extension member-call visibility follows imports (LANG-4 task 1, red)
- LANG-3 final-review regressions (red): setter write-site navigation, ByRef Assigns receiver, With compound assign, plain-Sub write message, setter completion detail
- Property/Assigns collision and Private instance-setter negatives (LANG-3 task 5, red)
- Shared setter negatives; ordinary calls to setter-only Shared extensions must be rejected (LANG-3 task 4 fix, red)
- T.Foo = v / T.Foo(k) = v Shared extension setters (LANG-3 task 4, red)
- X.Foo = v extension setters and paren-less Assigns Subs (LANG-3 task 2, red)


---

# v0.70.0

## New Features
- String As.../From... conversions via Bytes; remove ChangeEncoding/SetEncoding
- Unicode simple case mapping for String UCase/LCase
- Make String Len/Left/Right/Mid/Substring/IndexOf/InStr/Asc/Chr/Chars/pads character-aware
- Add String ...Bytes variants; make stdlib byte sites explicit
- Optional Declare and System.IsLibraryAvailable
- Stage Optional Declare libraries beside output, LSP outline, app-folder-first loader

## Bug Fixes
- Make JSON parse/escape and Database named-parameter scans linear
- ServerSocket IPC mode accepts a full socket path / pipe name
- IPCSocket.Connect accepts a full socket path / pipe name
- Harden character primitives (pad size overflow, strict UTF-8 widths)
- Stage Linux regex/TLS archives under driver names, scrub builder path
- Stage linux regex/tls archives under driver names, scrub builder path
- Windows regex archive staging, builder path leak, release version in win/linux builds
- Pass release version to cmake in windows/linux workflows
- Stage windows regex archives under driver names, never leak builder path
- Pass resolved release commit to linux/windows build workflows
- Rebase onto branch tip before pushing release version commit
- Push release version commit explicitly from detached HEAD
- Resolve short commit SHA before checkout in release-mac workflow
- Clean workspace before checkout in release-mac workflow
- Treat bug report content and attachments as untrusted in triage/fix skills
- Treat bug report content and attachments as untrusted data in triage/fix skills

## Changes
- TextField.Multiline: never apply to Password fields
- TextControl Bold/Italic/Underline/TextColor/Multiline and Graphics text style
- UTF-8 invariant, character-aware ops, explicit encoding conversion
- Add failing JSON parse scan-performance test (red)
- Add failing String conversion (As.../From...) test (red); register string-case sample
- Add failing Unicode UCase/LCase test (red)
- Ignore the playwright-mcp folder
- Add failing codepoint-semantics String test (red)
- Add failing String ...Bytes variant test (red)
- Merge remote-tracking branch 'Github/main' into fix/windows-regex-archive-staging
- Add hash specifier to windows build
- Test+fix: Optional Declare ByRef/struct coverage, Windows loader hardening


---

# v0.69.0

## New Features
- Declare accepts integer-backed Enum params/results (Enum X As Int32)
- Declare accepts integer-backed Enum params/results; Enum X As Int32 sized backing
- Window/View blocks accept 'Inherits <Class>'

## Bug Fixes
- MSVC runtime build warnings + standalone Windows/Linux release publish
- Publish standalone Windows/Linux releases via GitHub App to buoy-releases
- Silence MSVC D9002/C4273 warnings in runtime build
- Use llvm::*Overflow so Windows (MSVC) builds
- Use llvm::*Overflow instead of __builtin_*_overflow so MSVC builds


---

# v0.68.0

## New Features
- Layout editor treats panels with sections as opaque
- Outline flags panels with sections; Tab/Page completion
- Lower Tab/Page sections to AddTab/AddPage
- Parse Tab/Page sections inside Control bodies
- Layout round-trip modules drop inline handler spans; Handle in a layout is refused
- Layout editor no longer carries inline handlers
- Reject inline Handle in Window/View layouts; drop handler extents from the outline
- With-handler polish — hover/definition on control name, outline, modifier and empty-layout diagnostics
- LSP completion for With <control> handler blocks
- Validate and lower With <control> handler blocks
- Parse With <control> handler blocks in class bodies
- Derived class may reuse a base class's Private property name
- @Hidden attribute hides Perform* test hooks from autocomplete
- @Hidden attribute hides Public members (Perform* test hooks) from autocomplete

## Bug Fixes
- Tab = / Page = property lines are not section headers (peekSecond, not peek)
- String comparison and search ignore case by default
- Read-only layout editor shows the compiler's error; finish doc/sample migration off hook-name overrides
- Code-behind handlers for value-returning control events now run
- Attribute With-handler diagnostics to their file; reject With in generic classes
- Fold integer/Boolean operators and Const references in module/class Const initializers (buoy-releases#111)
- PagePanel/content-view pages double-scale under Windows HiDPI
- Decode non-ASCII \u escapes in Json.Parse; TryParse never throws (buoy-releases#112)
- Fold integer/Boolean operators and Const references in module- and class-scope Const initializers (buoy-releases#111)
- Stop PagePanel/content-view pages double-scaling under Windows HiDPI
- Decode non-ASCII \u escapes in Json.Parse; make Json.TryParse never throw (buoy-releases#112)
- String.Format heap overflow, OOB read, scratch-buffer leak, and 63-char truncation
- Size String.Format's output buffers from content, stop leaking/truncating
- Marshal AddressOf'd String-param callbacks for foreign (C) callers
- Reseal buoyscript package against ARC-enabled codegen
- Fix reference-counted String memory management
- Implement reference-counted String memory management (ARC)
- Sub Main(args) receives the real command line on Linux and Windows
- Closures returned from a function (or a closure call) are freed

## Changes
- Add true multidimensional arrays (Dim a(r, c), a(i, j), Dimensions, LastIndex(dim), ResizeTo)
- Add true multidimensional arrays: Dim a(r, c), a(i, j), Dimensions, LastIndex(dim), ResizeTo
- TabView/PagePanel accept children in layouts: Tab / Page sections
- Event handler refactor: With <control> blocks, value-returning fix, remove inline layout Handle
- Migrate inline-handler tests and sample to With / subclass Handle
- Make UIControl.mLayoutEngine/mLayoutHandle Internal
- Add an internal tooling category
- Moving some bugs around
- Pin down String ARC leak with a failing memory + characterization test
- Sub Main(args) must receive the real command line (failing on Linux/Windows)
- Closures returned from a function must be freed (failing)


---

# v0.67.0

## New Features
- UDP autodiscovery for fileservice-buoy + fsdiscover companion app
- Add NetworkInterface.BroadcastAddress
- Fileservice-buoy protocol parity with the Xojo fileservice, sandboxed paths, service install docs
- Bring fileservice-buoy to protocol parity with the Xojo fileservice
- Add << / >> bitwise shift operators
- MacOS application menu hook (Application.AppMenu) and About override (Application.AboutRequested)
- Add AppMenu/AboutRequested sample
- Add AppMenu/About ABI stubs for Windows and Linux
- Add Application.AppMenu and AboutRequested (macOS app menu hook)

## Bug Fixes
- Loop-scoped Dim/Const starts from Nil every iteration
- GroupBox children no longer inset twice on Linux
- Layout editor GroupBox content inset now matches the native runtime
- VSCode Debug honors launch.json cwd/args/env; Run uses the workspace folder
- Log service output under the service's own name, not "BuoyService"
- Windows crash (0xC0000005) tearing down a Window whose MenuBar holds a Menu
- Hide "Buoy: Open Layout Editor" from the Command Palette
- Windows outputs always end in .exe/.dll; import .lib named after the DLL
- Window programs fail to link on Windows/Linux (missing bui_ui_window_set_on_closing)
- Layout editor view shifts 1px on select/deselect
- Layout editor canvas/controls shift 1px on select/deselect
- Window native property setters use-after-close on macOS; add Window.Closing event
- Guard native Window property setters against use-after-close on macOS; add Window.Closing event
- Address final whole-branch review findings in AppMenu
- Address use-after-free and shortcut-collision review findings in AppMenu

## Changes
- Loop-scoped Dim/Const must start from Nil every iteration (failing)
- GroupBox children must be inset exactly once on every platform (failing on Linux)
- GroupBox editor/solver content inset must match native runtime (failing)
- Merge remote-tracking branch 'Github/main' into fix/vscode-debug-cwd-launch-setting-never-honored
- Service log identity must follow the service's own name (red)
- Debug/run launches must honor cwd (and launch.json args/env) (red)
- Run menubar_test on every platform via UNIT_TESTS
- Window + MenuBar with a Menu must not crash on Windows (red: 0xC0000005 on x64/arm64)
- Buoy.openLayoutEditor must be hidden from the Command Palette (red)
- --library import .lib must be named after the DLL (red: hidden .<stem>.lib)
- Windows outputs must end in .exe/.dll (red: a.out default, no extension appended)
- Add runtime_exports_in_sync check (red: bui_ui_window_set_on_closing missing)
- Nest TextAlignment enum on TextControl
- Add failing Application.AppMenu/AboutRequested test


---

# v0.66.0

## New Features
- Add Menu.Caption so MenuNeedsUpdate can identify the opening menu
- Layout editor duplicate (Cmd-D, Option-drag) and copy/cut/paste

## Bug Fixes
- Resolve vendored GTest_DIR before frontend/ is configured
- Bump hono to 4.13.8 (alerts #58, #59, #60)
- Bump js-yaml to 4.3.2 (alert #61)
- Bump js-yaml to 4.3.2 (alert #61, GHSA-2883-xcg3-v3hh)
- Lower Frame and Lock* in Window blocks to layout constraints

## Changes
- Failing test and sample for Frame/Lock* layout in Window blocks


---

# v0.65.0

## New Features
- Constraint overlay follows the dragged control live

## Bug Fixes
- Layout editor orphaned constraints, GroupBox caption offset, SafeArea inset


---

# v0.64.0

## New Features
- Nested-control Constraints support (View/GroupBox/RadioGroup/Splitter)
- Replace flat-solve editor preview with real per-container recursive solve
- Sema support for nested-control Constraints (parent+sibling scope, SafeArea rewrite, Splitter pane routing)
- Add Splitter.AddSubview, one pane per direct nested child
- Build RadioGroup ContentArea/SafeArea and Constraints support from scratch
- Wire GroupBox.ContentArea/SafeArea via inherited View helper
- Add View.ContentArea/SafeArea for nested-control constraints
- Attach a palette-dropped control directly into a container
- Splice a control's source block between parents on reparent
- Hit-test and reparent existing controls during drag
- Render nested layout-editor controls inside their parent's box
- Add pure containment/hit-test geometry for control attachment
- Report parentName for nested layout-editor controls
- Bundle buoy-debugstub + lldb-server for all six targets
- Attach to an already-running remote buoy-debugstub via target

## Bug Fixes
- Scope lldb-server lookup in package.sh to the arch being staged
- Remove duplicate nested-constraint gtest definition and fix parent-origin double-subtraction
- Stop double-subtracting parent origin from nested constraint solves
- Remove duplicate nested-constraint gtest definition breaking package.sh
- Layout editor mispositions and blocks selecting nested constraint-solved controls
- Close GroupBox's exposure to the WireContentAndSafeArea thin-container gap
- LSP editor preview applies the per-container SafeArea gap inset
- Accurate diagnostic for a top-level LHS referencing a nested RHS
- Cascade Layout() through every nesting level, not just the top ancestor
- Make View.AddSubview(ctrl As UIControl) Internal, not Public
- Gate View/RadioGroup WireContentAndSafeArea behind lazy-getter touch
- Decouple nested-control-constraints test from Window.SafeArea
- Move View.WireContentAndSafeArea() before layout solve
- Complete #If/#ElseIf autocomplete for Target predicates and #Define symbols
- Re-indent a control's source block on reparent
- Harden writeReorderControlsEdit's permutation guard against duplicates
- Give every nested Control block a real, grabbable Frame (I5)
- Correct nesting-unaware layout-editor consumers (C1/I2/I3/I4/M6/M9)
- Clear drop-target highlight unconditionally and dedupe controlMode derivation
- Route ordinary Frame-governed drags through attach/detach, not commitGesture's dead frame fallback
- Restore pointer-events/positioning for nested GroupBox/TabView controls
- Set parentName in controlOrdering.test.ts makeControl helper

## Changes
- Regression coverage for the final fix wave (Fix 1, 2/3, 6)
- Confirm StackView/TabView/PagePanel non-goal stays a clean compile error
- Complete #If/#ElseIf autocomplete for Target predicates and #Define symbols
- Layout editor: drag attach/detach + palette-drop into container (3/3)
- Layout editor: render nested controls + hit-test geometry (2/3)
- Layout editor: plumb parentName for nested controls (1/3)
- Fix macOS debug-stub to ship as a universal (arm64+x86_64) binary
- Remove File namespace; fold text I/O into FileSystemItem
- Attach to a remote buoy-debugstub, and bundle debug stubs for release
- Remove File namespace, fold ReadAllText/WriteAllText/AppendAllText into FileSystemItem


---

# v0.63.1

## Bug Fixes
- Windows dark mode for menu bar, popup menus, and RadioButton captions
- Skip redundant native measure pass on live resize ticks
- Document cross-referenced members missing from their owning class's docs

## Changes
- Windows dark mode: menu bar, popup menus, and RadioButton captions


---

# v0.63.0

## New Features
- Set minimum supported Windows version to 10.0.19045 in installer
- Apply dark chrome to ProgressBar, Slider, Stepper, DateTimePicker
- Native dark chrome for Button on Windows via uxtheme
- Draw a themed border around TabView's pane on Windows
- Theme-aware Toolbar item text color on Windows
- Theme-aware colors for ListBox/Splitter/GroupBox/Canvas/TabView/HtmlView on Windows
- Theme-aware Label/TextField/TextArea/ComboBox colors on Windows
- Dark title bar on Windows, live-updating on OS theme change
- Add shared Win32 dark/light theme module (unused yet)
- Show and edit GroupBox Caption in the Layout Editor

## Bug Fixes
- Revert DateTimePicker dark-mode diagnostic to simpler unconditional CFD chrome
- Windows quits on any window close, not just the last
- Only quit on Windows when the last window closes
- Revert TabView and TextArea dark-theme experiments
- Revert Button dark-mode chrome to DarkMode_Explorer
- Give toolbar SearchField creation-time dark chrome; keep ProgressBar visual-style opt-out dark-mode-only
- Theme-aware chrome for RadioButton/TextField/DateTimePicker; ProgressBar via explicit colors
- Re-theme TextArea scrollbar chrome on live dark/light toggle
- Keep Windows DisclosureTriangle's glyph at native size
- Use DarkMode_CFD theme class for ComboBox chrome
- Dark-theme TextArea's native scrollbar on Windows
- Re-theme already-created Windows controls on live OS theme toggle
- Apply dark chrome to Checkbox/ComboBox/TabView, mute DisclosureTriangle glyph
- Recolor Toolbar icons in dark mode; fix README Button wording
- Correct uxtheme ordinal-135 dispatch, app-mode init order, and chrome-apply call site
- Dark-mode toolbar legibility + WM_SYSCOLORCHANGE + comment fixes
- Fill TabView pane area with theme brush in dark mode
- Convert tabview page frame from physical to logical DPI units
- Give windows-dark-mode's TabView page a control so it realizes
- Make GroupBox's default BorderColor theme-aware
- Render GroupBox's Layout Editor skin like the real widget

## Changes
- Full dark-mode theming (title bar + controls)
- Opt DateTimePicker's date field out of visual styles in dark mode
- Sync user's expanded windows-dark-mode sample with indeterminate ProgressBar
- Try DarkMode_CFD for TabView's tab-strip theming
- Add a second declarative-syntax window to windows-dark-mode
- Add cross-platform dark-mode visual sample


---

# v0.62.1

## Bug Fixes
- Honor an absolute sourcePath in the Copy Resources build step
- Resolve GroupBox/RadioButton declarative Control block failures
- Actually invoke aws to confirm it works, not just command -v
- List raw object keys instead of delimited CommonPrefixes in s3-artifact-download
- Filter aws-cli's literal None text output in s3-artifact-download
- Filter aws-cli's literal "None" text output in s3-artifact-download
- Stop silencing list-objects-v2 stderr in s3-artifact-download
- Check aws.cmd not just aws.exe on Windows, --update the Linux installer
- Bypass pip broken extension-less aws shebang script on Windows
- Fix pip Scripts-dir path on Windows, add pip-less fallback for Linux
- Install AWS CLI on demand in s3-artifact actions


---

# v0.62.0

## New Features
- Insert Code boilerplate command
- Return FileSystemItem from OpenFileDialog/SaveFileDialog/SelectFolderDialog
- Register buoy.insertCode command and context menu entry
- Add Event Handler / Override Method snippet builders
- Add static boilerplate snippet builders for buoy.insertCode
- Wire buoy/handleEventsAt and buoy/overridableMethodsAt
- Add Workspace::insertableHandleEventsAt
- Add Workspace::overridableMethodCompletionsAt

## Bug Fixes
- Replace stale-version RELEASE_NOTES.md even with hand edits
- Patch vendored LLVM for Xcode 27's arm64e.x1 TAPI stubs
- Autocomplete class-scoped nested enums (e.g. Checkbox.CheckState)
- Offer window-level Handle events for cursor in Window block body
- Exclude synthesized event slots and Private methods from Override picker

## Changes
- Return FileSystemItem from file dialogs


---

# v0.61.0

## New Features
- Right-click keyword help, resolving local docs or falling back to the website
- Add FileSystemItem.IsVisible
- Add shared BuiltinMethodInfo table for String/Array builtin methods

## Bug Fixes
- Dispatch MenuSelected for items added after MenuBar.AddMenu
- Dispatch MenuSelected for items added after MenuBar.AddMenu; fix macOS Enabled ignored by native menu
- Include buoy-dap/buoy-debugstub in the single-arch darwin-universal fallback
- Correct breakpoint source-path casing before resolving against DWARF
- Correct import path casing so DWARF file names match the filesystem
- Correct import path casing so DWARF file names match the real filesystem
- Bump qs to 6.16.0 in editors/vscode (alerts #51, #55)
- Bump qs to 6.16.0 in editors/mcp (alerts #50, #52)
- Bump fast-uri to 3.1.6 in editors/vscode (alerts #46, #48, #56, #57)
- Bump fast-uri to 3.1.6 in editors/mcp (alerts #47, #49, #53, #54)
- Windows Canvas text centering/HiDPI scaling + ~42% oversized default control font
- Windows Canvas text no longer mis-centered/oversized on HiDPI, and every control's default font no longer 42% too large
- Catch remaining kiwi edit-variable exceptions in ConstraintSolver
- Catch kiwi::DuplicateConstraint and avoid CRT stdio in ConstraintSolver
- Stop scrub-dev-paths.py from silently disabling Windows/Linux cross-link archives
- Stage Linux cross-arch regex/PCRE2 archives in package.sh
- Strip extended attributes from app bundle before codesigning
- Stage Windows cross-arch regex/PCRE2 archives for package.sh
- Stage Windows cross-arch regex/PCRE2 archives in package.sh
- Avoid literal {app} inside a brace-delimited Pascal comment
- Fall back to a writable directory when Run/Debug/Build can't write into the project
- Remove stale files from upgraded component directories
- Stage x86_64 cross-arch regex/TLS archives for universal-darwin
- Stage x86_64 cross-arch regex/TLS archives for universal-darwin builds
- Name the offending control in kiwi unsatisfiable-constraint warnings
- Sign step errors clearly when its target does not exist
- Sign step errors clearly when its target doesn't exist
- Complete String and Array builtin methods for VSCode autocomplete
- Implement Array.IsEmpty end-to-end; derive Sema whitelist from shared table

## Changes
- Add regression test for client-supplied breakpoint path casing
- Move SpecialFolderDomains enum into System.FolderDomains
- Right-click keyword help (local docs or website fallback)
- :fix: updating the distributed learning docs with fixed versions
- :fix: updating learning references based on latest builds
- Fix String/Array builtin methods missing from VSCode autocomplete


---

# v0.61.0

## New Features
- Right-click keyword help, resolving local docs or falling back to the website
- Add FileSystemItem.IsVisible
- Add shared BuiltinMethodInfo table for String/Array builtin methods

## Bug Fixes
- Dispatch MenuSelected for items added after MenuBar.AddMenu
- Dispatch MenuSelected for items added after MenuBar.AddMenu; fix macOS Enabled ignored by native menu
- Include buoy-dap/buoy-debugstub in the single-arch darwin-universal fallback
- Correct breakpoint source-path casing before resolving against DWARF
- Correct import path casing so DWARF file names match the filesystem
- Correct import path casing so DWARF file names match the real filesystem
- Bump qs to 6.16.0 in editors/vscode (alerts #51, #55)
- Bump qs to 6.16.0 in editors/mcp (alerts #50, #52)
- Bump fast-uri to 3.1.6 in editors/vscode (alerts #46, #48, #56, #57)
- Bump fast-uri to 3.1.6 in editors/mcp (alerts #47, #49, #53, #54)
- Windows Canvas text centering/HiDPI scaling + ~42% oversized default control font
- Windows Canvas text no longer mis-centered/oversized on HiDPI, and every control's default font no longer 42% too large
- Catch remaining kiwi edit-variable exceptions in ConstraintSolver
- Catch kiwi::DuplicateConstraint and avoid CRT stdio in ConstraintSolver
- Stop scrub-dev-paths.py from silently disabling Windows/Linux cross-link archives
- Stage Linux cross-arch regex/PCRE2 archives in package.sh
- Strip extended attributes from app bundle before codesigning
- Stage Windows cross-arch regex/PCRE2 archives for package.sh
- Stage Windows cross-arch regex/PCRE2 archives in package.sh
- Avoid literal {app} inside a brace-delimited Pascal comment
- Fall back to a writable directory when Run/Debug/Build can't write into the project
- Remove stale files from upgraded component directories
- Stage x86_64 cross-arch regex/TLS archives for universal-darwin
- Stage x86_64 cross-arch regex/TLS archives for universal-darwin builds
- Name the offending control in kiwi unsatisfiable-constraint warnings
- Sign step errors clearly when its target does not exist
- Sign step errors clearly when its target doesn't exist
- Complete String and Array builtin methods for VSCode autocomplete
- Implement Array.IsEmpty end-to-end; derive Sema whitelist from shared table

## Changes
- Add regression test for client-supplied breakpoint path casing
- Move SpecialFolderDomains enum into System.FolderDomains
- Right-click keyword help (local docs or website fallback)
- :fix: updating the distributed learning docs with fixed versions
- :fix: updating learning references based on latest builds
- Fix String/Array builtin methods missing from VSCode autocomplete


---

# v0.60.0

## New Features
- Add GroupBox - titled, bordered container control
- Add GroupBox — titled, bordered container control

## Bug Fixes
- Prune nested git checkouts from app_resources.json manifest discovery
- Windows Picture no-SVG fallback build now links
- Add fmod to Apple/Windows curated link stubs
- Canvas Paint drawing now clips to the canvas's own bounds
- Windows native controls no longer ignore per-monitor DPI for text
- BaselineAnchor-only controls no longer render as unresolved


---

# v0.59.0

## New Features
- Add a control context menu for stacking order
- Add Inspector editing for the highest-impact property on each control
- Render visual control skins in place of wireframe boxes
- Add per-control-type visual skin spec builder
- Report declared control properties in layout outline

## Bug Fixes
- Dragging a constrained control no longer changes its target
- Deleting a control no longer leaves dangling Constraint references
- Prevent circular Constraint dependencies from drag, and keep a control's lines grouped together
- Dependent controls follow a drag, and anchor-drag no longer duplicates existing lines
- View wireframe rendering, Constraints list visibility, and Frame/Constraints conflict prevention
- Right-click on a control no longer starts a drag
- Address 4 issues found in Task 4 manual verification
- Address whole-branch review findings for layout editor skins
- Use JSON array of pairs for properties to preserve order
- Preserve property declaration order and add documentation

## Changes
- Layout editor: visual control rendering, property editing, stacking order


---

# v0.58.0

## New Features
- Redesign layout editor constraint visualizer
- Draft editable release notes, gate release: commits on them
- Stamp a build-number 4th component into the macOS installer version
- Constraints block completion for control names and anchor properties
- Autocomplete control names and anchor properties in Constraints blocks
- Allow Delegate declarations nested inside a Class
- Add System.IsDarkMode cross-platform dark-mode detection

## Bug Fixes
- Stop Interface Sub/Function signatures from growing indent
- Dedupe changelog/release-notes lines from squash-merge suffix
- Canvas no longer swallows Tab forever once focused (macOS + Linux)
- Build macOS bundles and Windows/Linux exes in temp dir, atomic move into place
- Build macOS bundles and Windows/Linux exes in a temp dir, then atomically move into place
- Don't suppress user Quit/Hide menu shortcuts on macOS
- Route Build/Run/Debug commands through the Build Graph
- Detect mid-line Lambda/Block literals in document formatter
- Indent Lambda/Block bodies and outdent End lines
- Indent Lambda/Block bodies and outdent their End lines
- Stop UIControl Lock* properties crashing on a second same-axis lock
- Clamp window resize to Auto Layout constraints
- Control's own Handle override no longer shadowed by declarative Window control block
- Rebuild an ancestor whose cached 'success' status no longer matches disk

## Changes
- Revert "chore: release v0.58.0"


---

# v0.58.0

## New Features
- Redesign layout editor constraint visualizer
- Draft editable release notes, gate release: commits on them
- Stamp a build-number 4th component into the macOS installer version
- Constraints block completion for control names and anchor properties
- Autocomplete control names and anchor properties in Constraints blocks
- Allow Delegate declarations nested inside a Class
- Add System.IsDarkMode cross-platform dark-mode detection

## Bug Fixes
- Stop Interface Sub/Function signatures from growing indent
- Dedupe changelog/release-notes lines from squash-merge suffix
- Canvas no longer swallows Tab forever once focused (macOS + Linux)
- Build macOS bundles and Windows/Linux exes in temp dir, atomic move into place
- Build macOS bundles and Windows/Linux exes in a temp dir, then atomically move into place
- Don't suppress user Quit/Hide menu shortcuts on macOS
- Route Build/Run/Debug commands through the Build Graph
- Detect mid-line Lambda/Block literals in document formatter
- Indent Lambda/Block bodies and outdent End lines
- Indent Lambda/Block bodies and outdent their End lines
- Stop UIControl Lock* properties crashing on a second same-axis lock
- Clamp window resize to Auto Layout constraints
- Control's own Handle override no longer shadowed by declarative Window control block
- Rebuild an ancestor whose cached 'success' status no longer matches disk


---

# v0.58.0

## New Features
- Redesign layout editor constraint visualizer
- Draft editable release notes, gate release: commits on them
- Stamp a build-number 4th component into the macOS installer version
- Constraints block completion for control names and anchor properties
- Autocomplete control names and anchor properties in Constraints blocks
- Allow Delegate declarations nested inside a Class
- Add System.IsDarkMode cross-platform dark-mode detection

## Bug Fixes
- Stop Interface Sub/Function signatures from growing indent
- Dedupe changelog/release-notes lines from squash-merge suffix
- Canvas no longer swallows Tab forever once focused (macOS + Linux)
- Build macOS bundles and Windows/Linux exes in temp dir, atomic move into place
- Build macOS bundles and Windows/Linux exes in a temp dir, then atomically move into place
- Don't suppress user Quit/Hide menu shortcuts on macOS
- Route Build/Run/Debug commands through the Build Graph
- Detect mid-line Lambda/Block literals in document formatter
- Indent Lambda/Block bodies and outdent End lines
- Indent Lambda/Block bodies and outdent their End lines
- Stop UIControl Lock* properties crashing on a second same-axis lock
- Clamp window resize to Auto Layout constraints
- Control's own Handle override no longer shadowed by declarative Window control block
- Rebuild an ancestor whose cached 'success' status no longer matches disk


---

# v0.57.0

## New Features
- Add Help button for layout editor hotkeys (#436)
- Add Help button for layout editor hotkeys
- Add Project Type build setting (Automatic/Console/Desktop) (#432)
- Add Project Type build setting (Automatic/Console/Desktop)
- Strip spaces from hex-formatted Developer Identity on blur
- Add Windows Tab-key handling (IsDialogMessage) and TabPressed suppression
- Add TabPressed event with macOS/Linux native suppression
- Focus position 0 on Window.Show/ShowModally
- Two-tier focus relocation on Focusable/Visible/Enabled/page-switch
- TabView/PagePanel/Splitter effective-focusability filtering - WIP
- Synthesize native focus chain from Window.mTabOrder
- Add FocusIndex, Window tab order list, InsertTabOrderAfter/Before
- Add UIControl.HasFocus query property

## Bug Fixes
- Nest CheckState inside Checkbox instead of global scope (#440)
- Nest CheckState inside Checkbox instead of global scope
- Native baseline chrome + TextControl font-push (follow-up to #438) (#439)
- Push TextControl.FontName/FontSize to the real native control
- Compute baseline from real native control chrome, not font math alone
- Baseline anchor layout uses real per-platform font metrics (#438)
- Wire real per-platform bridges into Baseline anchor layout
- Autosave stripped Developer Identity; reuse it in the Sign step (#435)
- Autosave stripped Developer Identity; reuse it in the Sign step
- Pass mac Developer Identity to Run/Debug compiles (#434)
- Pass mac Developer Identity to Run/Debug compiles
- Reject Secure prefs calls on unsigned builds (E210) (#431)
- Reject Secure prefs calls on unsigned builds (E210)
- TextField/TextArea FocusGained now fires on keyboard Tab (#429)
- TextField/TextArea FocusGained now fires on keyboard Tab
- Build Graph Sign step now runs after the compile it's wired to (#428)
- Linux TabView teardown double-free / SIGBUS (#425)
- Build Graph Sign step now runs after the compile it's wired to
- Linux TabView teardown double-free / SIGBUS
- MacOS secure-prefs hangs/crashes across rebuilt-binary Keychain identities (#424)
- MacOS secure-prefs hangs/crashes across rebuilt-binary Keychain identities
- Tab strands focus instead of advancing (missing WS_EX_CONTROLPARENT + tab-order registration race)
- ComputeRelocationTarget must exclude the whole departing subtree, not just focused
- Tab-order commit does minimal z-churn instead of hoisting to top
- Tab-order key-view chain wraps and never messages a closed window
- TabView sync/slot/relocation-order/registration/self-anchor bugs (§31 review)
- Cross-platform tab-order effective-focusability bugs on Linux/Windows
- HasFocus is a Function, not a Property, in tab-order.md
- Stop IsEffectivelyFocusable's page-selected check from skipping the container's own Visible/Enabled
- Exclude Window's on-screen-shown state from IsEffectivelyFocusable
- Change tab-order helpers from Public to Internal visibility
- Remove tautological assertion in tab-order test
- Install git-lfs on release runner before checkout (#421)
- Install git-lfs on release runner before checkout

## Changes
- Rebuild Linux libbuoy_layout.so with the Baseline anchor fix
- Strip VB/Xojo/Basic references from buoy ai init output (#437)
- Strip VB/Xojo/Basic references from buoy ai init output
- Skill for cleaning up branches and worktrees
- Regression coverage for space/umlaut paths in Copy Resources (#433)
- Strip spaces from hex-formatted Developer Identity on blur (#430)
- Regression coverage for space/umlaut paths in Copy Resources
- Native regression guard for macOS secure-prefs cross-identity read hang (#427)
- Merge remote-tracking branch 'Github/main' into fix/macos-secure-prefs-read-hang-test
- Native regression guard for macOS secure-prefs cross-identity crash (#426)
- Native regression guard for macOS secure-prefs cross-identity read hang
- Native regression guard for macOS secure-prefs cross-identity crash
- Tab Order and Focus Traversal (core) (#423)
- Docs+test(ui): tab-order documentation, sample, and CMake registration
- Cover IsDescendantOrSelf and the Focusable=True append path


---

# v0.56.0

## New Features
- Nesting-aware End Handle scanner with per-control degradation
- Preserve inline Handle blocks as keyed opaque spans
- Badge and list inline Handle blocks in the layout editor
- Warn before deleting a layout control that owns inline Handle code
- Report inline Handle spans in buoy/layoutOutline and degrade per-control on a broken body
- Lower window-level inline Handle blocks into the lowered Window class
- Diagnose bad inline Handle blocks in Window Control bodies
- Lower control-level inline Handle blocks into the synthesized <control>_<Event> hook
- Accept inline Handle blocks in Window/View bodies; share one Handle parser
- Add constraint reattach-drag and delete-via-trash
- Add inline relation/offset/priority editor popover
- Add anchor hit-targets and create-drag targeting engine
- Add constraint-drag axis/targeting/text-generation logic module
- Add scrollable zoomable canvas viewport with a zoom control
- Add zoom math pure-logic module for the layout editor
- Add Preview Constraints toggle with per-workspace persistence
- Render constraint preview lines and anchor dots in the layout editor
- Add constraint-overlay geometry/label logic module
- Decompose Constraints-line relation/priority/RHS into buoy/layoutOutline

## Bug Fixes
- Resized/ScaleFactorChanged firing during Window construction crashes on unbuilt siblings
- Stop the layout editor's handler badge from being clipped
- Preserve blank lines and comments inside Handle bodies
- Don't false-positive resync on bare-word statements that aren't block openers
- Correct misleading comment about handler signature validation
- Re-render on zero-movement selection click (#418)
- Re-render after zero-movement guard so selection still refreshes the view
- Apply the same zero-movement guard to multi-select and window-resize drags
- Selecting a constrained control no longer flattens its relative constraints to absolute pins
- Drop BaselineAnchor from the selected-control anchor-dot list
- Layer constraint overlay paint order, widen center-anchor fan offset, guard axis-less endpoint handles, and fix drag-preview cleanup/trash positioning
- Copy Resources nests into .app Contents, forces overwrite (#415)
- Paint anchor hit-targets under constraint endpoint handles; preserve Medium/Low priority on untouched reattach
- Build graph persist no longer races an open buoy-build-graph.json editor tab
- Correct Enter-on-Cancel and popover cleanup on external re-render
- Copy Resources nests into .app Contents, forces overwrite
- Fan CenterX/CenterY anchor dots apart, scale snap radius by zoom
- Preserve canvas-viewport scroll position across re-renders
- Keep resize handles and anchor dots a constant size across zoom levels
- Make drag/resize pointer math zoom-aware
- Correct zoom-anchored scroll padding offset and isolate floating buttons from scroll
- Anchor overlay to unresolved-control placeholder geometry, add markers for constant/unstructured constraints
- Correct RHS-selected constraint lines, case-insensitive frame lookups, and dimension-bracket hover/label/fan-out

## Changes
- Fix Resized/ScaleFactorChanged crash during Window construction (#420)
- Inline Handle blocks in declarative Window blocks (#419)
- Add inline-Handle Window block sample and unit test
- Selecting or clicking a constrained/multi-selected control flattens or duplicates its constraints (#417)
- Layout editor: drag-and-drop constraint creation and editing (#416)
- Layout editor: zoom and pan (#414)
- Constraint preview in the layout editor (#411)


---

# v0.56.0

## New Features
- Nesting-aware End Handle scanner with per-control degradation
- Preserve inline Handle blocks as keyed opaque spans
- Badge and list inline Handle blocks in the layout editor
- Warn before deleting a layout control that owns inline Handle code
- Report inline Handle spans in buoy/layoutOutline and degrade per-control on a broken body
- Lower window-level inline Handle blocks into the lowered Window class
- Diagnose bad inline Handle blocks in Window Control bodies
- Lower control-level inline Handle blocks into the synthesized <control>_<Event> hook
- Accept inline Handle blocks in Window/View bodies; share one Handle parser
- Add constraint reattach-drag and delete-via-trash
- Add inline relation/offset/priority editor popover
- Add anchor hit-targets and create-drag targeting engine
- Add constraint-drag axis/targeting/text-generation logic module
- Add scrollable zoomable canvas viewport with a zoom control
- Add zoom math pure-logic module for the layout editor
- Add Preview Constraints toggle with per-workspace persistence
- Render constraint preview lines and anchor dots in the layout editor
- Add constraint-overlay geometry/label logic module
- Decompose Constraints-line relation/priority/RHS into buoy/layoutOutline

## Bug Fixes
- Resized/ScaleFactorChanged firing during Window construction crashes on unbuilt siblings
- Stop the layout editor's handler badge from being clipped
- Preserve blank lines and comments inside Handle bodies
- Don't false-positive resync on bare-word statements that aren't block openers
- Correct misleading comment about handler signature validation
- Re-render on zero-movement selection click (#418)
- Re-render after zero-movement guard so selection still refreshes the view
- Apply the same zero-movement guard to multi-select and window-resize drags
- Selecting a constrained control no longer flattens its relative constraints to absolute pins
- Drop BaselineAnchor from the selected-control anchor-dot list
- Layer constraint overlay paint order, widen center-anchor fan offset, guard axis-less endpoint handles, and fix drag-preview cleanup/trash positioning
- Copy Resources nests into .app Contents, forces overwrite (#415)
- Paint anchor hit-targets under constraint endpoint handles; preserve Medium/Low priority on untouched reattach
- Build graph persist no longer races an open buoy-build-graph.json editor tab
- Correct Enter-on-Cancel and popover cleanup on external re-render
- Copy Resources nests into .app Contents, forces overwrite
- Fan CenterX/CenterY anchor dots apart, scale snap radius by zoom
- Preserve canvas-viewport scroll position across re-renders
- Keep resize handles and anchor dots a constant size across zoom levels
- Make drag/resize pointer math zoom-aware
- Correct zoom-anchored scroll padding offset and isolate floating buttons from scroll
- Anchor overlay to unresolved-control placeholder geometry, add markers for constant/unstructured constraints
- Correct RHS-selected constraint lines, case-insensitive frame lookups, and dimension-bracket hover/label/fan-out

## Changes
- Fix Resized/ScaleFactorChanged crash during Window construction (#420)
- Inline Handle blocks in declarative Window blocks (#419)
- Add inline-Handle Window block sample and unit test
- Selecting or clicking a constrained/multi-selected control flattens or duplicates its constraints (#417)
- Layout editor: drag-and-drop constraint creation and editing (#416)
- Layout editor: zoom and pan (#414)
- Constraint preview in the layout editor (#411)


---

# v0.55.1

## Changes
- Build Graph: add Build sink endpoint, allow dragging edge endpoints to rewire
- Build Graph: show Copy Resources source/destination and Run Script's path
- Build Graph: work with a single open file, no workspace required
- Build Graph: fix edge endpoint drag handle visibility and hover behavior
- Sign step: clear extended attributes before codesign
- Run Script step: respect quoted strings in the Arguments field
- Warn when a project's package version differs from buoy's bundled copy


---

# v0.55.0

## New Features
- Sink-only Run/Debug connectors, edge hit-area, hover, and arrowheads
- Run Run/Debug through the build graph with chain-rooted output dirs
- Add isSinkOnly predicate for Run/Debug edge validation
- Add load-time migration for backward Run/Debug edges
- Add chain-rooted build output directory resolution for Run/Debug

## Bug Fixes
- Rebuild an ancestor whose cached 'success' status no longer matches disk
- Sign step auto-resolves the built binary instead of requiring manual path entry
- Sign step errors on a blank path instead of signing the build output folder
- Save dirty docs, avoid stale-status skip across chain roots, and fix output-clobber in graph Run/Debug


---

# v0.54.1

## Bug Fixes
- Vendored zlib/libpng symbols no longer leak from pdf/zip packages (#404)
- If() ternary unifies Nil with reference types (#403)
- MacOS Graphics.DrawPicture renders vertically flipped (#402)
- Copy Resources build step supports single-file sources (#401)
- Select Case FCmp verifier failure on Double/Boolean selectors (#400)
- Vendored zlib/libpng symbols no longer leak from pdf/zip packages
- If() ternary unifies Nil with reference types
- MacOS Graphics.DrawPicture renders vertically flipped
- Copy Resources build step supports single-file sources
- Select Case FCmp verifier failure on Double/Boolean selectors
- Indent FileType block bodies in LSP formatter (#399)
- Indent FileType block bodies in LSP formatter
- Strip CRLF from package name in Windows installer staging (#398)
- Strip CRLF from package name when staging Windows installers


---

# v0.54.0

## New Features
- Add FileType language declaration (#396)
- Emit Inno Setup .iss registry fragment for FileType blocks on Windows
- Emit CFBundleDocumentTypes/UTExportedTypeDeclarations for FileType blocks
- Add FileType sample, unit test, and documentation
- Add AddFilter(fileType As FileType) overload to OpenFileDialog/SaveFileDialog
- Desugar FileType blocks into synthesized zero-arg constructor functions
- Validate FileType block fields in Sema
- Parse FileType top-level block declarations
- Add FileType keyword token
- Add stdlib FileType class and FileKind/FileTypeRole/FileTypeRank enums
- Locale.Current() takes a fallback parameter for the last-resort locale

## Bug Fixes
- Stop shipping internal ctest fixture packages in installers (#397)
- Stop shipping internal ctest fixture packages in installers
- Locale.Current() recovers real base locale instead of downgrading to en-US (#395)
- Address final-review findings — FileType script injection, plist/case bugs, test coverage
- Emit MimeType= and shared-mime-info XML for FileType blocks on Linux; fix .desktop gating for FileType-only projects
- Guard optional FileType plist keys against empty-value emission
- FileType desugar — Name falls back to block identifier, Icon resolves eagerly
- Locale.Current() reads native OS state instead of resolving an identifier
- Locale.Current() recovers from macOS Region Override's @rg= modifier
- Locale.Current() recovers the real base locale instead of downgrading to en-US
- Locale.Current() no longer crashes on unrecognized OS locale identifiers


---

# v0.53.0

## New Features
- Add pdf package sample, unit test, and CMake registration
- Implement PDFPage and PDFGraphics (Implements IGraphics)
- Rework pdf package to shim-based float-narrowing design (Task 4)
- Add libharu vendor scripts (Linux + Windows cross targets)
- Add PDF.bui Declares, error handling, and PDFDocument core
- Add pdf package scaffolding (libharu shared build, all 6 targets)
- Add libharu vendor scripts (macOS arm64 + x86_64)
- Add libpng vendor scripts (Linux + Windows cross targets)
- Add libpng vendor scripts (macOS arm64 + x86_64)
- Add cross-platform DisclosureTriangle control (#390)
- Add IGraphics interface for backend-agnostic drawing routines

## Bug Fixes
- Installers kill stale buoy-lsp/buoy-dap before overwriting binaries
- Correct PDFGraphics rendering and FFI int widths in the pdf package
- Nil-check Picture.ToPNG() result in PDFGraphics.DrawPicture
- Plug malloc leak on ToBytes() error path in PDF.bui
- Switch PDF.bui page-size Declares to bui_pdf_* shim (Task 5 rework)


---

# v0.53.0

## New Features
- Add pdf package sample, unit test, and CMake registration
- Implement PDFPage and PDFGraphics (Implements IGraphics)
- Rework pdf package to shim-based float-narrowing design (Task 4)
- Add libharu vendor scripts (Linux + Windows cross targets)
- Add PDF.bui Declares, error handling, and PDFDocument core
- Add pdf package scaffolding (libharu shared build, all 6 targets)
- Add libharu vendor scripts (macOS arm64 + x86_64)
- Add libpng vendor scripts (Linux + Windows cross targets)
- Add libpng vendor scripts (macOS arm64 + x86_64)
- Add cross-platform DisclosureTriangle control (#390)
- Add IGraphics interface for backend-agnostic drawing routines

## Bug Fixes
- Installers kill stale buoy-lsp/buoy-dap before overwriting binaries
- Correct PDFGraphics rendering and FFI int widths in the pdf package
- Nil-check Picture.ToPNG() result in PDFGraphics.DrawPicture
- Plug malloc leak on ToBytes() error path in PDF.bui
- Switch PDF.bui page-size Declares to bui_pdf_* shim (Task 5 rework)


---

# v0.52.0

## New Features
- Add EndOfLine platform line-ending constants (#378)

## Bug Fixes
- Linux Graphics.DrawPicture swaps red/blue and drops alpha for loaded Pictures (#389)
- Windows ServerSocket uses SO_EXCLUSIVEADDRUSE instead of SO_REUSEADDR (#388)
- Give each Windows/Linux remote test lane its own staging directory (#387)
- Enable Windows stack probes for vendored Zint (barcode PDF417/Aztec crash) (#386)
- Harden getQueueInitFn's POSIX guard with CAS + memory ordering (#385)
- Standalone_cache_isolation asserts on the wrong -v line (#384)
- Windows picture blitting drops per-pixel alpha (#383)
- MacOS MenuBar intermittently empty on launch (#382)
- LSP resolves package-qualified Import against .buoy/packages/ (#381)
- File.Exists fails to link on both Windows targets (#380)
- Uncaught-exception fallback reports real type/message/code (#379)
- Build expected paths with path.join in vscode stepType tests (#377)


---

# v0.51.0

## New Features
- Make Picture.Scale writable (#376)
- Bug-triage posts as buoy-triage-bot GitHub App; add not-a-bug confirmation gate
- Add FileSystemItem.Permissions for POSIX-style rwx bits

## Bug Fixes
- Locale.Current() no longer crashes on unrecognized OS locale identifiers (#374)
- Bump @hono/node-server to 1.19.17 (alert #45) (#372)
- LSP Shared Property completion; scope Picture.ImageFormat; VSCode word-suggest default
- Avoid node --test glob arg, Node 20 CI doesn't support it


---

# v0.50.0

## New Features
- Windows native implementation for Picture.Graphics offscreen drawing
- Implement Linux canvas backing + offscreen Graphics
- Wire Picture.Graphics/FromBuffer/GetBacking in the Buoy stdlib
- Implement macOS canvas backing + offscreen Graphics
- Add shared canvas-backing conversion code and C ABI declarations

## Bug Fixes
- Use node --test glob instead of bash $(find ...) in test:unit
- Address final-review findings for Picture.Graphics (feat/picture-graphics)
- Close ensure_canvas mutex race and generalize the fix


---

# v0.49.0

## New Features
- Build barcode package for Linux (x86_64+arm64), re-enable cross-platform tests
- Build barcode package for Windows (x64+arm64)
- Build barcode package for macOS (arm64+x86_64)
- Add Barcode.bui wrapper (Symbologies, Options, Encode)
- Add barcode package native shim (Zint + stb_image_write)

## Bug Fixes
- Copy barcode sample into examples/ and correct QR comment
- Guard oversized barcode payloads and silent Nil PNG decode
- Correct barcode.bui sample Expected comments to match real output
- Retype barcode Declare params to Int32/UInt8 to fix ARM64 crash
- Flatten nested classes in Barcode.bui, fix Double->Integer CType misuse
- VSCode auto-indent recognizes SyncLock as a block keyword
- Buoy-lsp never publishes diagnostics for vendored .buoy/packages/ files
- VSCode indentation - case-insensitive keywords, bidirectional Else/Case/Catch/Finally, drop ambiguous Property
- VSCode auto-indent recognizes all block constructs, not just a handful
- Exclude preproc_error_warning from Windows remote CI, Error-on-Windows is by design
- Remove stale loose fluenticons directory before writing sealed buipkg
- Exclude delegates_ffi from Windows remote CI, SIGUSR1 has no equivalent there
- Exclude 4 known-affected tests from windows_arm64_remote CI lane
- Toolbar.AddCustomView after attachment no longer corrupts widget lifetime on Linux
- Remove dimming on build graph nodes pending dependency


---

# v0.48.0

## New Features
- Add Run Script step type to build graph editor
- Widen Toolbar to TargetLinux, refresh docs/sample for Windows+Linux rendering
- Linux toolbar overflow chevron + CustomView/Separator/Space/FlexibleSpace
- Linux toolbar Group/MenuButton/SearchField item kinds
- Linux toolbar backend skeleton - Button/ToggleButton with DisplayMode
- Windows toolbar overflow chevron for items that don't fit the band width
- Windows toolbar MenuButton chevron indicator, confirm Group icon rendering
- Windows toolbar Button/ToggleButton owner-draw icon+DisplayMode rendering
- Add Picture.FromSystemIcon(String) and Toolbar icon-as-String overloads

## Bug Fixes
- Wire ToolbarCustomView.Overflow to native layout on all 3 platforms
- ToolbarGroup.PerformAction() incorrectly fires ToolbarAction (Windows/macOS)
- Run-remote-test.sh only verified the main binary's hash, not companions
- Linux StreamSocket.Close() never unblocked a reader thread blocked in recv()
- Linux arm64 accept() failure misread as success (missing SignExtend32)
- Windows StreamSocket.Close() hangs when reader thread blocked in ReadFile/recv
- Stop Linux Label controls from pinning the whole window's minimum width
- Give IconOnly/TextOnly toolbar rows more height
- Let SearchField/CustomView hide into toolbar overflow again
- Let Linux toolbar window shrink enough to trigger overflow chevron
- Add missing SafeArea regression control to toolbar sample
- Premultiply Windows toolbar overflow popup icon bitmaps
- Linux toolbar overflow popover torn down every tick + missing dead-chevron guards
- Close remaining dead-chevron path for toolbar overflow via Space/FlexibleSpace
- Windows toolbar overflow popup empty when SearchField/CustomView is the only overflowing item
- Measure Windows toolbar button width from real font metrics
- Linux toolbar DisplayMode recursion into Group children
- Windows toolbar icon alpha compositing and IconAndText caption clipping
- Correct toolbar overflow FlexibleSpace width sum + CustomView UAF
- Suppress spurious ToolbarAction on programmatic Toggled set
- Reserve space for MenuButton chevron and fix its font
- Correct stale comment on toolbar icon rendering scope (Win32)
- Sync resize_last_w/h in layoutToolbarBand synthetic re-fire
- Windows WM_SIZE now reports toolbar-band-subtracted content height


---

# v0.47.0

## New Features
- Add cross-platform accessibility to UIControl
- Add Application.UnhandledException crash-reporting hook
- Add Open Build Graph button to Project Build Settings
- Add right-click Add/Edit/Delete menus and schema-driven forms
- Absolute-position, draggable, linkable nodes in the build graph webview
- Walk the upstream chain when running a build graph node
- Add node/edge CRUD and persistence to the build graph panel
- Add custom-step task kind to the build graph task provider
- Extend build graph postMessage protocol for editable nodes/edges
- Add build-graph-file persistence (load/save)
- Add upstream-chain resolution with runMode filtering
- Add cycle detection for build graph edges
- Add step-type registry
- Add Sign step type
- Add step-type framework, unit test harness, Copy Resources step
- Add Build Graph panel (v1) - read-only target status board

## Bug Fixes
- Edge lines anchor to measured connector-dot positions, not guessed math
- Node stays "running" forever on an early error path
- Copy Resources hang, wrong-folder targeting, dark-mode borders; add Stop
- Address live-testing feedback on the build graph webview
- Sync-guard Shell cross-thread state and close DataAvailable notify race
- Address final-review findings (shell quoting, copy idempotency, listener leak, test wiring)
- Suppress post-drag click and reset stale pointer-drag state on re-render
- Set running status synchronously to close re-entrancy race window
- Guard against re-entrant node execution and handle executeTask failures
- Prune edges referencing deleted nodes on rebuild
- Clean out/test before rebuilding in test:unit script
- Bump hono to 4.13.1 in editors/mcp (alerts #34, #41, #42, #43)
- Bump fast-uri override to 3.1.5 in editors/mcp (alert #30)
- Bump ip-address to 10.4.0 in editors/mcp (alerts #31, #32, #33)
- Bump fast-uri override to 3.1.5 in editors/vscode (alert #35)
- Bump js-yaml to 4.3.1 in editors/vscode (alert #44)
- Bump undici to 7.29.0 in editors/vscode (alerts #36, #37, #38, #39, #40)


---

# v0.46.1

## Bug Fixes
- Tests/zip.bui hardcodes POSIX /tmp paths, fails first assertion on Windows
- Windows ServerSocket Mode.IPC aliases listening pipe as accepted connection, double-closes it
- Run-remote-test.sh can silently run a stale binary on extract failure
- Syntax to call a Shared method/property on a generic-class instantiation
- Fileservice-buoy GET /help crashes with NilObjectException
- Drop invalid static-local capture in PrefsLinux.cpp std::call_once
- Bui_picture_to_png passes libpng row_stride in components, not pixels


---

# v0.46.0

## New Features
- Add Build/Debug buttons to editor toolbar and context menu
- Add buoy.debug command

## Bug Fixes
- Default uninitialized String properties/fields to "" instead of null
- Apply real C-ABI coercion to FFI struct-by-value returns
- Add ldiv to Windows CRT stubs, fix LDivT LP64/LLP64 mismatch
- ListBox.RowAt/ColumnAt silently double-scale under real Windows DPI
- Floor p2l() toward negative infinity instead of truncating toward zero
- Gate ffi_localtime_r worked example for Windows
- Unary Not on Integer/Flags Enum produces valid bitwise complement
- Enforce StreamSocket.Timeout on Connect and Write
- Resolve `Package <name>` declarations in LSP document analysis
- Embed asInvoker Windows manifest in every binary Buoy produces
- Scope workspace/symbol to the whole program's import closure, not just the forward closure
- Use strtoll instead of strtol for Integer.Parse on Windows
- Use OS temp dir instead of hardcoded /tmp in http-server test
- Mangle generic-class Enum type arguments correctly instead of "$Unknown"
- ServerSocket accept thread never exits on Linux Close(), plus StreamSocket fd leak
- Type-check Shared Property const-foldable initializers in Sema
- Remote test harness never closes launched process's stdin, hanging stdin-reading tests
- Clean stale temp .app bundle before VSCode Run/Debug compile
- Linux clipboard async read deadlocks on self-owned content (no timeout escape hatch)
- Rebuild zip package's stale Windows minizip-ng.dll (snprintf + strdup)
- @Aligned class allocation crashes Windows at load (STATUS_ENTRYPOINT_NOT_FOUND)
- Cstring test's user-facing strdup declare crashes Windows at load
- Windows binaries using String.RegexMatch/RegexReplace crash at load (STATUS_ENTRYPOINT_NOT_FOUND)


---

# v0.45.0

## New Features
- Basic Import flattens by default, opt out with As or selective list
- Implicit conversion on Dim initializer and plain reassignment
- Hide underscore-prefixed names from LSP autocomplete
- Enforce Public/Private on package declares/*.bui, default Private to the package
- Add Prefs.SetSecure/GetSecure/HasSecure/DeleteSecure and PrefsException
- Implement Linux libsecret+OpenSSL-fallback backend for secure Prefs
- Add FileSystemItem.CreateFolder
- Implement Windows Credential Manager backend for secure Prefs
- Implement macOS Keychain backend for secure Prefs
- Declare secure Prefs C ABI in PrefsC.h
- Add .Name pseudo-property on enum-typed values
- Resolve Enum.Values Of T to a synthesized Array Of T literal
- Parse Enum.Values Of T as a namespace call with a type argument

## Bug Fixes
- Retain accepted ServerSocket connection past ConnectionRequest
- RunLoop dispatch-queue init race in --library builds
- Address final-review findings — extend implicit conversion to member writes and Shared/Lazy Property initializers, ship docs/plan/tests
- Extend implicit conversion fallback to class field initializers
- Reject @-attributes placed on a declaration that doesn't accept one
- Validate @Aligned(N) is a power of two >= 8, not just an Integer
- Create the Linux fallback .enc file 0600, not umask-default
- Apply the code changes described in 06c6971a
- Address final whole-branch review findings
- Use SECRET_SERVICE_OPEN_SESSION for the reachability probe
- Distinguish libsecret loadable from Secret Service reachable
- Address code review findings in Linux secure-Prefs backend
- Array.Append/Insert require exact element type, breaking Liskov substitution
- Correct DeleteSecureDomain partial-failure and enumerate-error handling
- Address code review findings in macOS Keychain secure-prefs backend
- Close RunLoop dispatch queue's lazy check-then-init race
- Populate TCPSocket.LocalPort via getsockname(), stopgap StreamSocket.Timeout default
- Close Shell resource leaks on error/teardown paths
- Reject trailing args on Enum.Values Of T, fix docs and stale comment
- Update stale EnumEntry doc comment, dedupe .Name codegen branch emission
- Bare access to own Shared members inside a Shared method; ship Assigns shared-receiver coverage


---

# v0.44.1

## Bug Fixes
- Stepper.SetRange re-clamps an already-set Value when the range narrows
- Make canonical buoy_ui.def the single source of truth for Windows stubs
- Make Windows runtime link steps produce reproducible builds
- Avoid SIGPIPE + pipefail false failure in nm|grep -q self-checks
- Fixed-mode array mutation now traps NotResizableException, not InvalidArgumentException
- Add missing sqlite3 sample cross-platform test coverage
- Drop unreachable field-target support from @Aligned
- Vendor zlib so its license reaches the release zip
- Guard plain StreamSocket NativeRead/NativeWrite against closed-fd reuse
- Reject non-foldable Const initializers in Sema instead of crashing
- Str() hard-errors on unhandled sized-integer widths
- Null window callbacks before DestroyWindow — Windows teardown heap corruption


---

# v0.44.0

## New Features
- Add constructor-argument syntax to Window/View/Control block declares

## Bug Fixes
- Complete Handle MenuSelected As Boolean migration in stale samples/tests/docs
- Flush buffered stdio before StdOut/StdErr raw write() calls
- Substitute generic type parameter in CType/TryCast/IsA cast targets
- Import real ucrtbase log2 instead of double-rounding on Windows
- Restore sticky IRBuilder debug location after Block/Lambda body emission
- Reject loop control inside a Lambda targeting an outer loop instead of crashing codegen
- Merge Windows AppIcon and version resources into one COFF object
- Make package payload verification O(N) instead of O(N^2)
- Link libraries referenced only by method-scoped Declares
- Resolve bare array-element write to instance Property instead of erroring undefined variable
- Resolve bare array-typed instance Property access instead of erroring undefined function
- Rebuild Linux x86-64 libbuoy_picture.so with lunasvg, harden build scripts against silent stub fallback
- Stage Resources/ on remote-test uploads; sanitize fluenticons digest path on Windows
- Stop attaching .zip/.tgz staging payloads to published releases


---

# v0.43.0

## New Features
- Add SelectFolderDialog and expand file dialog properties

## Bug Fixes
- Create missing output directory before linking, on all targets
- Enable AES crypto backend for zip package on Linux
- Parse explicitly-typed structure literals as call arguments
- Resolve class-nested enum unqualified in its own method signatures
- Stop generic Of-list parsing from consuming a following parameter's comma
- Stop GTK Window teardown from freeing already-destroyed child widgets
- Sink floating GTK4 widget refs before unref on Linux
- Universal-darwin desktop .app bundles no longer fail at lipo
- Add getenv/_putenv_s to Windows ucrtbase stub, fixing System.EnvironmentVariable setter link failure
- Bound WinHTTP connect/DNS-resolve timeouts on Windows
- Stop buoy_system.dll implicitly importing iphlpapi.dll on Windows
- Bump brace-expansion to patched versions (alerts #28, #29)
- Export bui_message_box_show from Windows buoy_ui.def


---

# v0.42.0

## New Features
- Add Application.Windows/WindowCount
- Add MenuBar.Menus/FindMenuByName/FindMenuByTag

## Bug Fixes
- Shared Property crashes - non-constant initializers and instance access
- Application-level menu dispatch dropped when a Window shares a MenuBar


---

# v0.41.0

## New Features
- Implement Set algebra (Union, Intersect, Difference, IsSubsetOf, IsSupersetOf)
- Allow Structure members to declare inline default values

## Bug Fixes
- Linux .rpm build crashes stripping bundled Windows import-lib stubs
- Discord release notification errors fail the release, cap math can exceed 2000 chars


---

# v0.40.0

## New Features
- Add yaml package (YamlItem, mirroring JSONItem's API)
- Add Alignment (TextAlignment) property to Label/TextField/TextArea
- Add Array.LastIndex(arr) as sugar for Count(arr) - 1
- Add Stepper class to the Buoy UI stdlib
- Add composed two-GtkButton Linux bridge for Stepper
- Add standalone msctls_updown32 Windows bridge for Stepper
- Add NSStepper-backed macOS bridge for Stepper
- Add BUI_KIND_STEPPER tag and stepper C ABI prototypes

## Bug Fixes
- TextField(FieldType.Number) doesn't restrict input on any platform
- Window-block and other synthesis-pass diagnostics misattribute file to <stdlib:UI>
- Reject Window-block control names that collide with a synthesized hook
- Optional<sized-int>.Or(literal) fails LLVM IR verification
- Random.RandomInteger/Currency.FromInteger/FromMinorUnits/Sleep reject sized ints
- Array.Count/.Count/Array.LastIndex segfault on a nil array element
- Uncaught runtime traps print a diagnostic before aborting
- Assignment through a member on an indexed/call statement head
- Vendor AppKit.tbd so Declare ... Lib "AppKit" actually links
- Array-property element write through a dotted/Me receiver
- Minizip-ng Windows package build — undefined snprintf
- Identifier-form Import resolves against the importing file's own directory
- Verify DateTime/TimeZone sized-int args, close stale bug report
- Mark Export'ed functions dllexport so Windows --library builds actually export symbols
- Reject compound-assign/read through bare-name Assigns setter with a clear diagnostic
- Rename regex package's Match consumers to RegexMatch
- Gate tests/streams.bui and samples/streams.bui tmp paths for Windows
- Link Windows targets against ucrtbase before msvcrt (cross-CRT crash)
- Attribute structural diagnostics to the user's file, not <stdlib:UI>
- Allow zero-arg bare-name Assigns setter dispatch (c() = 5)
- Move _ftelli64 from msvcrt to ucrtbase in Windows stub (STATUS_ENTRYPOINT_NOT_FOUND)
- Zip-based remote-test transfer + WSL warm-up for the Linux lab lane
- Socket_ffi_layer test - gate Windows Import/handles per target
- Skip resolution for already-loaded prelude imports (E209 regression)
- Shrink oversized Linux Stepper buttons to match @ControlSize(19, 27)
- Windows step-count FP epsilon guard; polish docs; file set_range clamp gap; archive plan
- Correct Stepper step-count flooring and set_range repositioning
- Disable rpm brp-strip pass to unblock Linux .rpm packaging


---

# v0.39.1

## Bug Fixes
- Cross-link TCPSocket/ServerSocket/TLS for x86_64-darwin
- Add raise/ldiv to the Linux libc cross-link stub
- GTK4 Linux controls no longer fire change-events for programmatic sets
- Export Block-runtime symbols in the x86_64 macOS libSystem.tbd stub
- Allow unqualified nested-enum references in a Property's default initializer
- Abstract method with a body no longer desyncs the parser's class scope
- Export ___exp10/_exp2 in macOS libSystem.tbd stubs for optimized Math.Pow builds


---

# v0.39.0

## New Features
- Native .deb/.rpm packages for Linux; switch Linux zip to .tgz
- Expand Package to whole-package imports, add packages-src fallback
- Fold Module dots in class-method mangling
- Resolve Module-qualified classes, enums and calls
- Resolve flattened Package symbols and report collisions
- Parse Package and Module declarations
- Add PackageDecl plus Module nsPrefix/flatten fields
- Reserve 'Package' and 'Module' keywords

## Bug Fixes
- Socket background thread racing process-exit teardown of SocketDispatchable.mLock
- StreamSocket/TCPSocket/ServerSocket leak their OS sockets when dropped without Close()
- --debug builds segfault destroying a Thread or Task
- UDPSocket leaks its OS socket when dropped without Close()
- Windows SCM console-redirect crash was a CRT link-order bug, not Session-0-specific
- Preserve Event/Operator declarations through generic-class monomorphization
- Package-qualified module identity for same-named package modules
- Throw/Try/RaiseEvent silently dropped from generic-class method bodies
- Emit //, /* */, and #If highlighting rules in VSCode grammar generator
- VSCode Run button breaks on Windows (PowerShell &&, missing .exe)
- Constructor throw leaks partially-constructed object
- Treat a bare 'Package' declaration as a dependency in forEntry()
- One canonical shadow predicate for Module/namespace qualification
- Instance fields/Properties shadow Module and namespace names
- Guard namespace-qualified call dispatch against shadowing locals
- Guard Module dotted-receiver collapse against shadowing locals
- Move duplicate-class file attribution to PartialClassMerge
- Accept soft-keyword class names (Set/Get) in New's dotted-segment loop


---

# v0.38.0

## New Features
- BuoyScript — embeddable Buoy JIT (LLVM ORCv2)
- Value-returning Event/Handle/RaiseEvent + HTMLView.CancelLoad
- Add Application.Executable As FileSystemItem
- Add WindowType, Window.Close(), and Window.ShowModally
- Autosave Project Build Settings webview
- Add System.Log / LogLevels
- Add System.EnvironmentVariable (get/set)
- Add System.CPUCount
- Bare Import <Package> falls back to a same-named installed package

## Bug Fixes
- Resolve each library in a multi-library package to its own file
- Bump brace-expansion to 5.0.8 (alert #27)
- Nest LogLevels inside Class System
- Include Windows installer exes in published release assets
- EmitTryUnwind reverse-iterator invalidated by nested Try in a Finally body
- Stop false-positive property/method name-collision warning on TimeZone.OffsetFromUtc
- Release Shared Property object slots at exit, stopping false-positive leak reports


---

# v0.37.0

## New Features
- Sample for labeled Exit For / Continue For
- Windows installer (Inno Setup) for both architectures
- Target the named loop from labeled Exit For / Continue For
- Validate Exit For / Continue For loop-variable labels (E423)
- Parse optional loop-variable label on Exit For / Continue For
- For...Downto descending-loop shorthand (buoy-releases#68)
- GitHub Actions workflow for automated issue triage

## Bug Fixes
- Return loop frame by value from resolveLoopFrame to avoid dangling pointer
- Guard Exit/Continue loop-variable rejection on recognized operand


---

# v0.36.1

## Bug Fixes
- Leak detector no longer walks freed nodes (buoy-releases#64)
- For loop with a negative Step now runs (was zero iterations)
- Show Buoy project-settings gear on activation, not only after tab switch
- Attach Linux/Windows packages to the same release as macOS


---

# v0.36.0

## New Features
- Add Windows/Linux build toggles to Mac release workflow


---

# v0.35.0

## New Features
- ByRef works on arrays and every other reference type
- Add backlog sweep phase to bug-triage skill
- Dismiss shipped Dependabot alerts as fix_started
- Leak detector reports per-object detail instead of just a count
- Build buoy-dap and buoy-debugstub on Windows and Linux
- Vendor OpenSSL natively on Windows and Linux self-hosted runners
- Vendor GoogleTest instead of relying on vcpkg/system packages

## Bug Fixes
- Retain by-value object/array parameters so reassigning one doesn't free the caller's object
- Debugger shows array and composite values instead of empty rows
- Bump hono to 4.12.31 in editors/mcp (alerts #20, #21, #22)
- Bump fast-uri to 3.1.4 in editors/mcp (alerts #23, #24)
- Bump fast-uri to 3.1.4 in editors/vscode (alerts #25, #26)
- Non-macOS builds defaulted to a macOS target; packaged distributions swept their own bundled packages
- Make build-llvm-prebuilt.yml publish step additive, not destructive
- Linux .so SONAME/filename mismatch broke zip + regex packages; Windows CRT time exports
- Package.sh/package-linux.sh never bundled libbuoy_tls.a + OpenSSL
- Stage examples at zip top level on Linux and Windows
- Use MSVC CRT _environ instead of GetEnvironmentStringsA
- Windows portability for ChildProcess.cpp
- Guard windows.h includes against min/max macros
- Detect and bundle liblldb.so (Linux) and .lib/.dll (Windows)
- Bundle lib/runtime and packages/ on Linux and Windows, fix arm64 mislabeling
- Use bash not pwsh for release-windows.yml publish job LFS step
- Mark linux-arm64 continue-on-error so publish is not skipped
- Pin Node 20 in release-linux.yml and build-platforms.yml
- Resolve --output-dir/--build-dir to absolute paths up front
- Git safe.directory for self-hosted runners, python3 fallback in package-windows.sh
- Windows portability for Link.cpp and ResourceManifest.cpp
- Guard windows.h include against min/max macro collision
- Windows portability for buoy-lsp Transport and DiagnosticsPublisher
- Use Set-Location instead of git -C for git lfs pull
- Pass explicit -C path to git lfs pull under pwsh
- Use pwsh not bash for git lfs pull on Windows
- Force git lfs pull after checkout to guarantee real content
- Fetch real Git LFS content in checkout, not pointer stubs
- Define S_ISDIR on Windows for TlsC.cpp
- Make Program explicitly move-only for MSVC
- MSVC compile errors in Parser.cpp, RegexC.cpp, TlsC.cpp
- Pin PATH to MSVC tools dir so link resolves to the real linker
- Use npm ci instead of npm install for the VSCode extension build
- Prefer Strawberry Perl over Git Bash bundled perl explicitly
- Force --libdir=lib for native OpenSSL builds
- Match Linux ARM64 runner's actual label casing (Linux/ARM64)
- Force clang explicitly when building LLVM on Linux
- Match Linux x86_64 runner's actual label (X64, not x86_64)
- Stop stripping LLVM's bin/ from the prebuilt tarball
- Recognize Windows .dll/.lib naming in vendor-pcre2.sh
- Match minizip-ng's actual static lib name on Windows
- Verify SHA256 checksums for downloaded cmake/ninja binaries
- Convert paths for cl.exe/lib.exe via cygpath, not just exclude flags
- Replace choco with portable cmake/ninja downloads on Windows CI
- Prevent Git Bash from mangling MSVC /flag args in vendor-sqlite.sh
- Surface gh release download errors instead of swallowing them
- Fall back to python instead of hardcoded python3 in workflows
- Make vendor-sqlite.sh portable across macOS/Linux/Windows


---

# v0.35.0

## New Features
- ByRef works on arrays and every other reference type
- Add backlog sweep phase to bug-triage skill
- Dismiss shipped Dependabot alerts as fix_started
- Leak detector reports per-object detail instead of just a count
- Build buoy-dap and buoy-debugstub on Windows and Linux
- Vendor OpenSSL natively on Windows and Linux self-hosted runners
- Vendor GoogleTest instead of relying on vcpkg/system packages

## Bug Fixes
- Retain by-value object/array parameters so reassigning one doesn't free the caller's object
- Debugger shows array and composite values instead of empty rows
- Bump hono to 4.12.31 in editors/mcp (alerts #20, #21, #22)
- Bump fast-uri to 3.1.4 in editors/mcp (alerts #23, #24)
- Bump fast-uri to 3.1.4 in editors/vscode (alerts #25, #26)
- Non-macOS builds defaulted to a macOS target; packaged distributions swept their own bundled packages
- Make build-llvm-prebuilt.yml publish step additive, not destructive
- Linux .so SONAME/filename mismatch broke zip + regex packages; Windows CRT time exports
- Package.sh/package-linux.sh never bundled libbuoy_tls.a + OpenSSL
- Stage examples at zip top level on Linux and Windows
- Use MSVC CRT _environ instead of GetEnvironmentStringsA
- Windows portability for ChildProcess.cpp
- Guard windows.h includes against min/max macros
- Detect and bundle liblldb.so (Linux) and .lib/.dll (Windows)
- Bundle lib/runtime and packages/ on Linux and Windows, fix arm64 mislabeling
- Use bash not pwsh for release-windows.yml publish job LFS step
- Mark linux-arm64 continue-on-error so publish is not skipped
- Pin Node 20 in release-linux.yml and build-platforms.yml
- Resolve --output-dir/--build-dir to absolute paths up front
- Git safe.directory for self-hosted runners, python3 fallback in package-windows.sh
- Windows portability for Link.cpp and ResourceManifest.cpp
- Guard windows.h include against min/max macro collision
- Windows portability for buoy-lsp Transport and DiagnosticsPublisher
- Use Set-Location instead of git -C for git lfs pull
- Pass explicit -C path to git lfs pull under pwsh
- Use pwsh not bash for git lfs pull on Windows
- Force git lfs pull after checkout to guarantee real content
- Fetch real Git LFS content in checkout, not pointer stubs
- Define S_ISDIR on Windows for TlsC.cpp
- Make Program explicitly move-only for MSVC
- MSVC compile errors in Parser.cpp, RegexC.cpp, TlsC.cpp
- Pin PATH to MSVC tools dir so link resolves to the real linker
- Use npm ci instead of npm install for the VSCode extension build
- Prefer Strawberry Perl over Git Bash bundled perl explicitly
- Force --libdir=lib for native OpenSSL builds
- Match Linux ARM64 runner's actual label casing (Linux/ARM64)
- Force clang explicitly when building LLVM on Linux
- Match Linux x86_64 runner's actual label (X64, not x86_64)
- Stop stripping LLVM's bin/ from the prebuilt tarball
- Recognize Windows .dll/.lib naming in vendor-pcre2.sh
- Match minizip-ng's actual static lib name on Windows
- Verify SHA256 checksums for downloaded cmake/ninja binaries
- Convert paths for cl.exe/lib.exe via cygpath, not just exclude flags
- Replace choco with portable cmake/ninja downloads on Windows CI
- Prevent Git Bash from mangling MSVC /flag args in vendor-sqlite.sh
- Surface gh release download errors instead of swallowing them
- Fall back to python instead of hardcoded python3 in workflows
- Make vendor-sqlite.sh portable across macOS/Linux/Windows


---

# v0.35.0

## New Features
- ByRef works on arrays and every other reference type
- Add backlog sweep phase to bug-triage skill
- Dismiss shipped Dependabot alerts as fix_started
- Leak detector reports per-object detail instead of just a count
- Build buoy-dap and buoy-debugstub on Windows and Linux
- Vendor OpenSSL natively on Windows and Linux self-hosted runners
- Vendor GoogleTest instead of relying on vcpkg/system packages

## Bug Fixes
- Retain by-value object/array parameters so reassigning one doesn't free the caller's object
- Debugger shows array and composite values instead of empty rows
- Bump hono to 4.12.31 in editors/mcp (alerts #20, #21, #22)
- Bump fast-uri to 3.1.4 in editors/mcp (alerts #23, #24)
- Bump fast-uri to 3.1.4 in editors/vscode (alerts #25, #26)
- Non-macOS builds defaulted to a macOS target; packaged distributions swept their own bundled packages
- Make build-llvm-prebuilt.yml publish step additive, not destructive
- Linux .so SONAME/filename mismatch broke zip + regex packages; Windows CRT time exports
- Package.sh/package-linux.sh never bundled libbuoy_tls.a + OpenSSL
- Stage examples at zip top level on Linux and Windows
- Use MSVC CRT _environ instead of GetEnvironmentStringsA
- Windows portability for ChildProcess.cpp
- Guard windows.h includes against min/max macros
- Detect and bundle liblldb.so (Linux) and .lib/.dll (Windows)
- Bundle lib/runtime and packages/ on Linux and Windows, fix arm64 mislabeling
- Use bash not pwsh for release-windows.yml publish job LFS step
- Mark linux-arm64 continue-on-error so publish is not skipped
- Pin Node 20 in release-linux.yml and build-platforms.yml
- Resolve --output-dir/--build-dir to absolute paths up front
- Git safe.directory for self-hosted runners, python3 fallback in package-windows.sh
- Windows portability for Link.cpp and ResourceManifest.cpp
- Guard windows.h include against min/max macro collision
- Windows portability for buoy-lsp Transport and DiagnosticsPublisher
- Use Set-Location instead of git -C for git lfs pull
- Pass explicit -C path to git lfs pull under pwsh
- Use pwsh not bash for git lfs pull on Windows
- Force git lfs pull after checkout to guarantee real content
- Fetch real Git LFS content in checkout, not pointer stubs
- Define S_ISDIR on Windows for TlsC.cpp
- Make Program explicitly move-only for MSVC
- MSVC compile errors in Parser.cpp, RegexC.cpp, TlsC.cpp
- Pin PATH to MSVC tools dir so link resolves to the real linker
- Use npm ci instead of npm install for the VSCode extension build
- Prefer Strawberry Perl over Git Bash bundled perl explicitly
- Force --libdir=lib for native OpenSSL builds
- Match Linux ARM64 runner's actual label casing (Linux/ARM64)
- Force clang explicitly when building LLVM on Linux
- Match Linux x86_64 runner's actual label (X64, not x86_64)
- Stop stripping LLVM's bin/ from the prebuilt tarball
- Recognize Windows .dll/.lib naming in vendor-pcre2.sh
- Match minizip-ng's actual static lib name on Windows
- Verify SHA256 checksums for downloaded cmake/ninja binaries
- Convert paths for cl.exe/lib.exe via cygpath, not just exclude flags
- Replace choco with portable cmake/ninja downloads on Windows CI
- Prevent Git Bash from mangling MSVC /flag args in vendor-sqlite.sh
- Surface gh release download errors instead of swallowing them
- Fall back to python instead of hardcoded python3 in workflows
- Make vendor-sqlite.sh portable across macOS/Linux/Windows


---

# v0.34.0

## New Features
- Chained array indexing over nested arrays (theArray(i)(j))
- Add Locale.ParseNumber for locale-aware string-to-number conversion
- Add Array.Shuffle in-place shuffle method

## Bug Fixes
- DateTime.MillisFrom1970/SecondsFrom1970 lose all sub-second precision
- Linux native .so links leak build-machine's absolute cache path into DT_NEEDED
- Dedupe vendored license files in packaging scripts
- Claim ownership of array-typed elements in ARC retain/release loops
- Flush stdio on Linux exit by calling libc exit() from crt0
- Claim ownership of array-typed Structure/Record fields in ARC
- Claim array-typed collection ownership in For Each codegen
- Claim ownership of array-typed elements in IndexAssign/Append/Insert


---

# v0.33.0

## New Features
- Add System.Microseconds() monotonic elapsed-time counter
- Add Inline function/method modifier for LLVM alwaysinline

## Bug Fixes
- Claim ownership of array-typed elements in array literal codegen
- Wrap buoy --help output to 75 columns


---

# v0.33.0

## New Features
- Add System.Microseconds() monotonic elapsed-time counter
- Add Inline function/method modifier for LLVM alwaysinline

## Bug Fixes
- Claim ownership of array-typed elements in array literal codegen
- Wrap buoy --help output to 75 columns


---

# v0.32.0

## New Features
- Add XSLT support to xml package (Xalan-C++-backed)
- Add streaming XMLReader; rename Xml-prefixed classes to XML
- Add XSD schema validation to xml package
- Add real XPath support to xml package (Xalan-C++-backed)
- AI coding kit — buoy ai init, MCP docs search, VSCode setup command
- Add xml package (Xerces-C++-backed DOM core)
- Suggest event names after Handle in completion
- Locale-aware Number/Currency formatting via Locale.FormatNumber/FormatCurrency
- Flesh out FileSystemItem + FileSystemDrive / System drive enumeration
- Locale-aware DateTime.ToString
- Wrap zip package's raw minizip-ng FFI in ZipReader/ZipWriter
- Add System.Folders (SpecialFolder) known-folder resolver
- Add inline If(condition, trueValue, falseValue) conditional expression
- Add cross-platform DateTimePicker control
- Add UDP broadcast and multicast support to UDPSocket
- Build crypto+buoy_tls for Windows/Linux with OpenSSL, all 6 targets done
- Rewire CMake/build scripts for OpenSSL, fix two KDF bugs found in testing
- Port TLS shim (runtime/tls/TlsC.cpp) from Botan to OpenSSL
- Port crypto package native shim from Botan to OpenSSL
- Extend postgres package to Linux and Windows (all 6 triples)
- Add postgres package (PostgreSQL backend for Database abstract class)

## Bug Fixes
- Bump brace-expansion to 1.1.16/2.1.2/5.0.7 (alerts #15, #16, #17)
- Bump js-yaml to 4.3.0 (alert #14)
- Bump markdown-it to 14.3.0 (alert #5)
- Bump linkify-it to 5.0.2 (alert #13)
- Bump undici to 7.28.0 (alerts #6, #7, #8, #9, #10, #11, #12)
- Bump tmp to 0.2.7 (alert #3)
- Bump form-data to 4.0.6 (alert #4)
- Bump serialize-javascript to 7.0.7 (alerts #1, #2)
- Ship only cleaned learning chapters (docs/learning_buoy), not docs/learning
- Deliver fluenticons as a single compressed .buipkg instead of ~6,238 loose files
- Default long-form local Array Of T to empty array (urgent segfault)
- Regression guard + close-loop for macOS window close-box crash (buoy-releases#39)
- Create Windows named pipe synchronously in ServerSocket.Listen() to close Mode.IPC race
- Harden DateTimePicker Linux backend against null-deref and floating-ref misuse
- Call ExitProcess explicitly on Windows so Winsock worker threads can't block exit
- Extend Linux libc/libpthread stubs for OpenSSL's fuller libc surface
- Disable OpenSSL async/QUIC, fix Linux atexit versioning, extend macOS libc stubs


---

# v0.32.0

## New Features
- Add XSLT support to xml package (Xalan-C++-backed)
- Add streaming XMLReader; rename Xml-prefixed classes to XML
- Add XSD schema validation to xml package
- Add real XPath support to xml package (Xalan-C++-backed)
- AI coding kit — buoy ai init, MCP docs search, VSCode setup command
- Add xml package (Xerces-C++-backed DOM core)
- Suggest event names after Handle in completion
- Locale-aware Number/Currency formatting via Locale.FormatNumber/FormatCurrency
- Flesh out FileSystemItem + FileSystemDrive / System drive enumeration
- Locale-aware DateTime.ToString
- Wrap zip package's raw minizip-ng FFI in ZipReader/ZipWriter
- Add System.Folders (SpecialFolder) known-folder resolver
- Add inline If(condition, trueValue, falseValue) conditional expression
- Add cross-platform DateTimePicker control
- Add UDP broadcast and multicast support to UDPSocket
- Build crypto+buoy_tls for Windows/Linux with OpenSSL, all 6 targets done
- Rewire CMake/build scripts for OpenSSL, fix two KDF bugs found in testing
- Port TLS shim (runtime/tls/TlsC.cpp) from Botan to OpenSSL
- Port crypto package native shim from Botan to OpenSSL
- Extend postgres package to Linux and Windows (all 6 triples)
- Add postgres package (PostgreSQL backend for Database abstract class)

## Bug Fixes
- Bump brace-expansion to 1.1.16/2.1.2/5.0.7 (alerts #15, #16, #17)
- Bump js-yaml to 4.3.0 (alert #14)
- Bump markdown-it to 14.3.0 (alert #5)
- Bump linkify-it to 5.0.2 (alert #13)
- Bump undici to 7.28.0 (alerts #6, #7, #8, #9, #10, #11, #12)
- Bump tmp to 0.2.7 (alert #3)
- Bump form-data to 4.0.6 (alert #4)
- Bump serialize-javascript to 7.0.7 (alerts #1, #2)
- Ship only cleaned learning chapters (docs/learning_buoy), not docs/learning
- Deliver fluenticons as a single compressed .buipkg instead of ~6,238 loose files
- Default long-form local Array Of T to empty array (urgent segfault)
- Regression guard + close-loop for macOS window close-box crash (buoy-releases#39)
- Create Windows named pipe synchronously in ServerSocket.Listen() to close Mode.IPC race
- Harden DateTimePicker Linux backend against null-deref and floating-ref misuse
- Call ExitProcess explicitly on Windows so Winsock worker threads can't block exit
- Extend Linux libc/libpthread stubs for OpenSSL's fuller libc surface
- Disable OpenSSL async/QUIC, fix Linux atexit versioning, extend macOS libc stubs


---

# v0.31.0

## New Features
- Make the raw sqlite3 FFI surface private to the database package
- Generic-method robustness for the Database base class + test migration
- Add Call statement keyword
- Rewrite database package as SQLiteDatabase backend of stdlib base
- Overload sets for generic instance methods
- Backend-agnostic abstract Database base layer in stdlib
- Per-project VSCode build config for multi-target Buoy compiles

## Bug Fixes
- Don't let an Abstract method's optional End consume the enclosing End Class
- Make layout editor control borders visible in dark themes
- Percent-decode file:// URIs in the LSP's workspace/import resolution
- Stop a stray .buoy/ dir from poisoning project-root detection
- Relocate and package Linux crt0.o for installed toolchains
- Defer window close callback off AppKit's synchronous teardown to stop close-button crash
- Copy Windows runtime DLLs correctly when -o has no directory component
- Alphabetize the control lists in the layout editor
- Reject Optional =/<> comparison in Sema instead of crashing codegen
- Stage the actual regression test and closure notes for the RSP bug
- Default uninitialized Array Of T property to empty array


---

# v0.30.0

## New Features
- Add hotkey legend to layout editor palette
- Disambiguate layout editor between multiple Window/View blocks in one file
- Resizable window, multi-select drag, and working snap in layout editor
- Embed Info.plist in the buoy binary and console-mode macOS executables
- Add declarative View blocks for reusable composite controls
- Add @DatabaseRecord attribute for compile-time SQLite marshaling

## Bug Fixes
- Flush temps in dotted-receiver Assigns-call branch to fix codegen crash
- Stop shipping dead empty examples/ folder in packaged releases
- Index Window/View/Control/Constraints as indent-openers in the formatter
- Correctly update all governing anchors in constraint drag steady-state
- Only run the solver when resizing the window/view


---

# v0.29.0


---

# v0.28.0

## New Features
- Add Variant tagged-union value box package (Xojo-conversion shim)
- Convert DateTime, TimeZone, and TimeInterval to real classes
- Add buoy --list-deprecations to catalog @Deprecated declarations
- Add Urgent severity tier for crash/segfault/hang bugs

## Bug Fixes
- Resolve record-literal payloads inside Some(...)/Ok(...)/Err(...)
- Close crypto package native/-source bug report, add regression guard
- Reject Array.RemoveValue/IndexOf/LastIndexOf/Contains value-type mismatches
- Build buoy_picture.dll's SVG path via native llvm-mingw to fix Windows entrypoint failure
- Statically link libucrt.a for Windows runtime DLL C99 stdio calls
- Resolve receiver.PropertyName(index) as array-property indexing, not a method call
- Reject out-of-range float literals instead of crashing the lexer
- Reject out-of-range integer literals instead of crashing the lexer
- Upload companion runtime DLLs/.so for remote CTest lanes
- Reject Weak on Shared Property/field instead of segfaulting at runtime
- Guard GTK4 popups/dialogs against unrealized/uninitialized toplevel
- Windows CRT fd-table functions work without special init; add missing stub exports
- Add missing loop-idiom-recognize libc symbols to Darwin libSystem.tbd stubs
- Load full certificate chain in server-side TLS
- Xor on Integer operands emitted invalid LLVM IR
- Load full certificate chain in server-side TLS


---

# v0.27.1

## Bug Fixes
- Package loader no longer has trouble with certain packages


---

# v0.27.0

## New Features
- Add TimeZone.New(offsetSeconds) fixed UTC-offset constructor

## Bug Fixes
- Intel macOS llvm vendoring fixed so debugger should work again
- Add missing vscode plugin items
- Support ByRef parameters on non-Declare functions, methods, and generics
- A `Structure` with a reference-type field no longer crashes at runtime when returned from a function
- Windows are now retained until they close so they don't get destroyed when the initialization variable goes out of scope
- Only search for a static libzstd when LLVM actually links zstd
- Class property defaults show correctly in the debugger


---

# v0.26.0

## New Features
- DateTime now as an initiator that takes Year, Month, Day, Hour, Minute, Second, Timezone
- Add trailing-default component-form DateTime.New constructor
- Add Break debugger-trap statement
- Project-level app resource manifest (app_resources.json) (#42)
- Method local declares
- Add HTTPServer package

## Bug Fixes
- Debugger now shows values at the top level instead of the internal LLVM id
- Add TimeZone.OffsetSeconds, make UTC offset computation real (#44)
- Allow paren-less calls for zero-argument methods (#43)
- Plist override fixes
- Fold package declares/ into modules/ for real Private scoping (#41)
- Grammar fix on Xojo plugin packaging demo
- Package extraction bookkeeping was per-entry-file instead of shared (#39)


---

# v0.25.0

## New Features
- Add TLS 1.2/1.3 support to TCPSocket and ServerSocket (#38)
- Source Fluent UI System Icons as a cross-platform icon library (#36)
- Add TextEncoding support
- Add regex package (typed Regex/Match/RegexError), fix core regex cross-linking
- Add per-user global package directory (#35)

## Bug Fixes
- TCPSocket compiles again for Windows targets
- Linux ARM64 now has text-encoding symbols

## Changes
- Cryptoprims package has been renamed crypto


---

# v0.24.0

## New Features
- Merge a user-supplied Info.plist into .app bundle output (#34)
- Add Targeted Constants and Localizations
- Add SerialPort/SerialConnection serial-port I/O (serialio package) (#33)
- Add System.Locale — OS-native number/date/currency formatting (#32)
- Add System.GetNetworkInterfaces() and NetworkInterface


---

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
