# parallelism

## Description of the dataset ``ted-metrics``
From the PDTB-3, we excluded:
- relations involving split connectives like "on the one hand ... on the other
hand ...",
- relations displaying one or two split text-spans,
- relations involving an overlap of the two text-spans (or one text-span containing the other),
- relations whose text-spans were made of two or more sentence,
- relation involving an act of speech,
- AltLex, AltlexC, Hypophora, EntRel and NoRel relations.

We end up with 39271 relations, available in the pandas DataFrame ``ted-metrics``, whose columns are:
- INDEX: an primary key for each discourse relation
- RelationType: Explicit or Implicit in PTDB-3's terminology
- Conn: the connective
- Provenance: refer to PDTB-3 manual
- Layout: ``ORDERED`` (Arg1 and then Arg2) or ``SWITCHED`` (Arg2 and then Arg1)
- Arg1 & Arg2: textspans
- 1Rel, 2Rel, 3Rel: PDTB-3 three-level taxonomy of discourse relations
- NumTokensArgX: Number of tokens in the textspan X
- NxGX: NetworkX graph of the constituency tree of textspan X
- SizeX: number of nodes in the simplified (cf ``.ipynb`` files for the definition of simplified) constituency tree of textspan X
- TED: Tree Edit Distance value
- MatchSeq: mapping sequence between the trees at format [ (1,1), (2,3), (3,None) ...]
- matched: number of mapped nodes in MatchSeq i.e. tuples without _None_
- deleted: number of deleted nodes i.e. tuples with _None_ on the right side
- inserted: number of inserted nodes i.e. tuples with _None_ on the left side

The two following columns refer to Sanders et al. 2018 terminology:
- Polarity: ``pos`` (positive) or ``neg`` (negative)
- Operation: ``add`` (additive) or ``cau`` (causal) or ``add/cau`` (in case a manual review is required)

## Desciption of the 

 
