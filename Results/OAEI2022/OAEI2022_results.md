# Results of Evaluation for the MSE track within OAEI 2022 
This is the first year the MSE track participates in a OAEI campaign. We are proud to be part of it and would like to thank everyone who has supported us along the way!

## Evaluation modalities
We performed the evaluation using the MELT platform on a Windows 10 system with 16 GB RAM. Every participating system was executed in its standard setting and we compare precision, recall and F-measure with regard to the reference alignment for each test case as well as computation time. 

## Participating systems
This year five systems registered on this track, each of which was used for evaluation. AMD produced an exception and produced empty alignment files, so results are only available for four of the matchers:
- A-LIOn
- LogMap
- LogMapLite
- Matcha

## Generated alignments
We have collected all generated alignments and make them available in a zip-file via the following link. These alignments are the raw results that the following report is based on.

[>>> Download alignments here](https://github.com/EngyNasr/MSE-Benchmark/raw/main/Results/OAEI2022/oaei2022-mse-alignments.zip)

## Results

The following are the results of the participating systems in OAEI 2022 that are completed with the our MSE benchmark.

**First Test Case**

| System   | Correspondences | Precision | Recall | F1-Measure | Time [s] |
|:--------:|:--------------------:|:---------:|:------:|:----------:|:--------:|
| A-LIOn   |           23         |   0.130   | 0.130  | 0.130      |   38     |
| LogMap   |            1         |   1.000   | 0.043  | 0.083      |    9     |
| LogMapLight |         5         |   0.400   | 0.087  | 0.143      |   27     |
| Matcha   |            4         |   0.000   | 0.000  | 0.000      |   22     |

**Second Test Case**

| System   | Correspondences | Precision | Recall | F1-Measure | Time [s] |
|:--------:|:--------------------:|:---------:|:------:|:----------:|:--------:|
| A-LIOn   |           163        |   0.387   | 0.209  | 0.271      |  208     |
| LogMap   |            67        |   0.881   | 0.195  | 0.320      |    3     |            
| LogMapLight |         67        |   0.851   | 0.189  | 0.309      |   83     |
| Matcha   |            6         |   0.000   | 0.000  | 0.000      |   15     |

**Third Test Case**
| System   | Correspondences | Precision | Recall | F1-Measure | Time [s] |
|:--------:|:--------------------:|:---------:|:------:|:----------:|:--------:|
| A-LIOn   |           0          |   0.000   | 0.000  | 0.000      | 135      |
| LogMap   |            56        |   0.946   | 0.841  | 0.891      | 14       |
| LogMapLight |         56        |   0.911   | 0.810  | 0.857      | 84       |
| Matcha   |            4         |   0.500   | 0.032  | 0.060      | 21       |

## Conclusions

## Contact
This track is organized by Engy Nasr and Martin Huschka. If anything is unclear, if you have any comments on the MSE track or would like to contribute, feel free to write an email to huschka [at] emi [.] fraunhofer [.] de.




