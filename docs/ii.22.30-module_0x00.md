## II.22.30 Module: 0x00

The _Module_ table has the following columns:

 * _Generation_ (a 2-byte value, reserved, shall be zero)

 * _Name_ (an index into the String heap)

 * _Mvid_ (an index into the Guid heap; simply a Guid used to distinguish between two versions of the same module)

 * _EncId_ (an index into the Guid heap; reserved, shall be zero)

 * _EncBaseId_ (an index into the Guid heap; reserved, shall be zero)

The Mvid column shall index a unique GUID in the GUID heap (§[II.24.2.5](ii.24.2.5-guid-heap.md)) that identifies this instance of the module. The _Mvid_ can be ignored on read by conforming implementations of the CLI. The _Mvid_ should be newly generated for every module, using the algorithm specified in ISO/IEC 11578:1996 (Annex A) or another compatible algorithm.

_[Note:_ The term GUID stands for Globally Unique IDentifier, a 16-byte long number typically displayed using its hexadecimal encoding.  A GUID can be generated by several well-known algorithms including those used for UUIDs (Universally Unique IDentifiers) in RPC and CORBA, as well as CLSIDs, GUIDs, and IIDs in COM. _end note]_

_[Rationale:_ While the VES itself makes no use of the _Mvid_, other tools (such as debuggers, which are outside the scope of this standard) rely on the fact that the _Mvid_ almost always differs from one module to another. _end rationale]_

The _Generation_, _EncId_, and _EncBaseId_ columns can be written as zero, and can be ignored by conforming implementations of the CLI.

The rows in the _Module_ table result from **.module** directives in the Assembly (§[II.6.4](ii.6.4-declaring-modules.md)).

> _This contains informative text only._

 1. The _Module_ table shall contain one and only one row \[ERROR\]

 2. _Name_ shall index a non-empty string. This string should match exactly any corresponding _ModuleRef_._Name_ string that resolves to this module. \[ERROR\]

 3. _Mvid_ shall index a non-null GUID in the Guid heap \[ERROR\]

> _End informative text._
