# Results of Evaluation for the MSE track within OAEI 2022 
This is the first year the MSE track participates in a OAEI campaign. We are proud to be part of it and would like to thank everyone who has supported us along the way!

## Evaluation modalities
We performed the evaluation using the MELT platform on a Windows 10 system with 16 GB RAM. Every participating system was executed in its standard setting and we compare precision, recall and F-measure with regard to the reference alignment for each test case as well as computation time. 

## Participating systems
This year five systems registered on this track, each of which was used for evaluation with the three test cases of the MSE benchmark. AMD produced an exception and produced empty alignment files, so results are only available for four of the matchers:
- A-LIOn
- LogMap
- LogMapLite
- Matcha

## Generated alignments
We have collected all generated alignments and make them available in a zip-file via the following link. These alignments are the raw results that the following report is based on.

[>>> Download alignments here](https://github.com/EngyNasr/MSE-Benchmark/raw/main/Results/OAEI2022/oaei2022-mse_alignments.zip)

## Results

The following are the results of the participating systems in OAEI 2022 within the MSE track.

### First Test Case

| System   | Correspondences | Precision | Recall | F1-Measure | Time [s] |
|:--------:|:--------------------:|:---------:|:------:|:----------:|:--------:|
| A-LIOn   |           23         |   0.130   | 0.130  | 0.130      |   38     |
| LogMap   |            1         |   1.000   | 0.043  | 0.083      |    9     |
| LogMapLight |         5         |   0.400   | 0.087  | 0.143      |   27     |
| Matcha   |            4         |   0.000   | 0.000  | 0.000      |   22     |

The first test case evaluates matching systems regarding their capability to find "equal" (=), "superclass" (>) and "subclass" (<) correspondences between one small and one large mse ontology. None of the systems finds correspondences other than "equal (=)". All evaluated systems compute the alignment in less than a minute. LogMap stands out with its very fast calculation time and maximum precision of 1.0. However, since only one correspondence was found, the recall and hence the F1-measure is low (0.083). In direct comparison, LogMapLight calculates the alignment in 27s, achieves much lower precision of 0.4 but due to a greater amount of correctly found correspondences the F1-measure is the best of the tested systems. A-LIOn finds the highest number of correspondences, but of those 23 found correspondences 20 are false positives which still results in the second best F1-measure at the lowest calculation time. Matcha finds 4 incorrect crorrespondences and is thus worst participant of the MSE test case one. Investigating the reason for the bad result, Matcha appears to match classes with objectpropertiers, e.g. "Temperature=hasTemperature".

### Second Test Case

| System   | Correspondences | Precision | Recall | F1-Measure | Time [s] |
|:--------:|:--------------------:|:---------:|:------:|:----------:|:--------:|
| A-LIOn   |           163        |   0.387   | 0.209  | 0.271      |  208     |
| LogMap   |            67        |   0.881   | 0.195  | 0.320      |    3     |            
| LogMapLight |         67        |   0.851   | 0.189  | 0.309      |   83     |
| Matcha   |            6         |   0.000   | 0.000  | 0.000      |   15     |

The second test case evaluates matching systems to find correspondences between the large-sized MaterialInformation to the mid-sized and BFO-based MatOnto which does not base on an upper level ontology. In comparison to the first test case, two of the four evaluated systems (A-LIOn, Matcha) need much longer to calculate the alignment, suprisingly two of them are even quicker (LogMap, LogMapLight). A-LIOn finds a large number of correspondences, hence has the highest recall of the evaluated systems, but 100 of the 163 found correspondences are incorrect which results in a moderate F1-measure of 0.271 at a rather slow calculation time of over 3 minutes. LogMap stands out again for its very fast computation time of only 3s at a high precision of 0.881. Since LogMap found only 59 correct correspondences out of the 302 reference correspondences, the recall is rather low but the F1-measure is still the highest of the tested systems. LogMapLight is 80s slower, finds the same amount of correspondences with 2 additional false positives, so results in a slightly lower overall F1-measure than LogMap. Matcha finds 6 wrong correspondences, where classes are matched to object properties again. 


### Third Test Case
| System   | Correspondences | Precision | Recall | F1-Measure | Time [s] |
|:--------:|:--------------------:|:---------:|:------:|:----------:|:--------:|
| A-LIOn   |           0          |   0.000   | 0.000  | 0.000      | 135      |
| LogMap   |            56        |   0.946   | 0.841  | 0.891      | 14       |
| LogMapLight |         56        |   0.911   | 0.810  | 0.857      | 84       |
| Matcha   |            4         |   0.500   | 0.032  | 0.060      | 21       |

The third test case evaluates matching systems to find correspondences between the large-sized MaterialInformation and the mid-sized EMMO. All evaluated systems compute the alignments in under 3 minutes. Surprisingly, A-LIOn takes the longest to compute the alignments but does not find any correspondence which might be due to some reasoning errors that were produced for EMMO. LogMap again stands out for fast computation time and high precision with 53 correct correspondences out of the 56 in total. Although still 10 reference correspondences were missing, the F1-measure of 0.891 is the best of the whole MSE track. Again 70s slower is LogMapLight with a slightly lower precision with 2 additional false positives again. 2 aditional false negatives result in a slightly worse F1-measure of 0.857 - but still the second best of the whole MSE track. Surprisingly, Matcha finds 2 correct correspondences out of 63 and earns a recall but a modest precision of 0.5 at a rather fast calculation time of 21s. 

## Conclusions
Unfortunately, none of the evaluated matcher finds all reference correspondences correctly. 

But LogMap stands out for its very fast computing time with very high precision at the same time. LogMapLight is significantly slower in every test case and almost constantly shows worse results - only in the first test case the recall of LogMapLight is higher than LogMap. In our opinion, LogMap would be recommended for MSE applications where high precision is demanded, LogMapLight does not appear to bring any decisive advantage. 

Matcha in its current implementation is not suited for MSE applications. 

A-LIOn produces errors while reasoning on the EMMO ontology, which is the only of the used MSE ontologies with a significant proportion of axioms. According to the annotations in EMMO, this ontology exclusively functions with the FaCT++ reasoner. That might be a cause for the occuring reasoning errors of A-LIOn. 

Since the creation of this MSE benchmark, a large amount of new MSE ontologies have been developed and utilized in various applications. Furthermore, in contrast to the early days of this benchmarks, those ontologies are now easily accessible on the new [Matportal](https://matportal.org/). In the future the mse benchmark should be updated with currently most utilized MSE ontologies, which includes the [BWMD-mid](https://matportal.org/ontologies/BWMD-MID), the [MSEO](https://matportal.org/ontologies/MSEO), the [PMDco](https://github.com/materialdigital/core-ontology), the [prov-o](https://www.ebi.ac.uk/ols/ontologies/prov). Also, multi-ontology matching and knowledge graph matching should be considered. 

## Contact
This track is organized by Engy Nasr and evaluation was performed by Martin Huschka. If anything is unclear, if you have any comments on the MSE track or would like to contribute, feel free to write an email to huschka [at] emi [.] fraunhofer [.] de.




