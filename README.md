# Selected topics in Common Criteria (CC) 2022

This note mainly describes the following:
- issues that have been raised in CC v3.1 and how they are addressed in CC:2022.

The reader of this note is assumed to be a person who understands CC and tries to solve security issues by making use of CC.

It should be noted that this note is neither an interpretation of CC, nor to support CC fundamentalism.

# CC:2022 Part 1
## "Referring to other standards" only in TSS is no longer accepted.

The title of A.13 of CC v3.1 release 5 Part 1 is "Referring to other standards in a ST".
This subclause describes following three options of referring to other standards in a Security Target (ST).
- Option a) "As an organisational security policy (or part of it)"
- Option b) "As a technical standard (for example a cryptographic standard) used in a refinement of an SFR"
- Option c) "As a technical standard (for example a cryptographic standard) mentioned in the TOE summary specification"

The first two options are readily understandable and still kept in CC:2022 Part 1 (see B.4 of CC:2022 Part 1). 

The last option c) was interpreted that, this allowed vendors to define a SFR without referring technical standards (e.g. cryptographic standards) provided that those standards are mentioned in the TOE summary specification (TSS).

Vendors could use this option to hide technical specification in SFRs for several reasons (e.g. proprietary cryptographic specification).

From Security Target (ST) readers' viewpoints, it was required to read TOE summary specification carefully so that what technical standards, especially cryptographic standards, are applied in an TOE, because the TOE vendor may have purposely hid technical standards in SFRs.

It should be also noted that vendors can sanitize STs and publish their ST-lite version. 
Through the sanitization process, vendors may have sanitized mentioning technical standards in the ST-lite version. In this case, ST readers no longer get to know what technical standards are applied.

Here, in D.5 and B.4 of CC:2022 Part 1, the corresponding option c) is no longer described. 
From PP authors' viewpoints, applying unintended technical standards (e.g. cryptographic standards) can be avoided at the stage of TSS by removing option c).

Therefore, "referring to other standards" only in TSS without explicitly referring in a SFR is no longer accepted.

# CC:2022 Part 2
## FCS_CKM.5
To be documented

# CC:2022 Part 3
## ALC_TAT.2
To be documented
