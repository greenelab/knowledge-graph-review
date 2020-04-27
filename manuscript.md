---
author-meta:
- David Nicholson
- Casey S. Greene
date-meta: '2020-04-27'
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
([permalink](https://greenelab.github.io/knowledge-graph-review/v/6f20fc1cdcfa1f65ccf623fffd0565805ab19813/))
was automatically generated
from [greenelab/knowledge-graph-review@6f20fc1](https://github.com/greenelab/knowledge-graph-review/tree/6f20fc1cdcfa1f65ccf623fffd0565805ab19813)
on April 27, 2020.
</em></small>

## Authors



+ **David Nicholson**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0003-0002-5761](https://orcid.org/0000-0003-0002-5761)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [danich1](https://github.com/danich1)<br>
  <small>
     Department of Systems Pharmacology and Translational Therapeutics, University of Pennsylvania
     · Funded by The Gordon and Betty Moore Foundation (GBMF4552) and the National Institutes of Health (T32 HG000046)
  </small>

+ **Casey S. Greene**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0001-8713-9213](https://orcid.org/0000-0001-8713-9213)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [cgreene](https://github.com/cgreene)
    · ![Twitter icon](images/twitter.svg){.inline_icon}
    [greenescientist](https://twitter.com/greenescientist)<br>
  <small>
     Department of Systems Pharmacology and Translational Therapeutics, Perelman School of Medicine, University of Pennsylvania; Childhood Cancer Data Lab, Alex's Lemonade Stand Foundation
     · Funded by The Gordon and Betty Moore Foundation (GBMF4552) and the National Institutes of Health (R01 HG010067)
  </small>



## Abstract {.page_break_before}

Knowledge graphs can support many biomedical applications.
These graphs represent biomedical concepts and relationships in the form of nodes and edges.
In this review, we discuss how these graphs are constructed and applied with a particular focus on how machine learning approaches are changing these processes.
Biomedical knowledge graphs have often been constructed by integrating databases that were populated by experts via manual curation, but we are now seeing a more robust use of automated systems.
A number of techniques are used to represent knowledge graphs, but often machine learning methods are used to construct a low-dimensional representation that can support many different applications.
This representation is designed to preserve a knowledge graph’s local and/or global structure.
Additional machine learning methods can be applied to this representation to make predictions within genomic, pharmaceutical, and clinical domains.
We frame our discussion first around knowledge graph construction and then around unifying relational learning techniques and unifying applications.
Advances in machine learning for biomedicine are creating new opportunities across many domains, and we note potential avenues for future work with knowledge graphs that appear particularly promising.


## Introduction

Knowledge graphs are a practical resource for many real world applications.
They have been used in social media mining to classify nodes [@DjhSdWbc] and create recommendation systems [@Eqbsazq5].
These graphs have also been used in natural language processing to interpret simple questions and use relational information to provide answers [@N0gUhlt9; @s8ydThMc].
In a biomedical setting these graphs have been used to prioritize genes relevant to disease [@GI2y7kMc; @Oi5yRd0v; @15k4Xz0i3; @1D9FTzRBg], perform drug repurposing [@O21tn8vf] and identify drug-target interactions [@15GxqZyO8].

Despite their utility, precisely defining a knowledge graph is a difficult task because there are multiple conflicting definitions [@V9M93in].
For this review, we define a knowledge graph as the following: a resource that integrates single or multiple sources of information into the form of a graph.
This graph allows for the capacity to make semantic interpretation, continuously incorporate new information and uncover novel hidden knowledge through computational techniques and algorithms.
Based on this definition resources like Hetionet [@O21tn8vf] would be considered a knowledge graph as Hetionet integrates multiple sources of information into the form of a graph (example shown in Figure {@fig:hetionet_schema}).
Hetionet was used to derive novel information concerning unique drug treatments [@O21tn8vf].
We do not consider databases like DISEASES [@5gG8hwv7] and DrugBank [@1FI8iuYiQ] to be knowledge graphs.
Although these resources contain essential information, they do not represent their data in the form of a graph.

Knowledge graphs are often constructed from manually curated databases [@O21tn8vf; 10.1371/journal.pcbi.1002574; @kBHNhSma; @tIGJl1ES;  @BTEcMH0X].
These databases provide previously established information that can be incorporated into a graph.
For example, a graph using DISEASES [@5gG8hwv7] as a resource would have genes and diseases as nodes, while edges added between nodes would represent an association between a gene and a disease.
This example shows a single type of relationship; however, there are graphs that use databases with multiple relationships [@O21tn8vf; @6Vifn4pu].
In addition to manual curation other approaches have used natural language processing techniques to construct knowledge graphs [@gddb9uXr; @rxaBUglG].
One example used a text mining system to extract sentences that illustrate a protein interacts with another protein [@ibJfUvEe].
Once identified, these sentences can be incorporated as evidence to establish an edge in a knowledge graph.

In this review we describe various approaches for constructing and applying knowledge graphs in a biomedical setting.
We discuss the pros and cons of constructing a knowledge graph via manually curated databases and via text mining systems.
We also compare assorted approaches for applying knowledge graphs to solve biomedical problems.
Lastly, we conclude on the practicality of knowledge graphs and point out future applications that have yet to be explored.

![
A metagraph (schema) of the heterogeneous network used in the Rephetio project [@O21tn8vf].
This undirected network depicts pharmacological and biomedical information.
The nodes (circles) represent entities and edges (lines) depict relational information between two entities.
](https://raw.githubusercontent.com/dhimmel/rephetio/f02d44fde7eeef0ffdca0800e0b43c48d800c86d/figure/metagraph.png){#fig:hetionet_schema}


## Building Biomedical Knowledge Graphs

Knowledge graphs can be constructed in many ways using resources such as pre-exisitng databases or text.
Usually, knowledge graphs are constructed using pre-existing databases. 
These databases are constructed by domain experts using approaches ranging from manual curation to automated techniques, such as text mining.
Manual curation is a time consuming process that requires domain experts to read papers and annotate sentences that assert a relationship.
Automated approaches rely on machine learning or natural language processing techniques to rapidly detect sentences of interest.
We categorize these automated approaches into the following groups: rule-based extraction, unsupervised machine learning, and supervised machine learning and discuss examples of each type of approach while synthesizing their strengths and weaknesses.

### Constructing Databases and Manual Curation

Database construction dates back all the way to 1956 where the first database contained a protein sequence of the insulin molecule [@GjM2NbnC].
The process of database construction involves gathering relevant text such as journal articles, abstracts, or web-based text and having curators read the gathered text to detect sentences that implicate a relationship (i.e., relationship extraction).
Notable databases constructed by this process can be in found in Table {@tbl:manual-curated-databases}.
An example database, COSMIC [@pfquADl5] was constructed by a group of domain experts scanning the literature for key cancer related genes.
This database contained approximately 35M entries in 2016 [@pfquADl5] and by 2018 had grown to 45M entries [@1E72FZcIm].
Studies have shown that databases constructed in this fashion contain relatively precise data but the recall is low [@5TLcy6Yl; @1BnoByjXH; @OELNNm08; @yjdNa04s; @d3rG3TXb; @16P0HRKom; @UdzvLgBM].
This happens because the publication rate is too high for curators to keep up [@vYYWSlK2].
This bottleneck highlights a critical need for future approaches to scale fast enough to compete with the increasing publication rate.

Semi-automatic methods are a way to accelerate the curation process [@17LLVYRDg; @iJxqfYog; @us6gXxVp; @kHKmKy23; @17KVV4Pum; @d3rG3TXb; @SHPz84Z7].
The first step of these methods is to use an automated system to initially extract sentences from text.
This process removes irrelevant sentences, which dramatically decreases the amount of text that curators must sift through.
Following the pre-filtering step, curators then approve or reject the remaining sentences.
This approach saved curators an average of 2-2.8 hours compared to manual efforts [@17LLVYRDg; @KX7N360G]. 
Despite automated systems excelling in identifying sentences for commonly occurring relationships, they tend to miss lesser-known relationships [@17LLVYRDg].
These systems also have a hard time parsing ambiguous sentences that naturally occur in text, which makes correcting them a challenging task [@17LLVYRDg].
Given these caveats, future approaches should look into using techniques that simplify sentences to solve the ambiguity issue [@umenx8Nh; @aJL1tPyy].

Despite the negatives of manual curation, it is still an essential process for extracting relationships from text.
This process can be used to generate gold standard datasets that automated systems use for validation [@Y2DcwTrA; @YWh6tPj] and can be used during the training process of these systems (i.e., active learning) [@MTIt6gSA].
It is important to remember that manual curation alone is precise, but results in low recall rates [@UdzvLgBM].
Future databases should consider initially relying on automated methods to obtain sentences at an acceptable recall level, then incorporate manual curation as a way to fix or remove irrelevant results.

| Database [Reference] | Short Description | Number of Entries | Entity  Types | Relationship Types | Method of Population |
| --- | --- | --- | --- | --- | --- |
| BioGrid [@kFAyvOpe] | A database for major model organisms. It contains genetic and proteomic information.| 572,084 | Genes, Proteins| Protein-Protein interactions | Semi-automatic methods |
| Comparative Toxicogenomics Database [@axd6eJec] | A database that contains manually curated chemical-gene-disease interactions and  relationships. | 2,429,689 | Chemicals (Drugs), Genes, Diseases | Drug-Genes, Drug-Disease, Disease-Gene mappings | Manual curation and Automated systems |
| Comprehensive Antibiotic Resistance Database [@1ByMfX8Y1] | Manually curated database that contains information about the molecular basis of antimicrobial resistance. | 174,443 | Drugs, Genes, Variants | Drug-Gene, Drug-Variant mappings | Manual curation |
| COSMIC [@pfquADl5] | A database that contains high resolution human cancer genetic information. | 35,946,704 | Genes, Variants, Tumor Types| Gene-Variant Mappings | Manual Curation |
| Entrez-Gene [@u7vVtngU] | NCBI's Gene annotation database that contains information pertaining to genes, gene's organism source, phenotypes etc. | 7,883,114 | Genes, Species and Phenotypes | Gene-Phenotypes and Genes-Species mappings | Semi-automated curation |
| OMIM [@1FZWpEoss] | A database that contains phenotype and genotype information | 25,153 | Genes, Phenotypes | Gene-Phenotype mappings | Manual Curation |
| PharmGKB [@qbo1ouMs] | A database that contains genetic, phenotypic, and clinical information related to pharmacogenomic studies. | 43,112 | Drugs, Genes, Phenotypes, Variants, Pathways | Gene-Phenotypes, Pathway-Drugs, Gene-Variants, Gene-Pathways | Manual Curation and Automated Methods |
| UniProt [@1ZE22clL] | A protein protein interaction database that contains proteomic information. | 560,823 | Proteins, Protein sequences | Protein-Protein interactions | Manual and Automated Curation |

Table: A table of databases that used a form of manual curation to populate entries. 
Reported number of entities and relationships are relative to time of publication.
{#tbl:manual-curated-databases}

### Text Mining for Relationship Extraction

#### Rule-Based Relationship Extraction

Rule based-extraction consists of identifying essential keywords and grammatical patterns to detect relationships of interest. 
Keywords are established via expert knowledge or though the use of pre-existing ontologies, while grammatical patterns are constructed via experts curating parse trees. 
Parse trees are tree data structures that depict a sentence's grammatical structure and come into two forms: a constituency parse tree (Figure {@fig:constituency-parse-tree-example}) and a dependency parse tree (Figure {@fig:dependency-parse-tree-example}).
Both trees use part of speech tags, labels that dictate the grammatical role of a word such as noun, verb, adjective, etc, for construction, but represent the information in two different forms.
Constituency parse trees breaks a sentence down into a subphrases (Figure {@fig:constituency-parse-tree-example}) while dependency path trees analyzes the grammatical structure of a sentence (Figure {@fig:dependency-parse-tree-example}).
Many text mining approaches [@i7KpvzCo; @3j1T67vB; @iiQkIqUX] use such trees to generate features for machine learning algorithms and these approaches are discussed in later sections.
In this section we focus on approaches that use rule based extraction as a primary strategy to detect sentences that allude to a relationship.

Grammatical patterns can simplify sentences for easy extraction [@aJL1tPyy; @66vfJAIo].
Jonnalagadda et al. used a set of grammar rules inspired by constituency trees to reshape complex sentences with simpler versions [@aJL1tPyy] and these simplified versions were manually curated to determine the presence of a relationship.
By simplifying sentences this approach achieved high recall, but had low precision [@aJL1tPyy].
Other approach used simplification techniques to make extraction easier [@15I4QE3J; @7PCrlbDi; @J0VF6x1n; @1HnOwZ1Xq].
Tudor et al. simplified sentences to detect protein phosphorylation events [@J0VF6x1n].
Their sentence simplifier broke complex sentences that contain multiple protein events into smaller sentences that contain only one distinct event.
By breaking these sentences down the authors were able to increase their recall; however, sentences that contained ambiguous directionality or multiple phosphorylation events were too complex for the simplifier.
As a consequence the simplifier missed some relevant sentences [@J0VF6x1n].
These errors highlight a crucial need for future algorithms to be generalizable enough to handle various forms of complex sentences.

Pattern matching is a fundamental approach used to detect relationship asserting sentences.
These patterns can consist of phrases from constituency trees, a set of keywords or some combination of both [@OnvaFHG9; @d3rG3TXb; @dRQuIwpJ; @23i6gRBE; @1avvFjJ9; @KEkjqdB0].
Xu et al. designed a pattern matcher system to detect sentences in PubMed abstracts that indicate drug-disease treatments [@1avvFjJ9].
This system matched drug-disease pairs from ClinicalTrials.gov to drug-disease pairs mentioned in abstracts.
This matching process aided the authors in identifying sentences that can be used to create simple patterns, such as "Drug in the treatment of Disease" [@1avvFjJ9], to match other sentences in a wide variety of abstracts.
The authors hand curated two datasets for evaluation and achieved a high precision score of 0.904 and a low recall score of 0.131 [@1avvFjJ9].
This low recall score was based on constructed patterns being too specific to detect infrequent drug pairs.
Besides constituency trees, some approaches used dependency trees to construct patterns [@jg0TGCov; @i7KpvzCo].
Depending upon the nature of the algorithm and text, dependency trees could be more appropriate than constituency trees and vise versa.
The performance difference between the two trees remains as an open question for future exploration.

Rules based methods provide a basis for many relationship extraction systems.
Approaches in this category range from simplifying sentences for easy extraction to identifying sentences based on matched key phrases or grammatical patterns.
Both require a significant amount of manual effort and expert knowledge to perform well.
A future direction is to develop ways to automatically construct these hand-crafted patterns, which would accelerate the process of creating these rule-based systems.

![
A visualization of a constituency parse tree using the following sentence: "BRCA1 is associated with breast cancer" [@1EvoylLWK].
This type of tree has the root start at the beginning of the sentence.
Each word is grouped into subphrases depending its correlating part of speech tag.
For example, the word "associated" is a past participle verb (VBN) that belongs to the verb phrase (VP) subgroup.
](images/figures/constituency_parse_tree_example.png){#fig:constituency-parse-tree-example}

![
A visualization of a dependency parse tree using the following sentence: "BRCA1 is associated with breast cancer" [@10i1qMFbL].
For these type of trees the root begins with the main verb of the sentence.
Each arrows represents the dependency shared between two words.
For example, the dependency between BRCA1 and associated is nsubjpass, which stands for passive nominal subject.
This means that "BRCA1" is the subject of the sentence and it is being referred to by the word "associated".
](images/figures/dependency_parse_example.png){#fig:dependency-parse-tree-example}

#### Extracting Relationships Without Labels

Unsupervised extractors draw inferences from textual data without the use of annotated labels.
These methods involve some form of clustering or statistical calculations.
In this section we focus on methods that use unsupervised learning to extract relationships from text. 

An unsupervised extractor can exploit the fact that two entities may appear together in text.
This event is referred to as co-occurrence and studies that use this phenomenon can be found in Table {@tbl:unsupervised-methods-text-mining}.
Two databases DISEASES [@5gG8hwv7] and STRING [@iihNCsNX] were populated using a co-occurrence scoring method on PubMed abstracts, which measured the frequency of co-mention pairs within individual sentences as well as the abstracts themselves.
This technique assumes that each individual co-occurring pair is independent from one another.
Under this assumption mention pairs that occur more than expected were presumed to implicate the presence of an association or interaction.
This approach was able to identify 543,405 disease gene associations [@5gG8hwv7] and 792,730 high confidence protein protein interactions [@iihNCsNX], but is limited to only using PubMed abstracts.

Full text articles are able to dramatically enhance relationship detection [@DGlWGDEt; @pLAIFXqP].
Westergaard et al. used a co-occurrence approach, similar to DISEASES [@5gG8hwv7] and STRING [@iihNCsNX], to mine full articles for protein-protein interactions and other protein related information [@DGlWGDEt].
The authors discovered that full text provided better prediction power than using abstracts alone, which suggests that future text mining approaches should consider using full text to increase detection power.

Unsupervised extractors often treat different biomedical relationships as multiple isolated problems.
An alternative to this perspective is to capture all different types at once.
Clustering is an approach that accomplish this concept of simultaneous extraction.
Percha et al. used a biclustering algorithm on generated dependency parse trees to group sentences within PubMed abstract [@CSiMoOrI].
Each cluster was manually curated to determine which relationship each group represented.
This approach captured 4,451,661 dependency paths for 36 different groups [@CSiMoOrI].
Despite the success, this approach suffered from technical issues such as dependency tree parsing errors.
These errors resulted in some sentences not being captured by the clustering algorithm [@CSiMoOrI] and future clustering approaches should consider simplifying sentences to prevent this type of issue.

Overall unsupervised methods provide a means to rapidly extract relationship asserting sentences without the need of annotated text.
Approaches in this category range from calculating co-occurrence scores to clustering sentences and provide a generalizable framework that can be used on large repositories of text.
Full text has already been show to meaningfully improve the performance of methods that aim to infer relationships using cooccurrences [@DGlWGDEt], and we should expect similar benefits for machine learning approaches.
Furthermore, we expect that simplifying sentences would improve unsupervised methods and should considered as an initial preprocessing step.

| Study | Relationship of Interest | 
| --- | --- | 
| CoCoScore [@IGXdryzB] | Protein-Protein Interactions, Disease-Gene and Tissue-Gene Associations |
| Rastegar-Mojarad et al. [@ETC6lm7S] | Drug Disease Treatments |
| CoPub Discovery [@AdKPf5EO] | Drug, Gene and Disease interactions |
| Westergaard et al. [@DGlWGDEt]| Protein-Protein Interactions |
| DISEASES [@5gG8hwv7] | Disease-Gene associations|
| STRING [@q9Fhy8eq]| Protein-Protein Interactions |
| Singhal et al. [@10tWTMIaV] | Genotype-Phenotype Relationships |

Table: Table of approaches that mainly use a form of co-occurrence. {#tbl:unsupervised-methods-text-mining}

#### Supervised Relationship Extraction

Supervised extractors use labeled sentences to construct generalized patterns that bisect positive examples (sentences that allude to a relationship) from negative ones (sentences that do not allude to a relationship).
Most of these approaches have flourished due to pre-labelled publicly available datasets (Table {@tbl:supervised-text-datasets}).
These datasets were constructed by curators for shared open tasks [@16As8893j; @6wNuLZWb] or as a means to provide the scientific community with a gold standard [@L9IIm3Zd; @6wNuLZWb; @luGt8luc].
Approaches that use these available datasets range from using linear classifiers such as support vector machines (SVMs) to non-linear classifiers such as deep learning techniques.
The rest of this section discusses approaches that use supervised extractors to detect relationship asserting sentences.

Some supervised extractors involve the mapping of textual input into a high dimensional space.
SVMs are a type of classifier that can accomplish this task with a mapping function called a kernel [@iiQkIqUX; @1B0lnkj35].
These kernels take information such as a sentence's dependency tree [@i7KpvzCo; @3j1T67vB], part of speech tags [@iiQkIqUX] or even word counts [@1B0lnkj35] and map them onto a dense feature space.
Within this space, these methods construct a hyperplane that separates sentences in the positive class (illustrates a relationship) from the negative class (does not illustrate a relationship). 
Kernels can be manually constructed or selected to cater to the relationship of interest [@iiQkIqUX; @3j1T67vB;@1B0lnkj35; @1B0lnkj35].
Determining the correct kernel is a nontrivial task that requires expert knowledge to be successful.
In addition to single kernel methods, a recent study used an ensemble of SVMs to extract disease-gene associations [@GeCe9qfW].
This ensemble outperformed notable disease-gene association extractors [@jg0TGCov; @hbAqN08A] in terms of precision, recall and F1 score.
Overall, SVMs have been shown to be beneficial in terms of relationship mining; however, major focus has shifted to utilizing deep learning techniques which can perform non-linear mappings of high dimensional data.

Deep learning is an increasingly popular class of techniques that can construct their own features within a high dimensional space [@vDFZcSf9; @BeijBSRE].
These methods use different forms of neural networks, such as recurrent or convolutional neural networks, to perform classification.

Recurrent neural networks (RNN) are designed for sequential analysis and use a repeatedly updating hidden state to make predictions.
An example of a recurrent neural network is a long short-term memory (LSTM) network [@x4dbEYer].
Cocos et al. [@kCSge2o8] used a LSTM to extract drug side effects from de-identified twitter posts, while Yadav et al. [@hEblZ1j5] used an LSTM to extract protein-protein interactions.
Others have also embraced LSTMs to perform relationship extraction [@8lfvAUz7; @8NrcroGt; @k4sSP5gN; @1F5aZYjOB; @kCSge2o8]. 
Despite the success of these networks, training can be difficult as these networks are highly susceptible to vanishing and exploding gradients [@YYBiIF26; @789lze3k].
One proposed solution to this problem is to clip the gradients while the neural network trains [@FoztezBR].
Besides the gradient problem, these approaches only peak in performance when the datasets reach at least a tens of thousands of data points [@anpoBunY].

Convolutional neural networks (CNNs), which are widely applied for image analysis, use multiple kernel filters to capture small subsets of an overall image [@BeijBSRE].
In the context of text mining an image is replaced with words within a sentence mapped to dense vectors (i.e., word embeddings) [@1GhHIDxuW; @u5iJzbp9].
Peng et al. used a CNN to extract sentences that mentioned protein-protein interactions [@TNHJioqT] and Zhou et al. used a CNN to extract chemical-disease relations [@HS4ARwmZ].
Others have used CNNs and variants of CNNs to extract relationships from text [@1H4LpFrU0; @5LOkzCNK; @19fr9ZRrA].
Just like RNNs, these networks perform well when millions of labeled examples are present [@anpoBunY]; however, obtaining these large datasets is a non-trivial task.
Future approaches that use CNNs or RNNs should consider solutions to obtaining these large quantities of data through means such as weak supervision [@EHeTvZht], semi-supervised learning [@xWET58su] or using pre-trained networks via transfer learning [@12JtL2o6T; @YRDXK4f4].

Semi-supervised learning [@xWET58su] and weak supervision [@EHeTvZht] are techniques that can rapidly construct large datasets for machine learning classifiers. 
Semi-supervised learning trains classifiers by combining labeled data with unlabeled data.
For example, one study used a variational auto encoder with a LSTM network to extract protein-protein interactions from PubMed abstracts and full text [@hNMqMImK].
This is an elegant solution for the small dataset problem but requires labeled data to start. 
This dependency makes finding under-studied relationships difficult as one would need to find or construct examples of the missing relationships at the start.

Weak or distant supervision takes a different approach by using noisy or even erroneous labels to train classifiers [@EHeTvZht; @WYud0jQT; @vzoBuh4l; @9Jo1af7Z].
Under this paradigm sentences are labeled based on their mention pair being present (positive) or absent (negative) in a database and, once labeled, a machine learning classifier can be trained to extract relationships from text [@EHeTvZht].
For example, Thomas et al. [@kvlZD1mv] used distant supervision to train a SVM to extract sentences mentioning protein-protein interactions (PPI). 
Their SVM model achieved comparable performance against a baseline model; however, the noise generated via distant supervision was difficult to eradicate [@kvlZD1mv].
A number of efforts have focused on combining distant supervision with other types of labeling strategies to mitigate the negative impacts of noisy knowledge bases [@Kry87kzn; @M5UWoN93; @xy08BzDf].
Nicholson et al. [@19fr9ZRrA] found that, in some circumstances, these strategies can be reused across different types of biomedical relationships to learn a heterogeneous knowledge graph in cases where those relationships describe similar physical concepts.
Combining distant supervision with other types of labeling strategies remains an active area of investigation with numerous associated challenges and opportunities.
Overall, semi-supervised learning and weak supervision provide promising results in terms of relationship extraction and future approaches should consider using these paradigms to train machine learning classifiers.

| Dataset | Type of Sentences |
| --- | --- |
| AIMed [@YWh6tPj] | Protein-Protein Interactions |
| BioInfer [@DWpAeBxB] | Protein-Protein Interactions | 
| LLL [@szMMEMdC] | Protein-Protein Interactions |
| IEPA [@115pgEuOr] | Protein-Protein Interactions |
| HPRD5 [@L9IIm3Zd] | Protein-Protein Interactions |
| EU-ADR [@Y2DcwTrA] | Disease-Gene Associations |
| BeFree [@hbAqN08A] | Disease-Gene Associations |
| CoMAGC [@luGt8luc] | Disease-Gene Associations | 
| CRAFT [@1Du6MinB8] | Disease-Gene Associations |
| Biocreative V CDR [@6wNuLZWb] | Compound induces Disease |
| Biocreative IV ChemProt [@16As8893j] | Compound-Gene Bindings |

Table: A set of publicly available datasets for supervised text mining. {#tbl:supervised-text-datasets}


## Applying Knowledge Graphs to Biomedical Challenges

Knowledge graphs can help researchers tackle many biomedical tasks such as finding new treatments for existing drugs [@O21tn8vf], aiding efforts to diagnose patients [@10nDTiETi] and predicting associations between diseases and biomolecules [@YyPaovQ0].
In many cases, solutions rely on representing knowledges graphs in a low dimensional space, which is a process called representation learning.
This space preserves a knowledge graph's local and/or global structure and can support efforts to apply machine learning methods to make predictions.
In the next sections we review the unifying techniques that construct this low dimensional space and unifying applications that use this space to solve biomedical problems.

### Unifying Techniques

Mapping high dimensional data into a low dimensional space greatly improves modeling performance in fields such as natural language processing [@1GhHIDxuW; @u5iJzbp9] and image analysis [@j7KrVyi8].
The success of these approaches provides rationale for representing knowledge graphs into a low dimensional space [@DSiHGDz9].
Techniques that construct this representation often require information on how nodes are connected with one another [@18ZTxo1gJ; @u6NlpEUq; @dylXYFm6; @9F3iyg8e], while other approaches can work directly with the edges themselves [@E5xHFo4P].
We group these methods into the following three categories: matrix factorization, translational methods, and deep learning (Figure {@fig:unifying_techniques_overview}).

![
Pipeline for representing knowledge graphs in a low dimensional space.
Starting with a knowledge graph, this space can be generated using one of the following options: Matrix Factorization (a), Translational Models (b) or Deep Learning (c).
The output of this pipeline is an embedding space that clusters similar node types together.
](images/figures/unifying_techniques_overview.png){#fig:unifying_techniques_overview}

#### Matrix Factorization

Matrix factorization is a technique that uses linear algebra to map high dimensional data onto a low dimensional space.
This projection is accomplished by decomposing a matrix into a set of small rectangular matrices (Figure {@fig:unifying_techniques_overview} (a)).
Notable methods for matrix decomposition include Isomap [@13cvwdrYY], Laplacian eigenmaps [@MxPEnWF1] and Principal Component Analysis (PCA) [@sSbTaHau]/Singular Vector Decomposition (SVD) [@H0ez30Pz].
These methods were designed to be used on many different types of data; however, we discuss their use in the context of representing a knowledge graphs in a low dimensional space.	

SVD [@H0ez30Pz] is an algorithm that uses matrix factorization to portray knowledge graphs in a low dimensional space.
The input for this algorithm is an adjacency matrix ($A$), which is a square matrix where rows and columns represent nodes and each entry represents the presence of an edge between two nodes. 
This matrix ($A$) gets decomposed into three parts: a square matrix $Σ$ and a set of two small rectangular matrices $U$ and $V^{T}$.
This values within $Σ$ are called singular values, which are akin to eigenvalues [@H0ez30Pz].
Each row in $U$ and each column in $V^{T}$ represents nodes within a low dimensional space [@H0ez30Pz; @sSbTaHau].
In practice $U$ is usually used to represent nodes in a knowledge graph, but $V^{T}$ can also be used [@H0ez30Pz; @TFsQrgwM].
Typically, SVD appears in recommendation systems via collaborative filtering [@Z5VAJJmP]; however, this technique can also be used as a standalone baseline to compare to other approaches [@QcVYdxZu].

Laplacian eigenmaps is a technique that assumes there is low dimensional structure in a high dimensional space [@MxPEnWF1].
This algorithm preserves this structure while projecting data into a low dimensional space. 
Typically, the first step of this algorithm is to construct a figurative knowledge graph where nodes represent datapoints and edges are constructed based on similarity of two datapoints; however, in this context, the knowledge graph has already been defined.
The next step in this algorithm is to obtain both an adjacency matrix ($A$) and a degree matrix ($D$) from the knowledge graph.
A degree matrix is a diagonal matrix where each entry represents the number of edges connected to a node.
The adjacency and degree matrices are converted into a laplacian matrix ($L$), which is a matrix that shares the same properties as the adjacency matrix.
The laplacian matrix is generated by subtracting the adjacency matrix from the degree matrix ($L=D-A$) and, once constructed, the algorithm uses linear algebra to calculate the laplacian's eigenvalues and eigenvectors ($Lx = \lambda Dx$).
The generated eigenvectors represent the knowledge graph's nodes represented in a low dimensional space [@MxPEnWF1].
Other efforts have used variants of this algorithm to construct their own low dimensional representations of knowledge graphs [@18ZTxo1gJ; @u6NlpEUq; @KzDGRrSP].
Typically, eigenmaps work well when knowledge graphs have a sparse number of edges between nodes but struggle when presented with denser networks [@QcVYdxZu; @FE8pyO0l; @KzDGRrSP].
An open area of exploration is to adapt these methods to accommodate knowledge graphs that have a large number of edges.

Matrix factorization is a powerful technique that uses a matrices such as  an adjacency matrix as input.
Common approaches involve using SVD, Laplacian eigenmaps or variants of the two to construct low dimensional representations.
Despite reported success, the dependence on matrices like an adjacency matrix creates an issue of scalability as matrices of large networks would take too much memory for a regular computer to operate well.
Furthermore, these methods treat all edge types the same, but a possible extension is to incorporate node and edge types as sources of input.

#### Translational Distance Models

Translational distance models treat edges in a knowledge graph as linear transformations.
For example, one such algorithm, TransE [@mGBbZq62], treats every node-edge pair as a triplet with head nodes represented as $\textbf{h}$, edges represented as $\textbf{r}$, and tail nodes represented as $\textbf{t}$.
These representations are combined into an equation that mimics the iconic word vectors translations ($\textbf{king} - \textbf{man} + \textbf{woman} \approx \textbf{queen}$) from the word2vec model [@u5iJzbp9].
The described equation is shown as follows: $\textbf{h} + \textbf{r} \approx \textbf{t}$.
Starting at the head node ($\textbf{h}$), one adds the edge vector ($\textbf{r}$) and the result should be the tail node ($\textbf{t}$).
TransE optimizes vectors for $\textbf{h}$, $\textbf{r}$, $\textbf{t}$, while guaranteeing the global equation ($\textbf{h} + \textbf{r} \approx \textbf{t}$) is satisfied [@mGBbZq62].
A caveat to the TransE approach is that it forces relationships to have a one to one mapping, which may not be appropriate for all relationship types.

Wang et al. attempted to resolve the one to one mapping issue by developing the TransH model [@nprR5cVj].
TransH treats relations as hyperplanes rather than a regular vector and projects the head ($\textbf{h}$) and tail ($\textbf{t}$) nodes onto a hyperplane.
Following this projection, a distance vector ($\textbf{d}_{r}$) is calculated between the projected head and tail nodes.
Finally, each vector is optimized while preserving the global equation: $\textbf{h} + \textbf{d}_{r} \approx \textbf{t}$ [@nprR5cVj].
Other effots have built off of the TransE and TransH models [@R8kotaKY, @E5xHFo4P; @BRGxlTb9]. 
In the future, it may be beneficial for these models to incorporate other types of information such as edge confidence scores, textual information, or edge type information when optimizing these distance models.

#### Deep Learning

Deep learning is a paradigm that uses multiple non-linear transformations to map high dimensional data into a low dimensional space.
Many techniques that use deep learning on knowledge graphs are based on word2vec [@u5iJzbp9; @1GhHIDxuW], a set of approaches that are widely used for natural language processing.
The goal of word2vec is to project words onto a low dimensional space that preserves their semantic meaning.
Strategies for training word2vec models use one of two neural network architectures: skip-gram and continuous bag of words (CBOW).
Both models are feed-forward neural networks, but CBOW models are trained to predict a word given its context while skip-gram models are trained to predict the context given a word [@u5iJzbp9; @1GhHIDxuW].
Once training has finished, words are now associated with dense vectors that downstream models, such as feed forward networks or recurrent networks, can use for input.

Deepwalk is an early method that represents knowledge graphs in a low dimensional space [@ViMmBmL6]. 
The first step of this method is to perform a random walk along a knowledge graph.
During the random walk, every generated sequence of nodes is recorded and treated as a sentence in word2vec [@u5iJzbp9; @1GhHIDxuW].
After every node has been processed, a skip-gram model is trained to predict the context of each node thereby constructing a low dimensional representation of a knowledge graph [@ViMmBmL6].
A limitation for deepwalk is that the random walk cannot be controlled, so every node has an equal chance to be reached.
Grover and Leskovec demonstrated that this limitation can hurt performance when classifying edges between nodes and developed node2vec as a result [@PD4udqRe].
Node2vec operates the in the same fashion as deepwalk; however, this algorithm specifies a parameter that lets the random walk be biased when traversing nodes [@PD4udqRe].
A caveat to both deepwalk and node2vec is that they ignore information such as edge type and node type.
Various approaches have evolved to fix this limitation by incorporating  node, edge and even path types when representing knowledge graphs in a low dimensional space [@12mzC63eD; @1AeZs6xaT; @1G1nukcFt; @eSGflyQ5].
An emerging area of work is to develop approaches that capture both the local and global structure of a graph when constructing this low dimensional space.

Instead of using the word2vec framework, some deep learning approaches use an adjacency matrix as input [@u5iJzbp9; @1GhHIDxuW].
These approaches use neural networks called autoencoders to generate this low dimensional space [@1H8Rd6pHW; @hjIIetVM; @1A6Dhbwkr].
Autoencoders map input such as an adjacency matrices into a low dimensional space and then determines how to construct this space via reconstructing the same input [@BQS8ClV0; @1ErNQZjBt].
This generated space represents the nodes and their connectivity structure within a knowledge graph [@1H8Rd6pHW; @hjIIetVM; @1A6Dhbwkr].
Despite the high potential of this approach, this method relies on an adjacency matrix for input which can run into scalability issues as a knowledge graph asymptotically increases in size [@RjwcaMhj].
Plus, Khosla et al. discovered that approaches akin to node2vec outperformed algorithms using autoencoders when undergoing link prediction and node classification [@RjwcaMhj].
Overall, the performance of deep learning techniques largely depends upon the structure of nodes and edges within a knowledge graph [@RjwcaMhj].
Future work should include hybrid models that use both node2vec and autoencoders to construct complementary low dimensional representations of knowledge graphs.

### Unifying Applications

Knowledge graphs have been applied to many biomedical challenges ranging from identifying proteins' functions [@1EP2NrAhl] to prioritizing cancer genes [@17R6q0KTd] to recommending safer drugs to patients [@aLsdEzlV; @8vj5v8un] (Figure {@fig:unifying_applications}).
In this section we review how knowledge graphs are applied in biomedical settings and put particular emphasis on an emerging set of techniques that represent knowledge graphs in a low dimensional space.

![
Overview of various biomedical applications that make use of knowledge graphs.
Categories consist of: (a) Multi-Omic applications, (b) Pharmaceutical Applications and (c) Clinical Applications.
](images/figures/unifying_applications_overview.png){#fig:unifying_applications}

#### Multi-Omic Applications

Multi-omic applications employ knowledge graphs to study the genome, how genes are expressed in the transcriptome, and how the products of those transcripts interact in the proteome.
These graphs are used to establish connections between -omic entities as well as diseases.
Tasks in this context include gene-symptom prioritization [@otY29wFV], protein-protein interaction prediction [@6O3BO6WO; @Y2RTnbCe] and detecting miRNA-disease associations [@YyPaovQ0].
We focus specifically on multi-omic applications that represent knowledge graphs in a low dimensional space to make connections.

Recommendation systems make use of knowledge graphs to establish links between RNA with disease and proteins with other proteins.
Shen et al. used an algorithm called collaborative filtering to establish an association between miRNA and diseases [@YyPaovQ0].
The authors constructed a miRNA-Disease network using the Human MicroRNA Disease database (HMDD) [@1F18ycwfS] and generated an adjacency matrix with the rows representing miRNA and the columns representing diseases.
This matrix was decomposed into small rectangular matrices using SVD, then these small matrices were used to calculate similarity scores between miRNAs and diseases.
High scores implied a high likelihood that a given miRNA had an association with a given disease [@YyPaovQ0].
Other approaches built off of Shen et al.'s work by incorporating novel ways to perform matrix factorization [@1DjgsuPV2; @hZ2R5BRj;@4xcJzyPc] or by integrating machine learning models in conjunction with matrix factorization [@icSe8Yyw].
These approaches achieved high area under the receiver operating curve (AUROC), but new discoveries have been hard to validate as experiments in this space are costly and time consuming at best [@YyPaovQ0].
Apart from miRNA, collaborative filtering has been used to predict protein-protein interactions [@6FrpIkNZ; @6O3BO6WO; @Y2RTnbCe].
Although extensive validation of newly generated candidates may be impractical, it would be helpful to see future efforts in this space include a blinded literature search for prioritized and randomly selected candidates as part of the standard evaluation pipeline.

Applications of deep learning techniques have mainly used the node2vec model [@PD4udqRe] or variants of it.
Yang et al. used node2vec to create a recommendation system to infer associations between genes and disease symptoms [@otY29wFV].
The authors constructed a gene-disease symptom knowledge graph by combining two bipartite graphs: genes with diseases and diseases with disease symptoms.
The generated graph was embedded via node2vec and similarity scores were calculated for every gene-symptom pair in the graph.
High scores implied a high likelihood of an association [@otY29wFV].
This approach outperformed methods that didn't use a knowledge graph; however, validation was difficult as it involved manual curation of the literature [@otY29wFV].
Similar approaches used variants of node2vec to predict gene-disease associations
[@1D9FTzRBg; doi:10.3389/fgene.2019.00226 @6PISrkV5; @taI1UUAE] analyze RNA-seq data [@qbHGtxhA] and infer novel protein information [@QQtRw08H; @8qB2oCgy; @RYW74Wvh; @1EP2NrAhl].

Knowledge graphs benefited the multi-omics field as a resource for generating novel discoveries.
Most approaches to date use matrix factorization and node2vec to project knowledge graph into a low dimensional space, while translational models (Figure {@fig:unifying_techniques_overview} (b)) may be an untapped resource that could aid future efforts.
Another area of exploration could be incorporating multiple sources of information such as compounds, anatomic locations or genetic pathways to improve the specificity of findings (i.e., to predict that a protein-protein interaction happens in a specific cell type or tissue).

#### Pharmaceutical Applications

There are a multitude of examples where knowledge graphs have been applied to identify new properties of drugs.
Tasks in this field involve predicting drugs interacting with other drugs [@NnOS86ev], identifying molecular targets a drug might interact with [@11ua4nEkY] and identifying new disease treatments for previously established drugs [@sj2fr8fp].
In this section we concentrate on applications that apply these graphs to discover new properties of drugs and focus on approaches that use these graphs in a low-dimensional space.

Similar to multi-omic applications, recommendation systems have utilized knowledge graphs to infer novel links between drugs and diseases.
Dai et al. used collaborative filtering to infer drug-disease associations [@11ua4nEkY].
The authors constructed a drug-disease network by integrating two bipartite networks: a drug-gene interaction network and a disease-gene interaction network.
They integrated both networks under the assumption that drugs associated with a disease interact with the same gene of interest. 
Following construction, the authors generated an adjacency matrix where rows represent drugs and columns represent diseases.
This matrix was decomposed into two small rectangular matrices and these matrices were used to calculate similarity scores between all drugs and all diseases.
High values implied a high chance of an association [@11ua4nEkY].
Related approaches used this technique to infer drug-target interactions [@S0MrOfj0; @HOrwJFzW; @Z391qdG0] and drug-disease treatments [@dbgPwLaZ; @94kKAy9w; @oKdMo9U9; @16FEYidu2; @18YRZaX7n].
In spite of reported success, these approaches are limited to the drugs and diseases contained in the graph.
Combining these approaches with representations of chemical structures might make it possible to one day make predictions about novel compounds.

Applications that use deep learning techniques have used node2vec [@19E33rJiu; @dR3gjJXP] and autoencoders [@za8DCIPS; @PYqNAHh7] approaches to represent knowledge graphs in a low dimensional space.
Zong et al. used a node2vec-like model to predict drug-target associations [@19E33rJiu].
The authors constructed a disease-target-disease network using drug centered databases: Drugbank [@111FgvD8J] and Diseasome [@14fs7pzn0].
Next, the authors applied a random walk to the graph and trained a skip-gram model to generate a low dimensional representation of the graph.
Lastly, the authors constructed a similarity metric that used this space to rank how similar drugs are to their targets [@19E33rJiu].
A limitation to this approach is that their graph is missing information such as pharmacological class or drug chemical structure that could improve prediction performance.
Overall, deep learning provides a robust set of techniques that have been shown to outperform most linear approaches in this context [@245Px4P3; @WMEox1CM].

Applications that discover new properties of drugs have benefited from using knowledge graphs as a resource.
Most methods to date use matrix factorization and deep learning techniques to produce a low-dimensional representation.
Due to the success of deep learning [@245Px4P3; @WMEox1CM] much of the field's focus has shifted to these techniques; however, a possible improvement is to use an ensemble of deep learning techniques and linear methods to improve performance.
Another potential avenue for future work would be to incorporate entity-specific hierarchical information or similarity information to improve detection power.
For drugs, this could include pharmaceutical classes or chemical structure similarities.

#### Clinical applications

Clinical applications that use knowledge graphs are in early stages of development, but the long-term goal is to use analyses of these graphs to aid patient care.
Typically, graphs for these applications are constructed from electronic health records (EHR): nodes represent patients, drugs and diseases while edges represent relationships such as a patient being prescribed a treatment or a patient being diagnosed with a disease [@xNv4Rkif; @mrfQbq3g; @xU6Ims3W; @gddb9uXr].
Tasks within this field range from improving patient diagnoses [@UuF5A9Pu;@OCnhKscH] to recommending safer drugs for patients [@aLsdEzlV; @OCnhKscH] and we briefly discuss efforts that use knowledge graphs to accomplish such tasks.

Early work in this field applied translational models (Figure {@fig:unifying_techniques_overview} (b)) to knowledge graphs with the goal of recommending safe drugs.
Wang et al. used a variant of the TransH [@nprR5cVj] model to create such a system for patients [@aLsdEzlV].
They constructed a disease-patient-drug network by integrating a patient-disease bipartite network with a patient-drug bipartite network.
Every node in the newly constructed graph was embedded while satisfying the following equation: $\textbf{h} - \textbf{r} \approx \textbf{t}$.
Following the embedding step, the authors formulated their own similarity metric that selected drug combinations with a low number of interactions [@aLsdEzlV].
Researchers in [@BRGxlTb9] applied a similar variant of the TransH model to a medical knowledge graph and evaluated their model for link prediction rather than patient recommendation.

In contrast with most applications where node2vec and autoencoder models have become established, deep learning methods in this field have focused on using graph attention models [@Exfv0f4l].
These models mimic machine translation models [@haHzVaaz] and aim to simultaneously represent knowledge graphs in a low dimensional space and perform the task at hand.
Choi et al. used a graph attention model to predict patient diagnoses [@10nDTiETi].
The authors constructed a directed graph using medical concepts from patient EHR data.
This directed graph was fed into a graph attention network and then used to predict a patient's likelihood of heart failure [@10nDTiETi].
Other approaches have used graph attention models to perform clinical tasks such as drug safety recommendations [@8vj5v8un] and patient diagnoses [@QNJ3b5bY].

Knowledge graphs have shown promising results when used for clinical applications; however, there is still room for improvement.
Most approaches have run into the common problem of missing data within EHR [@10nDTiETi; @aLsdEzlV; @8vj5v8un].
Future directions for the field consist of designing algorithms that can fill in this missing data gap or construct models that can take missing data into account.


## Conclusion

Knowledge graphs are becoming widely used in biomedicine, and we expect their use to continue to grow.
At the moment, most are constructed from databases derived from manual curation or from co-occurrences in text.
However, we expect that machine learning approaches will play a key role in quickly bringing new findings into these graphs.
Representing these knowledge graphs in a low dimensional space that captures a graph's local and global structure can enable many downstream machine learning analyses, and methods to capture this structure are an active area of research.

As with any field, rigorous evaluation that can identify key factors that drive success is critical to moving the field forward.
In regard to knowledge graphs, evaluation remains hard.
Experiments in this context require a significant amount of time and consequently resources [@otY29wFV; @YyPaovQ0].
Moving from open ended and uncontrolled evaluations that consist of describing findings that are consistent with the literature to blinded evaluations of the literature that corroborate predictions and non-predictions would be a valuable first step.
There are also well-documented biases related to node degree and degree distribution that must be considered for accurate evaluation [@17QDcGqUi].
Furthermore, the diversity of applications hinders the development of a standardized set of expected evaluations.

We anticipate that a fruitful avenue of research will be techniques that can produce low dimensional representations of knowledge graphs that distinguish between multple node and edge types.
There are also many different sources of bias that lead to spurious edges or incompleteness, and modeling these may support better representations.
It is a promising time for research into the construction and application of knowledge graphs.
The peer reviewed literature is growing at an increasing rate and maintaining a complete understanding is becoming increasingly challenging for scientists.
One path that scientists can take to maintain complete awareness is to become hyper-focused on specific areas of knowledge graph literature.
If advances in how these graphs are constructed, represented, and applied can enable the linking of fields, we may be able to savor the benefits of this detailed knowledge without losing the broader contextual links.


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>
