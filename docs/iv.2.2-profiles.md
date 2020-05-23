## IV.2.2 Profiles

A Profile is simply a set of Libraries, grouped together to form a consistent whole that provides a fixed level of functionality. A conforming implementation of the CLI shall specify the Profile it implements, as well as any additional Libraries that it provides. The Kernel Profile (§[IV.3.1](iv.3.1-the-kernel-profile.md)) shall be included in all conforming implementations of the CLI. Thus, all Libraries and CLI features that are part of the Kernel Profile are available in all conforming implementations. This minimal feature set is described in §[IV.4](iv.4-kernel-profile-feature-requirements.md).

_[Rationale:_ The rules for combining Libraries together are complex, since each Library can add members to types defined in other libraries. By standardizing a small number of Profiles the interaction of the Libraries that are part of each Profile are specified completely. A Profile provides a consistent target for vendors of devices, compilers, tools, and applications. Each Profile specifies a trade-off of CLI feature and implementation complexity against resource constraints. By defining a very small number of Profiles, market for each Profile is increased, making each a desirable target for a class of applications across a wide range of implementations and tool sets. _end rationale]_
