# Beyond Citations: Tracing the Rapid Adoption and Impact of AlphaFold in Biomedical Research Through Full-Text Analysis
by Haochuan Cui1, Yuzhuo Wang2 and Kai Li3

## Methods:

### 1.Identifying the type of sections in the full text
We analyzed the paper section title where AlphaFold is located as one signal of how AlphaFold is used in scientific research. Existing studies have shown that section titles provide sufficient information for identifying the functional structure for sections (Ma et al., 2022). Therefore, we used a rule-based approach to process section titles and identify their categories. Specifically, we divided the sections into six types: "Abstract," "Introduction," "Methods," "Results," "Discussion," and "others." For each category, we constructed a set of keywords. If a section title contained keywords associated with a specific category, the section was classified accordingly. The keywords corresponding to the different categories are as follows
Introduction: introduction, introductions, background, backgrounds, related literature, related work, literature review, related works, pre publication history, review.
Methods: method, methods, research methods, research method, research methodology, research methodologies, proposed method, proposed methods, material and method', 'materials and method, material and methods, materials and methods, methodology, methodologies, statistical analysis, molecular methods, statistical methods, patients and methods, materials, data and statistical analyses, data collection, data and methods, comparison of methods, material \& methods, statistics', 'the proposed fusion method, methods/design, experimental section, experimental design, materials and methods, experimental methodologies, data analysis', 'trial design, models design and calculation method, methods design, experimental procedures, subjects and methods, diagnostic methods, methods and materials, method and materials, methods and material, method and material, experimental methods.
Results: result, results, experimental results, experimental results and analysis, findings, results and taxonomic treatment, results and discussion, results/discussion, results discussion, results and discussions, result and discussion, results discussion.
Discussion: discussion, discussions, discussion and conclusions, discussion and conclusion, discussions and conclusion, strengths and limitations of the study, future, conclusions and future perspectives, summary, conclusion, conclusions, limitation, limitations, limitation of the study, summary and implications, conclusion and outlook, conclusion and future work, future directions, conclusions and recommendations, discussions and conclusions, discussion conclusion.
 





### 2.Classifying the functional role of sentences mentioning AlphaFold
We initially collected 56,650 sentences mentioningAlphaFold from the PMC Open Access dataset. To classify the functional role of these sentences, we utilized the classification framework introduced by Jurgens et al. (2018), which identifies six citation functions: Uses, CompareOrContrast, Background, Extend, Motivation, and Future. The following provides a detailed description of each citation function based on their definitions:
- USES indicates that the current work employs data, methods, or other resources from the cited paper. It shows direct application or utilization of contributions. 
- COMPARISON OR CONTRAST  is used to express similarities or differences between the current work and the cited paper.It helps position the current research within the broader context of existing work.
- BACKGROUND is used when the cited paper provides relevant information or context for the current domain or research. It helps establish the foundational knowledge necessary for understanding the current work. 
- MOTIVATION highlights the need for data, goals, methods, or other elements that the cited paper addresses. It often sets the stage for why the current research is important or necessary. 
- EXTENSION is used when the current work builds upon or extends the data, methods, or findings of the cited paper. It demonstrates advancement or improvement over the cited paper’s work. 
- FUTURE: This function indicates that the cited paper presents a potential avenue for future work. It suggests that the cited paper contributions could be further explored or developed in subsequent research" 
Our model achieves an F1 score of 76% on the annotated dataset.

Using a human-labeled dataset from Jurgens et al. (2018) as training data, which includes nearly 2,000 sentences annotated for one of the six citation functions, we implemented a BERT-based classification model, specifically leveraging SciBERT as the pre-trained model. Our model achieved an F1 score of 76% on the annotated dataset. We then applied this trained model to classify sentences mentioning AlphaFold according to their citation function. Given our research focus on how the focal paper employs AlphaFold, we concentrated on the 'Uses,' 'Comparison or Contrast,' and 'Background' functions, merging the remaining categories into 'Other.'
