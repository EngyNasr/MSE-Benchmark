# MSE Benchmark V1.0

This project includes the MSE (Material Sciences and Engineering) Benchmark created during the Master's Thesis: "Evaluation of Automatic Ontology Matching for Materials Sciences and Engineering".

The project may also include future improvements for the Benchmark.

>**The MSE Benchmark was used for the very first time as MSE track to evaluate ontology matching tools in the OAEI campaign 2022:**  
>[**Results of the Evaluation for the MSE track within OAEI 2022**](Results/OAEI2022/OAEI2022_results.md)

## Table of Content

- [MSE Benchmark Description](#msebenchmarkdescription)
    - [MSE Test Cases](#msetestcases)
    - [Manual Reference Alignments](#manualreferencealignments)
    - [Background Knowledge Ontologies](#backgroundknowledgeontologies)

<a name="msebenchmarkdescription"/>  

## MSE Benchmark Description
The MSE Benchmark V1.0 consists of three MSE test cases each including two ontologies, a manual reference alignment for every test case and MSE-related background knowledge ontologies:

- ***Test Cases***
    - First Test Case: 
        - Source Ontology (O1)
        - Target Ontology (O2)
        - Manual Reference Alignment (R) 
    - Second Test Case: 
        - Source Ontology (O1)
        - Target Ontology (O2)
        - Manual Reference Alignment (R)
    - Third Test Case: 
        - Source Ontology (O1)
        - Target Ontology (O2)
        - Manual Reference Alignment (R)  
        ####

- ***Resouces (Background Knowledge Ontologies)***
    - Periodic Table Dictionary
    - EMMO (European Materials Modelling Ontology)
    - Other resources were used like WordNet which can be found Online ([Github Page](https://github.com/AgreementMakerLight/AML-Project/tree/master/AgreementMakerLight/store/knowledge))

<a name="msetestcases"/>  

### MSE Test Cases:

One major part of the MSE benchmark are the test cases. The ontologies chosen do not target very specialized disciplines of the MSE domain, e.g. ceramics. They are all created to be general to the MSE domain. Being from the same level of specialization, they can be matched to each other and used for the evaluation of the ontology matchers.

***A test case consists of two OWL-ontologies chosen from three different MSE ontologies:***

 - **MaterialInformation** ontology created by Prof. Ashino in Japan [Prof.Ashino's Paper](https://pdfs.semanticscholar.org/7f0a/d9346c8664bbb9e7d60c1efbd663a7790cdb.pdf?_ga=2.38778980.631833280.1600761428-1848885946.1600761428)
   - The ontology is not openly available, however, it was provided upon request. 
   - The ontology is not based on an upper level ontology, which makes the ontology not easily interoperable with other MSE ontologies. 
   - The ontology is also divided into smaller ontologies (partitions). 
   - The partitions are Environment, Geometry, Material Information, Manufacturing Process, Property, Substance, Unit Dimension, Structure, Equation and Physical Constant. 
   - The full ontology consists of 545 classes, 98 properties (relations) and 411 individuals (instances of the classes).
####
 - **MatOnto** ontology available on GitHub [Page](https://github.com/inovexcorp/MatOnto-Ontologies)
   - The cloned ontology's files are RDF data, saved in Turtle (.ttl) format. 
   - The files are converted from Turtle format into RDF/XML, (.OWL).
   - The ontology is based on the upper level ontology, the BFO. 
   - The full ontology consists of 847 classes, 96 properties (relations) and 131 individuals (instances of the classes).
####
- **EMMO** (European Materials Modelling Ontology) v1.0.0-alpha2, available on Github [Page](https://github.com/emmo-repo/EMMO)
    - EMMO is an ongoing MSE ontology.
    - This version is downloaded on November 2020.
    - EMMO is an upper and mid level ontology.
    - EMMO adapts the BFO in its creation, accordingly classes are similar to the BFO but modified.
    - The full ontology consists of 451 classes, 35 properties (relations) and 0 individuals (instances of the classes).

***Test Cases Design:***

[![Test-Cases-Design.jpg](https://i.postimg.cc/3NXxfmK9/Test-Cases-Design.jpg)](https://postimg.cc/YLS7h4Lm)

<sup>Summary of the three test cases compositions, created from above mentioned MSE ontologies, such that the green rectangles show the upper level ontologies EMMO and the BFO and the blue circles show the domain specific ontologies. The 1st test case is between a reduced subset of MaterialInformation ontology and  the complete MatOnto (BFO + MatOnto). The 2nd test case is between the complete MaterialInformation ontology and the complete MatOnto (BFO + MatOnto). Finally, the 3rd test case is between the EMMO upper level ontology and the complete MaterialInformation ontology.</sup>


***1st Test Case (MatOnto - Reduced MaterialInformation):***

 - This test case is designed to demonstrate the behavior of the ontology matchers upon two domain specific MSE ontologies. It is designed small in terms of the number of entities to be able to evaluate and discuss ontology matchers on the expected possible logical relations (e.g., =, ⊆, ⊇, ⊥) that would be the best practice to have as alignments between the two ontologies’ classes, enabling an easier interoperable merging afterwards.
 - The test case is designed to discuss how each matcher implicitly shows more logical relations and how to improve each matcher result.

***2nd Test Case (MaterialInformation - MatOnto):***
 - This test case is a bigger scale version of the 1st test case in terms of the number entities, but not in terms of the variety of logical relations, it only consists of the equivalence (=) logical relation.
 - Both of the ontologies included in the test case are domain specific ontologies, MatOnto bases on the BFO as its upper level ontology however, MaterialInformation ontology has no base of any formal (upper leverl ontology) ontology.
 - This test case is a typical practice if two MSE domain ontologies are decided to be merged in one ontology to see how far the ontology matchers will get alignments of ontologies’ classes of the same domain, and how the ontology matchers will help in improving interoperability between these two ontologies due to the difference of usage of the formal ontologies.

***3rd Test Case (EMMO - MaterialInformation ):***
 - This test case is designed for a case in which a domain ontology has to be merged to an upper level ontology in order to maximize the cross-domain interoperability of this domain ontology. 
 - To do so, the most commonly known upper level ontology in the domain ontology's domain is chosen, and then merged to it. 
 - Accordingly, a matching should be done first between the domain ontology and the upper level ontology chosen.
The EMMO is chosen as an upper level ontology, since EMMO is mainly designed for the MSE domain.

<a name="manualreferencealignments"/>  

### Manual Reference Alignments
The second part of the MSE benchmark is the manual reference alignment, which are the expected result from the test cases’ alignment. They are compared to the result of the ontology matchers. For every test case, a manual reference alignment is created.

- Singulars and plurals are equivalently matched (e.g. water = waters).
- Only classes correspondances are included (No properties or individuals alignment).


***1st Test Case:***

Includes all possible types of logical relations (correspondences) between ontologies’ classes, subclass (⊆) , superclass (⊇) and equivalence (=).
        
***2nd Test Case:***

Include only the equivalence (=) logical relation (correspondences) between the ontologies’ classes.
    
***3rd Test Case:***

Include only the equivalence (=) logical relation (correspondences) between the ontologies’ classes.

<a name="backgroundknowledgeontologies"/>  

### Background Knowledge Ontologies

The background knowledge ontology acts as a **Resources** (semantic bridge), a midway in the matching process between the two input ontologies. If a class from the first ontology is not lexically aligned (String Matching) to another class from the second ontology, but they are defined to be synonymous of each other in the background kwowledge ontology, then they will be aligned together as equivalent based on the knowledge provided by the background knowledge ontology.

***Periodic Table Dictionary:***
    
 - The dictionary is created using Protege, saved as an ontology (.OWL) file to represent a specific case that was spot out from the test cases creation. 
 - It includes all elements of the periodic table, and in the same class of each element the (rdf:label) includes the element’s abbreviation.
    
***EMMO:***

 - The ontology is also chosen as a background knowledge ontology since it incorporates a rich hierarchy and is designed for multiscale materials modelling.
 - In consequence, the importance of the choice of the corresponding background knowledge ontology for each ontology matching process can be discussed.
