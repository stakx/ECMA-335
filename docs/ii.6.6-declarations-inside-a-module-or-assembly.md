## II.6.6 Declarations inside a module or assembly

Declarations inside a module or assembly are specified by the following grammar. More information on each option can be found in the corresponding clause or subclause.

 | _Decl_ ::= | Clause
 | ---- | ----
 | \| `.class` _ClassHeader_ `'{'` _ClassMember_* `'}'` | §[II.10](ii.10-defining-types.md)
 | \| `.custom` _CustomDecl_ | §[II.21](ii.21-custom-attributes.md)
 | \| `.data` _DataDecl_ | §[II.16.3.1](ii.16.3.1-data-declaration.md)
 | \| `.field` _FieldDecl_ | §[II.16](ii.16-defining-and-referencing-fields.md)
 | \| `.method` _MethodHeader_ `'{'` _MethodBodyItem_* `'}'` | §[II.15](ii.15-defining-referencing-and-calling-methods.md)
 | \| _ExternSourceDecl_ | §[II.5.7](ii.5.7-source-line-information.md)
 | \| _SecurityDecl_ | §[II.20](ii.20-declarative-security.md) 
 | \| &hellip;
