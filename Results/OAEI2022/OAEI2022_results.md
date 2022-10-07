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

The second test case evaluates matching systems to find correspondences between the large BFO-based MaterialInformation to the mid-sized MatOnto which does not base on an upper level ontology. In comparison to the first test case, two of the four evaluated systems (A-LIOn, Matcha) need much longer to calculate the alignment, suprisingly two of them are even quicker (LogMap, LogMapLight). A-LIOn finds a large number of correspondences, hence has the highest recall of the evaluated systems, but 100 of the 163 found correspondences are incorrect which results in a moderate F1-measure of 0.271 at a rather slow calculation time of over 3 minutes. LogMap stands out again for its very fastcomputation time of only 3s at a high precision of 0.881. Since 8 of the 67 found correspondences were fals positive s, the recall 


### Third Test Case
| System   | Correspondences | Precision | Recall | F1-Measure | Time [s] |
|:--------:|:--------------------:|:---------:|:------:|:----------:|:--------:|
| A-LIOn   |           0          |   0.000   | 0.000  | 0.000      | 135      |
| LogMap   |            56        |   0.946   | 0.841  | 0.891      | 14       |
| LogMapLight |         56        |   0.911   | 0.810  | 0.857      | 84       |
| Matcha   |            4         |   0.500   | 0.032  | 0.060      | 21       |

## Conclusions

## Contact
This track is organized by Engy Nasr and Martin Huschka. If anything is unclear, if you have any comments on the MSE track or would like to contribute, feel free to write an email to huschka [at] emi [.] fraunhofer [.] de.




