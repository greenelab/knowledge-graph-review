---
author-meta:
- David Nicholson
- Jane Roe
date-meta: '2019-09-16'
keywords:
- knowledge-graphs
- network-embeddings
- text-mining
- natural-language-processing
- deep-learning
- machine-learning
- literature-review
lang: en-US
title: Constructing Knowledge Graphs and Their Biomedical Applications
...






<small><em>
This manuscript
([permalink](https://greenelab.github.io/knowledge-graph-review/v/e0a2cb3a7059fc665e89e2c8f117db8a1a8a3b33/))
was automatically generated
from [greenelab/knowledge-graph-review@e0a2cb3](https://github.com/greenelab/knowledge-graph-review/tree/e0a2cb3a7059fc665e89e2c8f117db8a1a8a3b33)
on September 16, 2019.
</em></small>

## Authors



+ **David Nicholson**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0003-0002-5761](https://orcid.org/0000-0003-0002-5761)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [danich1](https://github.com/danich1)<br>
  <small>
     Department of Systems Pharmacology and Translational Therapeutics, University of Pennsylvania
     · Funded by GBMF4552 and T32 HG000046
  </small>

+ **Jane Roe**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [XXXX-XXXX-XXXX-XXXX](https://orcid.org/XXXX-XXXX-XXXX-XXXX)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [janeroe](https://github.com/janeroe)<br>
  <small>
     Department of Something, University of Whatever; Department of Whatever, University of Something
  </small>



## Abstract {.page_break_before}

1. Give high level description of review as it pertains to knowledge graphs (creation and application)


## Introduction

Knowledge graphs are a practical resource for many real world applications.
They have been used in social medial mining to classify nodes [@IexVJgDF] or to create a recommendation system [@Eqbsazq5].
Knowledge graphs have also been used to understand natural language via interpreting simple questions and using relational information to provide answers [@N0gUhlt9; @s8ydThMc].
In a biomedical setting these graphs have been used to prioritize genes relevant to disease [@GI2y7kMc; @Oi5yRd0v; @15k4Xz0i3; @1D9FTzRBg], perform drug repurposing [@O21tn8vf] and identify drug-target interactions [@15GxqZyO8].

Despite their utility, precisely defining a knowledge graph is a difficult task because there are multiple conflicting definitions [@V9M93in].
For this review, we define a knowledge graph as the following: a resource that integrates single or multiple sources of information into the form of a graph.
This graph allows for the capacity to make semantic interpretation, continuously incorporate new information and uncover novel hidden knowledge through computational techniques and algorithms.
Based on this definition resources like Hetionet [@O21tn8vf] would be considered a knowledge graph.
Hetionet integrates multiple sources of information into the form of a graph (example shown in Figure {@fig:hetionet_schema}) and was used to derive novel information concerning unique drug treatments [@O21tn8vf].
We do not consider databases like DISEASES [@5gG8hwv7] and DrugBank [@1FI8iuYiQ] to be knowledge graphs.
These resources contain essential information, but do not represent their data in graph form.

Knowledge graphs are often constructed from manually curated databases [@O21tn8vf; 10.1371/journal.pcbi.1002574; @kBHNhSma; @tIGJl1ES;  @BTEcMH0X].
These sources provide previously established information that can be incorporated into a graph.
For example, a graph using DISEASES [@5gG8hwv7] as a resource would have genes and diseases as nodes, while edges would be added between nodes that have an association.
This example shows a single type of relationship; however, there are graphs that use databases with multiple relationships.
Other approaches have used natural language processing techniques to build knowledge graphs [@gddb9uXr; @rxaBUglG].
One example used a text mining system to extract sentences that indicated a protein interacting with another protein [@ibJfUvEe].
Once these sentences have been identified, they are incorporated as evidence for establishing edges in a knowledge graph.

In this review we describe various approaches for constructing and applying knowledge graphs in a biomedical setting.
We discuss the pros and cons of constructing a knowledge graph via manually curated  databases and via text mining systems.
We also compare assorted approaches for applying knowledge graphs to solve biomedical problems.
Lastly, we conclude on the practicality of knowledge graphs and point out future applications that have yet to be explored.

![
A metagraph (schema) of the heterogeneous network used in the Rephetio project [@O21tn8vf].
This undirected network depicts pharmacological and biomedical information.
The nodes (circles) represent entities and edges (lines) depict  relational information between two entities.
](https://raw.githubusercontent.com/dhimmel/rephetio/f02d44fde7eeef0ffdca0800e0b43c48d800c86d/figure/metagraph.png){#fig:hetionet_schema}


## Building Biomedical Knowledge Graphs

Knowledge graphs can be constructed in many ways using resources such as text or pre-existing databases. 
Usually, knowledge graphs are constructed using pre-existing databases.
These databases are constructed by domain experts using approaches ranging from manual curation to automated techniques, such as text mining systems.
Manual curation is a process that involves extensive use of domain experts to read papers and detect sentences that assert a relationship.
Automated approaches involve the use of machine learning or natural language processing techniques to rapidly detect sentences of interest.
We categorize these automated approaches into the following groups: rule-based extraction, unsupervised machine learning, and supervised machine learning.
We discuss examples of each type of approach and synthesize the strengths and weaknesses of each.

### Constructing Databases and Manual Curation

1. Talk about papers that construct knowledge graphs without text mining approaches
2. Discuss the positives and negatives for these methods

### Text Mining for Relationship Extraction

#### Rule-Based Natural Language Processing

1. Mention papers on hand written rules and expressions

#### Unsupervised Machine Learning

1. Mention Clustering Analysis
2. Mention Co-Occurrence approaches

#### Supervised Machine Learning

1. Mention the availablility of publically available data
	1. PPI - 5 datasets 
	   1. 10.1016/j.artmed.2004.07.016 
	   2. 10.1186/1471-2105-8-50 
	   3. Learning language in logic - genic interaction extraction challenge
	   4. 10.1093/bioinformatics/btl616 
	   5. http://helix-web.stanford.edu/psb02/ding.pdf
	2. DaG - 3 datasets
	   1. 10.1016/j.jbi.2012.04.004 
	   2. 10.1186/s12859-015-0472-9
	   3. 10.1186/1471-2105-14-323 
	   4. 10.1186/1471-2105-13-161
	3. CiD 
	  1. 10.1093/database/baw068 
	4. CbG 
	  1. Biocreative VI track 5 - raw citation
	5. more if exists talk about deep learning methods
2. Mention the use of Support Vector Machines and other non deep learning classifiers
   1. Will have to mention that field has moved to deep learning.
   2. 10.1186/s13326-017-0168-3
   3. 10.1371/journal.pcbi.1004630
3. Mention deep learning methods
   1. 1901.06103v1
   2. 10.1016/j.knosys.2018.11.020
   3. 10.1177/0165551516673485
   4. 1706.01556v2
   5. ^^ A few papers here but a lot more will be put into place 
   6. Mention caveat which is the need for large annotated datasets
   7. Mention a direction the field is moving to which is weak supervision and more that info that will come in time.


## Applying Knowledge Graphs to Biomedical Challenges

1. Mention that these graphs can be used for discovery
2. Mention representation learning (aka representing a graph as dense vectors for nodes and/or edges)
3. 

### Unifying Techniques

1. Set up the problem that maps a knowledge graph into a low dimensional space

#### Matrix Factorization

1. Mention techniques for these with some papers

#### Deep Learning

1. Define node neighborhoods
2. Talk about random walks 
3. Talk about auto encoders random walk independent approaches 

### Unifying Applications

1. Mention how the previous section is used in a biomedical setting

#### Disease and Gene Interactions

1. Mention disease gene prioritization
2. Mention Disease gene associations

#### Protein Protein Interactions

1. Mention predicting genes interacting genes

#### Drug Interactions

1. Talk about drug side effects
2. Drug repurposing
3. Drug-Disease Interations

#### Clinical applications

1. Can mention EHR use and other related applications
2. Mention Tiffany's work on private data embeddings


## Conclusion
1. Summarize discussed positives and pitfalls
2. Leave some open ended questions yet to be explored
  1. Will come into play as I write this review paper


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>
