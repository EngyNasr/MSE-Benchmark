# Results of Evaluation for the MSE track within OAEI 2022 
This is the first year the MSE track participates in a OAEI campaign. We are proud to be part of it and would like to thank everyone who has supported us along the way!

## Evaluation modalities
We performed the evaluation using the MELT platform on a Windows 10 system with 16 GB RAM. Every participating system was executed in its standard setting and we compare precision, recall and F-measure as well as the computation time. 

## Participating systems
This year five systems registered on this track, each of which was used for evaluation with the three test cases of the MSE benchmark. AMD produced errors and an empty alignment file, so results are only available for four of the matchers:
- A-LIOn
- LogMap
- LogMapLite
- Matcha

## Generated alignments
We have collected all generated alignments and make them available in a zip-file via the following link. These alignments are the raw results that the following report is based on.

[>>> Download alignments here](https://github.com/EngyNasr/MSE-Benchmark/raw/main/Results/OAEI2022/oaei2022-mse_alignments.zip)

## Results

The following results were obtained for the participating matching systems in the OAEI campaign 2022 within the MSE track.

### First Test Case

| System   | Correspondences | Precision | Recall | F1-Measure | Time [s] |
|:--------:|:--------------------:|:---------:|:------:|:----------:|:--------:|
| A-LIOn   |           23         |   0.130   | 0.130  | 0.130      |   38     |
| LogMap   |            1         |   1.000   | 0.043  | 0.083      |    9     |
| LogMapLight |         5         |   0.400   | 0.087  | 0.143      |   27     |
| Matcha   |            4         |   0.000   | 0.000  | 0.000      |   22     |

The first test case evaluates matching systems regarding their capability to find "equal" (=), "superclass" (>) and "subclass" (<) correspondences between the mid-sized MatOnto and the small-sized (since reduced) MaterialInformation ontology. None of the evaluated systems finds correspondences other than "equal" (=). All evaluated systems compute the alignment in less than a minute. LogMap stands out with its very fast calculation time of 9s and the maximum precision of 1.0. However, since only one correspondence was found by LogMap, the recall and hence the F1-measure is low (0.083). In direct comparison, LogMapLight calculates the alignment in three times the time and achieves much lower precision (0.4) but due to a greater amount of correctly found correspondences the F1-measure is the best of the tested systems in the first test case - although still low with 0.142. A-LIOn finds the highest number of correspondences, but of those 23 found correspondences 20 are false positives which results in the second best F1-measure at the slowest pace. Matcha finds 4 incorrect crorrespondences thusthe  is worst participant in the MSE test case one. Investigating the reason for the bad result, Matcha appears to match classes with object propertiers, e.g. "Temperature" =" hasTemperature".

### Second Test Case

| System   | Correspondences | Precision | Recall | F1-Measure | Time [s] |
|:--------:|:--------------------:|:---------:|:------:|:----------:|:--------:|
| A-LIOn   |           163        |   0.387   | 0.209  | 0.271      |  208     |
| LogMap   |            67        |   0.881   | 0.195  | 0.320      |    3     |            
| LogMapLight |         67        |   0.851   | 0.189  | 0.309      |   83     |
| Matcha   |            6         |   0.000   | 0.000  | 0.000      |   15     |

The second test case evaluates the matching systems to find correspondences between the large-sized MaterialInformation and the mid-sized BFO-based MatOnto. In comparison to the first test case, two of the four evaluated systems (A-LIOn, Matcha) need much longer to calculate the alignment, suprisingly two of the systems are even quicker (LogMap, LogMapLight) than in the first test case. A-LIOn finds a large number of correspondences, hence has the highest recall of the evaluated systems  but 100 out of the 163 found correspondences are incorrect which results in a moderate F1-measure of 0.271 and a rather slow calculation time of over 3 minutes. LogMap stands out again for its very fast computation time of only 3s at a high precision of 0.881. Since LogMap found only 59 correct correspondences out of the 302 reference correspondences, the recall is rather low but the F1-measure is still the highest of the tested systems. LogMapLight is almost 30 times slower than LogMap but finds the same amount of correspondences with 2 additional false positives, so it achieves a slightly lower overall F1-measure than LogMap. Matcha finds 6 wrong correspondences where classes are matched to object properties as in the first test case. 


### Third Test Case
| System   | Correspondences | Precision | Recall | F1-Measure | Time [s] |
|:--------:|:--------------------:|:---------:|:------:|:----------:|:--------:|
| A-LIOn   |           0          |   0.000   | 0.000  | 0.000      | 135      |
| LogMap   |            56        |   0.946   | 0.841  | 0.891      | 14       |
| LogMapLight |         56        |   0.911   | 0.810  | 0.857      | 84       |
| Matcha   |            4         |   0.500   | 0.032  | 0.060      | 21       |

The third test case evaluates matching systems to find correspondences between the large-sized MaterialInformation and the mid-sized EMMO. All evaluated systems compute the alignments in under 3 minutes. Surprisingly, A-LIOn takes the longest to compute the alignments but does not find any correspondence which might be due to some reasoning errors that were produced for EMMO. LogMap again stands out for the fast computation time and high precision with 53 correct correspondences out of the 56 in total. Although LogMap misses out 10 reference correspondences, the F1-measure of 0.891 is the best of the whole MSE track. LogMapLight is 6 times slower than LogMap with a slightly lower precision and 2 additional false positives. Due to 2 additional false negatives, LogMapLight achieves a slightly worse F1-measure of 0.857 - but still the second best of the whole MSE track. Positively surprising, Matcha finds at least 2 correct correspondences out of the 63 reference correspondences and earns its non-zero recall with a fair precision of 0.5 and a rather fast calculation time of 21s. 

## Conclusions
Unfortunately, none of the evaluated matcher finds all reference correspondences correctly. 

LogMap stands out for its very fast computing speed with very high precision at the same time. LogMapLight is significantly slower in every test case and almost constantly shows worse results - only in the first test case the recall of LogMapLight is higher than for LogMap. In our opinion, LogMap is definitely recommended for MSE applications where high precision is demanded. In comparison to that, LogMapLight does not appear to bring any decisive advantage over LogMap. 

Matcha in its current implementation is not suited for MSE applications. 

A-LIOn produces moderate results but does not bring any advantage over LogMap. Furthermore, A-LIOn produces errors while reasoning on EMMO. The latter is the only one of the MSE ontologies used with a significant proportion of essential axioms. According to the annotations in EMMO, this ontology exclusively can be inferred with the FaCT++ reasoner. That might be a cause for the occuring reasoning errors of A-LIOn and bad results in the third test case. 

Since the creation of this MSE benchmark, a large amount of new MSE ontologies have been developed and utilized in various applications. Furthermore, in contrast to the early days of this benchmarks, those ontologies are now easily accessible on the new [Matportal](https://matportal.org/). In the future the mse benchmark should be updated with currently most utilized and moreover general MSE ontologies, which includes the [BWMD-mid](https://matportal.org/ontologies/BWMD-MID), the [MSEO](https://matportal.org/ontologies/MSEO), the [PMDco](https://github.com/materialdigital/core-ontology), the [prov-o](https://www.ebi.ac.uk/ols/ontologies/prov). Apart from considering frequently used domain ontologies like the [BWMD-domain](https://gitlab.cc-asp.fraunhofer.de/EMI_datamanagement/bwmd_ontology/-/raw/master/BWMD_domain.owl), the [LPBFO](https://matportal.org/ontologies/LPBFO) and others, also multi-ontology matching and knowledge graph, e.g. using the [AluTrace data](https://github.com/Mat-O-Lab/AluTraceProject) should be considered in future OAEI campaigns. 

## Contact
This track is organized by Engy Nasr and evaluation was performed by Martin Huschka. If anything is unclear, if you have any comments on the MSE track or would like to contribute, feel free to write an email to huschka [at] emi [.] fraunhofer [.] de.




