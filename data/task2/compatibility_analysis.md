## MSA Omega Cluster

Using [Clustal Omega](https://www.ebi.ac.uk/jdispatcher/msa/clustalo) to align sequences

1. 7QTL_C is fully aligned with the Pb2 protein sequence.
2. 8H69_C is partially aligned with the Pb2 protein sequence.
3. 8Y7M_C is also fully aligned with the Pb2 protein sequence, but we can see that 8Y7M_C has extra amino acids at the end.

## Notes

In vmd, tk console, we use the code below to export only chain C:

```tk
set sel [atomselect top "chain C"]
$sel writepdb filtered_C.pdb
```

---

