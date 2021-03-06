## I.8.5.3.1 Visibility of types

Only type names, not member names, have controlled visibility. Type names fall into one of the following three categories

 * **Exported** from the assembly in which they are defined. While a type can be marked to *allow* it to be exported from the assembly, it is the configuration of the assembly that decides whether the type name *is* made available.

 * **Not exported** outside the assembly in which they are defined.

 * Nested within another type. In this case, the type itself has the visibility of the type inside of which it is nested (its **enclosing type**). See §[I.8.5.3.4](i.8.5.3.4-nested-types.md).

A top-level named type is *exported* if and only if it has public visibility. A type generated by a type definer is exported if and only if it is made from exported types.

A type generated by a type definer is visible if all types from which it was generated are visible.
