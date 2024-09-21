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
### Specifying cryptographic key agreement using FCS_CKM.5
In E.3.2.2 of CC:2022 Part 2, "cryptographic key agreement" is mentioned as an operation of FCS_COP.1.1.
Taking into account that FCS_COP.1 has dependency of FCS_CKM.4 "cryptographic key destruction", as seen in 10.2 of CC v3.1 release 5, 
PP or ST authors specify "cryptographic key agreement" using FCS_COP.1.1, destruction of the following keys would be required.
- destruction of a key input to the TOE security function (TSF) enforcing the SFR.
- destruction of agreed key or derived keying material output from the TSF enforcing the SFR.

However in 10.3.5 of CC:2022 Part 2, the dependency of FCS_CKM.4 or FCS_CKM.6 is not described.
Therefore PP, ST authors, evaluators, and/or certifiers may fail to recognize the need of cryptographic key destruction.
This can result in a security hole in TOEs.

Here cryptographic key derivation will normally require input key or secret information, and output derived key or derived keying material.
FCS_CKM.5 is purposely designed to address these two types of keys. 
So FCS_CKM.5 can be used to specify cryptographic key agreement with less effort.
Also FCS_CKM.5 has dependency of FCS_CKM.6 as seen in 10.2.9 of CC:2022 Part 2.
In addition, as pointed out in E.2.2 and E.2.6.1 of CC:2022 Part 2, cryptographic key destruction is required not only for input key, but also for output derived key within the context of FCS_CKM.5.

Therefore, specifying cryptographic key agreement using rather FCS_CKM.5 than FCS_COP.1 will be considered as a sound approach, by taking into account the FCS_CKM.5, its dependecy and its supporting text.

# CC:2022 Part 3
## ALC_TAT.2
To be documented
