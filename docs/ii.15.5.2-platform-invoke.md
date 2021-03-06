## II.15.5.2 Platform invoke

Methods defined in native code can be invoked using the *platform invoke* (also know as PInvoke or p/invoke) functionality of the CLI. Platform invoke will switch from managed to unmanaged state and back, and also handle necessary data marshalling. Methods that need to be called using PInvoke are marked as **pinvokeimpl**. In addition, the methods shall have the implementation attributes **native** and **unmanaged** (§[II.15.4.2.4](ii.15.4.2.4-method-attributes.md)).

 | _MethAttr_ ::= | Description | Clause
 | ---- | ---- | ----
 | `pinvokeimpl` `'('` _QSTRING_ [ `as` _QSTRING_ ] _PinvAttr_* `')'` | Implemented in native code
 | \| &hellip; | §[II.15.4.1.5](ii.15.4.1.5-the-param-type_directive.md)

The first quoted string is a platform-specific description indicating where the implementation of the method is located (for example, on Microsoft Windows&trade; this would be the name of the DLL that implements the method). The second (optional) string is the name of the method as it exists on that platform, since the platform can use name-mangling rules that force the name as it appears to a managed program to differ from the name as seen in the native implementation (this is common, for example, when the native code is generated by a C++ compiler).

Only static methods, defined at global scope (i.e., outside of any type), can be marked **pinvokeimpl**. A method declared with pinvokeimpl shall not have a body specified as part of the definition.

 | _PinvAttr_ ::= | Description (platform-specific, suggestion only)
 | ---- | ----
 | `ansi` | ANSI character set.
 | \| `autochar` | Determine character set automatically.
 | \| `cdecl` | Standard C style call
 | \| `fastcall` | C style fastcall.
 | \| `stdcall` | Standard C++ style call.
 | \| `thiscall` | The method accepts an implicit *this* pointer.
 | \| `unicode` | Unicode character set.
 | \| `platformapi` | Use call convention appropriate to target platform.

The attributes **ansi**, **autochar**, and **unicode** are mutually exclusive. They govern how strings will be marshaled for calls to this method: **ansi** indicates that the native code will receive (and possibly return) a platform-specific representation that corresponds to a string encoded in the ANSI character set (typically this would match the representation of a C or C++ string constant); **autochar** indicates a platform-specific representation that is "natural" for the underlying platform; and **unicode** indicates a platform-specific representation that corresponds to a string encoded for use with Unicode methods on that platform.

The attributes **cdecl**, **fastcall**, **stdcall**, **thiscall**, and **platformapi** are mutually exclusive. They are platform-specific and specify the calling conventions for native code.

_[Example:_ The following shows the declaration of the method `MessageBeep` located in the Microsoft Windows&trade; DLL `user32.dll`:

 ```ilasm
 .method public static pinvokeimpl("user32.dll" stdcall) int8
       MessageBeep(unsigned int32) native unmanaged {}
 ```

_end example]_
