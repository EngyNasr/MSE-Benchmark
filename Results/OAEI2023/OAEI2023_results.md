# Results of evaluation for the MSE track within OAEI 2023 
This is the second time the MSE track participates in an OAEI campaign. We are proud to be part of it and would like to thank everyone who has supported us along the way!

## Evaluation modalities
We performed the evaluation using the MSE benchmark v1.2 and the MELT platform on a laptop with Intel i7-1260P at 2.10 GHz, 16 GB RAM and Windows 11. Every participating system was executed in its standard setting and we compare precision, recall and F-measure as well as the computation time. No background knowledge was used for evaluation. 

## Participating systems
This year four systems registered on this track, each of which was used for evaluation with the three test cases of the MSE track. AMD produced errors and an empty alignment file, so results are only available for three of the matchers:
- LogMap
- LogMapLite
- Matcha
<!-- AMD -->

## Generated alignments
We have collected all generated alignments and make them available in a zip-file via the following link. These alignments are the raw results that the following report is based on.

[>>> Download alignments here](https://github.com/EngyNasr/MSE-Benchmark/raw/main/Results/OAEI2023/oaei2023-mse_alignments.zip)

## Results

The following results were obtained for the participating matching systems in the OAEI campaign 2022 within the MSE track.

### First Test Case

| System   | Correspondences | Precision | Recall | F1-Measure | Time [s] |
|:--------:|:--------------------:|:---------:|:------:|:----------:|:--------:|
| LogMap   |            1         |   1.000   | 0.043  | 0.083      |    20     |
| LogMapLite |         5         |   0.400   | 0.087  | 0.143      |   53     |
| Matcha   |            11         |   0.273   | 0.130  | 0.176      |   28     |
<!--| AMD	   |                    |      |   |       |        | -->
 
The first test case evaluates matching systems regarding their capability to find "equal" (=), "superclass" (>) and "subclass" (<) correspondences between the mid-sized MatOnto and the small-sized (since reduced) MaterialInformation ontology. None of the evaluated systems finds correspondences other than "equal" (=). All evaluated systems compute the alignment in less than a minute. In comparison the results of 2022 Matcha performs the matching task alsmost as quick as LogMap, who stood out for its very fast calculation time. Apart from the runtime, the results for LogMap and LogMapLite don't change in comparison to the evaluation in 2022. LogMap presents a maximum precision value of 1.0, however since only one correspondence was found by LogMap, the recall and hence the F1-measure is low (0.083). In direct comparison to LogMap, LogMapLite calculates the alignment in around half the time and achieves much lower precision (0.4) but due to a greater amount of correctly found correspondences the F1-measure is better - although still low with 0.143. Matcha finds 8 incorrect crorrespondences thus is the worst performing participant in terms of precision in the first test case. Investigating the reason for this bad precision, Matcha appears to match classes with object propertiers, e.g. "Temperature" =" hasTemperature" as in 2022 already. Since the recall is the best of the partcipating systems, Matcha turns out to be the best performing system based on its F1-measure. 

### Second Test Case

| System   | Correspondences | Precision | Recall | F1-Measure | Time [s] |
|:--------:|:--------------------:|:---------:|:------:|:----------:|:--------:|
| LogMap   |            67        |   0.881   | 0.195  | 0.320      |    06     |            
| LogMapLite |         67        |   0.851   | 0.189  | 0.309      |   77     |
| Matcha   |            87         |   0.756   | 0.219  | 0.339      |   15     |
<!-- | AMD   |                   |      |   |       |       | -->

The second test case evaluates the matching systems to find correspondences between the large-sized MaterialInformation and the mid-sized BFO-based MatOnto. Suprisingly, LogMap performs the matching task significantly quicker than in the first test case and stands out for its very fast computation time of only 6s at a high precision of 0.881. Apart from the runtime, the results for LogMap and LogMapLite don't change in comparison to the evaluation in 2022. Since LogMap found only 59 correct correspondences out of the 302 reference correspondences, the recall is rather low but the F1-measure is still the highest of the tested systems. LogMapLite is significantly slower than LogMap but finds the same amount of correspondences with 2 additional false positives, so it achieves a slightly lower overall F1-measure than LogMap. Matcha finds 6 wrong correspondences where classes are matched to object properties as in the first test case. Matche presents the worst precision in this test case but the best recall. Based on its F1-measure, Matcha performs slightly better than the other systems in this test case. 


### Third Test Case
| System   | Correspondences | Precision | Recall | F1-Measure | Time [s] |
|:--------:|:--------------------:|:---------:|:------:|:----------:|:--------:|
| LogMap   |            56        |   0.946   | 0.841  | 0.891      | 25       |
| LogMapLite |         56        |   0.911   | 0.810  | 0.857      | 53       |
| Matcha   |            59         |   0.949   | 0.889  | 0.918      | 23       |
<!-- | AMD   |                     |      |   |       |       | -->

The third test case evaluates matching systems to find correspondences between the large-sized MaterialInformation and the mid-sized EMMO. All evaluated systems compute the alignments in under one minutes. Apart from the runtime, the results for LogMap and LogMapLite don't change in comparison to the evaluation in 2022. All of the systems present high precision values. LogMap computes 3 false positives, LogMapLite computes 5 false positives but Matcha 3 as well but has with 56 the highest number of true positives which results in the best precision of the testes systems. Since it has the highest number of correctly found correspondences, the recall and also the F1-measure is the highest of the evaluated systems in the third test case at the fastest computation time. 

## Conclusions
Unfortunately, none of the evaluated matcher finds all reference correspondences correctly. 

In comparison to the evaluation of 2022, LogMap and LogMapLite are not the significantly best performing systems when it comes to precision. Matcha improved in comparison to the 2022 evaluation and is in all test cases the systems that performs best in terms of F1-measure at comparable computation times to the fast LogMap matcher. Based on the 2023 evaluation, Matcha along with LogMap is recommended for mse applications when high precision is required with reasonable recall performance. 

Since the creation of this MSE benchmark, a large amount of new MSE ontologies have been developed and utilized in various applications. In contrast to the early development stages of this benchmark, those ontologies are now easily accessible on the new [Matportal](https://matportal.org/). In the future, the mse benchmark should be updated with the currently most used top and mid-level MSE ontologies, which include the [BWMD-mid](https://matportal.org/ontologies/BWMD-MID), the [MSEO](https://matportal.org/ontologies/MSEO), the [PMDco](https://github.com/materialdigital/core-ontology), the [prov-o](https://www.ebi.ac.uk/ols/ontologies/prov) and [IOF-mat](https://industrialontologies.org/working-groups/the-material-science-and-engineering-mse-working-group-wg/). In the [OntoCommons project](https://ontocommons.eu/) alignments of frequently used ontologies of the mse application area are produced. A collaboration with relevant project members was already established to further improve the MSE benchmark based on the project results. Apart from also considering frequently used domain and application ontologies like the [BWMD-domain](https://gitlab.cc-asp.fraunhofer.de/EMI_datamanagement/bwmd_ontology/-/raw/master/BWMD_domain.owl), the [LPBFO](https://matportal.org/ontologies/LPBFO) and others, also multi-ontology matching, knowledge graph mathing e.g. using the [AluTrace data](https://github.com/Mat-O-Lab/AluTraceProject) and the usage of background knowledge should be considered in future OAEI campaigns. 

## Contact
This track is organized by Engy Nasr and evaluation was performed by Martin Huschka. If anything is unclear, if you have any comments on the MSE track or would like to contribute, feel free to write an email to huschka [at] emi [.] fraunhofer [.] de.




