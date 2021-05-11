This file describes MoBa 98K batch, located on TSD p697 project.

### Plink bfile location
```
/cluster/projects/p697/genotype/MoBa_98k_post-imputationQC
```
The file hard-calls information for``N=86890`` individuals and ``M=5003746`` markers.

A copy of the bim, fam and covariate files are also located at 
```
/tsd/p697/data/durable/genotype/MoBa_98k_post-imputationQC/
```

## Dosage data location

Dosage data in ``.bgen`` format is located here:
```
/cluster/projects/p697/genotype/MoBa_98k_post-imputationQC/bgen
/tsd/p697/data/durable/genotype/MoBa_98k_post-imputationQC/bgen
```
Corresponding .sample file has invalid FID column, simply a copy of IID column.
If you use information on family structure, please use the data from ``.fam`` files.

### Covariate file
```98k-ec-eur-fin-batch-basic-qc-cov.txt``` 
hopefully contains a lot of the relevant infromation needed to link the genotypes to phenotypes,
and to run analyses witht he relevant covariates, including principal components.
(information on principal components is also available in a separate file ``98k-ec-eur-fin-projections.txt``).

NB: There are significant genotyping plate, genotyping batch, and imputation batch effects.
Therefore, we highly recommend including these as covarates in all analyses.
The ``ID_2445`` column contains the ``F_ID_2445`` for fathers, 
the ``M_ID_2445`` for mothers,
and the ``PREG_ID_BARN_NR`` for children
(created using the command ``paste(child$PREG_ID, child$BARN_NR, sep="_")`` in R).

The FID and IID columns match the FID (column 1) and IID (column 2) of the plink fam file.

Any column with ``_num`` at the end of the column name contains a numeric version of the column with the same name
(e.g., ``genotyping_center`` and ``genotyping_center_num``).

There are some MZ twin pairs and across generation first degree relationships.
Basic information about these relationships can be found in 
``/tsd/p697/data/durable/projects/moba_qc_imputation/resources`` folder.
Files: ``MZ_twin_pairs_identified_by_KING.txt`` and ``Within_generation_PO_across_generation_S_identified_by_KING.txt``.
