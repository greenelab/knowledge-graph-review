---
author-meta:
- David Nicholson
- Casey S. Greene
bibliography:
- content/manual-references.json
date-meta: '2020-05-22'
header-includes: '<!--

  Manubot generated metadata rendered from header-includes-template.html.

  Suggest improvements at https://github.com/manubot/manubot/blob/master/manubot/process/header-includes-template.html

  -->

  <meta name="dc.format" content="text/html" />

  <meta name="dc.title" content="Constructing Knowledge Graphs and Their Biomedical Applications" />

  <meta name="citation_title" content="Constructing Knowledge Graphs and Their Biomedical Applications" />

  <meta property="og:title" content="Constructing Knowledge Graphs and Their Biomedical Applications" />

  <meta property="twitter:title" content="Constructing Knowledge Graphs and Their Biomedical Applications" />

  <meta name="dc.date" content="2020-05-22" />

  <meta name="citation_publication_date" content="2020-05-22" />

  <meta name="dc.language" content="en-US" />

  <meta name="citation_language" content="en-US" />

  <meta name="dc.relation.ispartof" content="Manubot" />

  <meta name="dc.publisher" content="Manubot" />

  <meta name="citation_journal_title" content="Manubot" />

  <meta name="citation_technical_report_institution" content="Manubot" />

  <meta name="citation_author" content="David Nicholson" />

  <meta name="citation_author_institution" content="Department of Systems Pharmacology and Translational Therapeutics, University of Pennsylvania" />

  <meta name="citation_author_orcid" content="0000-0003-0002-5761" />

  <meta name="twitter:creator" content="@None" />

  <meta name="citation_author" content="Casey S. Greene" />

  <meta name="citation_author_institution" content="Department of Systems Pharmacology and Translational Therapeutics, Perelman School of Medicine, University of Pennsylvania" />

  <meta name="citation_author_institution" content="Childhood Cancer Data Lab, Alex&#39;s Lemonade Stand Foundation" />

  <meta name="citation_author_orcid" content="0000-0001-8713-9213" />

  <meta name="twitter:creator" content="@greenescientist" />

  <link rel="canonical" href="https://greenelab.github.io/knowledge-graph-review/" />

  <meta property="og:url" content="https://greenelab.github.io/knowledge-graph-review/" />

  <meta property="twitter:url" content="https://greenelab.github.io/knowledge-graph-review/" />

  <meta name="citation_fulltext_html_url" content="https://greenelab.github.io/knowledge-graph-review/" />

  <meta name="citation_pdf_url" content="https://greenelab.github.io/knowledge-graph-review/manuscript.pdf" />

  <link rel="alternate" type="application/pdf" href="https://greenelab.github.io/knowledge-graph-review/manuscript.pdf" />

  <link rel="alternate" type="text/html" href="https://greenelab.github.io/knowledge-graph-review/v/a35fa6b9aab0f9ec2fd899175248313ccdf0b7d7/" />

  <meta name="manubot_html_url_versioned" content="https://greenelab.github.io/knowledge-graph-review/v/a35fa6b9aab0f9ec2fd899175248313ccdf0b7d7/" />

  <meta name="manubot_pdf_url_versioned" content="https://greenelab.github.io/knowledge-graph-review/v/a35fa6b9aab0f9ec2fd899175248313ccdf0b7d7/manuscript.pdf" />

  <meta property="og:type" content="article" />

  <meta property="twitter:card" content="summary_large_image" />

  <link rel="icon" type="image/png" sizes="192x192" href="https://manubot.org/favicon-192x192.png" />

  <link rel="mask-icon" href="https://manubot.org/safari-pinned-tab.svg" color="#ad1457" />

  <meta name="theme-color" content="#ad1457" />

  <!-- end Manubot generated metadata -->'
keywords:
- knowledge-graphs
- network-embeddings
- text-mining
- natural-language-processing
- deep-learning
- machine-learning
- literature-review
lang: en-US
manubot-clear-requests-cache: false
manubot-output-bibliography: output/references.json
manubot-output-citekeys: output/citations.tsv
manubot-requests-cache-path: ci/cache/requests-cache
title: Constructing Knowledge Graphs and Their Biomedical Applications
...






<small><em>
This manuscript
([permalink](https://greenelab.github.io/knowledge-graph-review/v/a35fa6b9aab0f9ec2fd899175248313ccdf0b7d7/))
was automatically generated
from [greenelab/knowledge-graph-review@a35fa6b](https://github.com/greenelab/knowledge-graph-review/tree/a35fa6b9aab0f9ec2fd899175248313ccdf0b7d7)
on May 22, 2020.
</em></small>

## Authors



+ **David Nicholson**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0003-0002-5761](https://orcid.org/0000-0003-0002-5761)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [danich1](https://github.com/danich1)<br>
  <small>
     Department of Systems Pharmacology and Translational Therapeutics, University of Pennsylvania
     · Funded by The Gordon and Betty Moore Foundation (GBMF4552); The National Institutes of Health (T32 HG000046)
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
     · Funded by The Gordon and Betty Moore Foundation (GBMF4552); The National Institutes of Health (R01 HG010067)
  </small>



## Abstract {.page_break_before}

Knowledge graphs can support many biomedical applications.
These graphs represent biomedical concepts and relationships in the form of nodes and edges.
In this review, we discuss how these graphs are constructed and applied with a particular focus on how machine learning approaches are changing these processes.
Biomedical knowledge graphs have often been constructed by integrating databases that were populated by experts via manual curation, but we are now seeing a more robust use of automated systems.
A number of techniques are used to represent knowledge graphs, but often machine learning methods are used to construct a low-dimensional representation that can support many different applications.
This representation is designed to preserve a knowledge graph’s local and/or global structure.
Additional machine learning methods can be applied to this representation to make predictions within genomic, pharmaceutical, and clinical domains.
We frame our discussion first around knowledge graph construction and then around unifying representational learning techniques and unifying applications.
Advances in machine learning for biomedicine are creating new opportunities across many domains, and we note potential avenues for future work with knowledge graphs that appear particularly promising.


## Introduction

Graphs are practical resources for many real-world applications.
They have been used in social network mining to classify nodes [@doi:10.1007/978-1-4419-8462-3_5] and create recommendation systems [@doi:10.1145/3184558.3186904].
They have also been used in natural language processing to interpret simple questions and use relational information to provide answers [@arxiv:1404.4326; @doi:10.1145/3038912.3052675].
In a biomedical setting, graphs have been used to prioritize genes relevant to disease [@pmid:21121028; @doi:10.1101/651000; @doi:10.1109/CIBCB.2019.8791472; @doi:10.1093/bioinformatics/bty559], perform drug repurposing [@doi:10.7554/eLife.26726] and identify drug-target interactions [@doi:10.1371/journal.pcbi.1002574].

Within a biomedical setting, some graphs can be considered knowledge graphs; although, precisely defining a knowledge graph is difficult because there are multiple conflicting definitions [@raw:KG_DEF].
For this review, we define a biomedical knowledge graph as the following: a resource that integrates one or more expert-derived sources of information into a graph where nodes represent biomedical entities and edges represent relationships between two entities.
This definition is consistent with other definitions found in the literature [@doi:10.3233/SW-160218;@doi:10.1109/MIC.2019.2928449;@doi:10.1016/j.eswa.2019.112948;@doi:10.1109/MSN.2016.030;@doi:10.1109/jproc.2015.2483592;@doi:10.1145/1242572.1242667;@doi:10.1109/TKDE.2017.2754499].
Often relationships are considered unidirectional (e.g., a compound treats a disease, but a disease cannot treat a compound); however, there are cases where relationships can be considered bidirectional (e.g., a compound resembles another compound, or a gene interacts with another gene).
A subset of graphs that meet our definition of a knowledge graph would be unsuitable for applications such as symbolic reasoning [@doi:10.1007/978-0-585-29599-2_11]; however, we chose a more liberal definition because it has been demonstrated that these broadly defined graphs have numerous uses throughout the literature.
For example, Hetionet (Figure {@fig:hetionet_schema}) [@doi:10.7554/eLife.26726] would be considered a biomedical knowledge graph by this definition, and it has been used to identify drug repurposing opportunities [@doi:10.7554/eLife.26726].
We do not consider databases like DISEASES [@doi:10.1016/j.ymeth.2014.11.020] and DrugBank [@doi:10.1093/nar/gkx1037] to be knowledge graphs.
Although these resources contain essential information, they do not represent their data in the form of a graph.

Biomedical knowledge graphs are often constructed from manually curated databases [@doi:10.7554/eLife.26726; @doi:10.1371/journal.pcbi.1002574; @doi:10.1038/s41467-017-00680-8; @doi:10.1186/s12859-016-1336-7; @doi:10.1016/j.jbi.2011.11.017].
These databases provide previously established information that can be incorporated into a graph.
For example, a graph using DISEASES [@doi:10.1016/j.ymeth.2014.11.020] as a resource would have genes and diseases as nodes, while edges added between nodes would represent an association between a gene and a disease.
This example shows a single type of relationship; however, there are graphs that use databases with multiple relationships [@doi:10.7554/eLife.26726; @doi:10.1016/j.jbi.2008.03.004].
In addition to manual curation, other approaches have used natural language processing techniques to construct knowledge graphs [@doi:10.1186/s12859-015-0549-5; @doi:10.1007/s10115-019-01351-4].
One example used a text mining system to extract sentences that illustrate a protein's interaction with another protein [@doi:10.1016/j.knosys.2018.11.020].
Once identified, these sentences can be incorporated as evidence to establish an edge in a knowledge graph.

In this review we describe various approaches for constructing and applying knowledge graphs in a biomedical setting.
We discuss the pros and cons of constructing a knowledge graph via manually curated databases and via text mining systems.
We also compare assorted approaches for applying knowledge graphs to solve biomedical problems.
Lastly, we conclude on the practicality of knowledge graphs and point out future applications that have yet to be explored.

![
The metagraph (i.e., schema) of the knowledge graph used in the Rephetio project [@doi:10.7554/eLife.26726].
The authors of this project refer to their resource as a heterogenous network (i.e., hetnet), and this network meets our definition of a knowledge graph.
This resource depicts pharmacological and biomedical information in the form of nodes and edges. 
The nodes (circles) represent entities and edges (lines) represent relationships that are shared between two entities.
The majority of edges in this metagraph are depicted as unidirectional, but some relationships can be considered bidirectional.
](https://raw.githubusercontent.com/hetio/het.io/e1ca4fd591e0aa01a3767bbf5597a910528f6f86/about/metagraph.png){#fig:hetionet_schema}


## Building Biomedical Knowledge Graphs

Knowledge graphs can be constructed in many ways using resources such as pre-existing databases or text.
Usually, knowledge graphs are constructed using pre-existing databases. 
These databases are constructed by domain experts using approaches ranging from manual curation to automated techniques, such as text mining.
Manual curation is a time-consuming process that requires domain experts to read papers and annotate sentences that assert a relationship.
Automated approaches rely on machine learning or natural language processing techniques to rapidly detect sentences of interest.
We categorize these automated approaches into the following groups: rule-based extraction, unsupervised machine learning, and supervised machine learning and discuss examples of each type of approach while synthesizing their strengths and weaknesses.

### Constructing Databases and Manual Curation

Database construction dates back all the way to 1956 when the first database contained a protein sequence of the insulin molecule [@doi:10.4172/jcsb.1000081].
The process of database construction involves gathering relevant text such as journal articles, abstracts, or web-based text and having curators read the gathered text to detect sentences that implicate a relationship (i.e., relationship extraction).
Notable databases constructed by this process can be in found in Table {@tbl:manual-curated-databases}.
An example database, COSMIC [@doi:10.1093/nar/gkw1121] was constructed by a group of domain experts scanning the literature for key cancer related genes.
This database contained approximately 35M entries in 2016 [@doi:10.1093/nar/gkw1121] and by 2018 had grown to 45M entries [@doi:10.1093/nar/gky1015].
Studies have shown that databases constructed in this fashion contain relatively precise data but the recall is low [@doi:10.1038/nmeth1209-860; @doi:10.1038/nmeth.1284; @doi:10.1093/database/bau058; @doi:10.1093/nar/gku1205; @doi:10.1186/s12859-018-2103-8; @doi:10.1093/database/bax043; @doi:10.1093/bioinformatics/btm229].
Low recall happens because the publication rate is too high for curators to keep up [@doi:10.1007/s11192-010-0202-z].
This bottleneck highlights a critical need for future approaches to scale fast enough to compete with the increasing publication rate.

Semi-automatic methods are a way to accelerate the curation process [@doi:10.1016/j.jbi.2010.11.001; @doi:10.1093/database/bau067; @doi:10.1093/database/bas010; @doi:10.1145/3269206.3269229; @doi:10.1093/database/baz068; @doi:10.1186/s12859-018-2103-8; @doi:10.1186/s12859-018-2021-9].
The first step of these methods is to use an automated system to initially extract sentences from text.
This process removes irrelevant sentences, which dramatically decreases the amount of text that curators must sift through.
Following the pre-filtering step, curators then approve or reject the remaining sentences.
This approach saved curators an average of 2-2.8 hours compared to manual efforts [@doi:10.1016/j.jbi.2010.11.001; @doi:10.1136/amiajnl-2013-001837]. 
Despite automated systems excelling in identifying sentences for commonly occurring relationships, they tend to miss lesser-known relationships [@doi:10.1016/j.jbi.2010.11.001].
These systems also have a hard time parsing ambiguous sentences that naturally occur in text, which makes correcting them a challenging task [@doi:10.1016/j.jbi.2010.11.001].
Given these caveats, future approaches should look into using techniques that simplify sentences to solve the ambiguity issue [@doi:10.1093/database/bau038; @pmid:21346999].

Despite the negatives of manual curation, it is still an essential process for extracting relationships from text.
This process can be used to generate gold standard datasets that automated systems use for validation [@doi:10.1016/j.jbi.2012.04.004; @doi:10.1016/j.artmed.2004.07.016] and can be used during the training process of these systems (i.e., active learning) [@doi:10.1007/s11390-012-1306-0].
It is important to remember that manual curation alone is precise but results in low recall rates [@doi:10.1093/bioinformatics/btm229].
Future databases should consider initially relying on automated methods to obtain sentences at an acceptable recall level, then incorporate manual curation as a way to fix or remove irrelevant results.

| Database [Reference] | Short Description | Number of Entries | Entity  Types | Relationship Types | Method of Population |
| --- | --- | --- | --- | --- | --- |
| BioGrid [@doi:10.1093/nar/gks1158] | A database for major model organisms. It contains genetic and proteomic information.| 572,084 | Genes, Proteins| Protein-Protein interactions | Semi-automatic methods |
| Comparative Toxicogenomics Database [@doi:10.1093/nar/gky868] | A database that contains manually curated chemical-gene-disease interactions and  relationships. | 2,429,689 | Chemicals (Drugs), Genes, Diseases | Drug-Genes, Drug-Disease, Disease-Gene mappings | Manual curation and Automated systems |
| Comprehensive Antibiotic Resistance Database [@doi:10.1093/nar/gkw1004] | Manually curated database that contains information about the molecular basis of antimicrobial resistance. | 174,443 | Drugs, Genes, Variants | Drug-Gene, Drug-Variant mappings | Manual curation |
| COSMIC [@doi:10.1093/nar/gkw1121] | A database that contains high resolution human cancer genetic information. | 35,946,704 | Genes, Variants, Tumor Types| Gene-Variant Mappings | Manual Curation |
| Entrez-Gene [@doi:10.1093/nar/gkq1237] | NCBI's Gene annotation database that contains information pertaining to genes, gene's organism source, phenotypes etc. | 7,883,114 | Genes, Species and Phenotypes | Gene-Phenotypes and Genes-Species mappings | Semi-automated curation |
| OMIM [@pmid:30445645] | A database that contains phenotype and genotype information | 25,153 | Genes, Phenotypes | Gene-Phenotype mappings | Manual Curation |
| PharmGKB [@doi:10.1038/clpt.2012.96] | A database that contains genetic, phenotypic, and clinical information related to pharmacogenomic studies. | 43,112 | Drugs, Genes, Phenotypes, Variants, Pathways | Gene-Phenotypes, Pathway-Drugs, Gene-Variants, Gene-Pathways | Manual Curation and Automated Methods |
| UniProt [@doi:10.1093/nar/gky1049] | A protein-protein interaction database that contains proteomic information. | 560,823 | Proteins, Protein sequences | Protein-Protein interactions | Manual and Automated Curation |

Table: A table of databases that used a form of manual curation to populate entries. 
Reported number of entities and relationships are relative to the time of publication.
{#tbl:manual-curated-databases}

### Text Mining for Relationship Extraction

#### Rule-Based Relationship Extraction

Rule-based extraction consists of identifying essential keywords and grammatical patterns to detect relationships of interest. 
Keywords are established via expert knowledge or through the use of pre-existing ontologies, while grammatical patterns are constructed via experts curating parse trees. 
Parse trees are tree data structures that depict a sentence's grammatical structure and come in two forms: a constituency parse tree (Figure {@fig:constituency-parse-tree-example}) and a dependency parse tree (Figure {@fig:dependency-parse-tree-example}).
Both trees use part of speech tags, labels that dictate the grammatical role of a word such as noun, verb, adjective, etc., for construction, but represent the information in two different forms.
Constituency parse trees break a sentence into subphrases (Figure {@fig:constituency-parse-tree-example}) while dependency path trees analyze the grammatical structure of a sentence (Figure {@fig:dependency-parse-tree-example}).
Many text mining approaches [@doi:10.1093/database/bay108; @doi:10.1093/bioinformatics/btw503; @doi:10.1186/s13326-017-0168-3] use such trees to generate features for machine learning algorithms and these approaches are discussed in later sections.
In this section we focus on approaches that use rule-based extraction as a primary strategy to detect sentences that allude to a relationship.

Grammatical patterns can simplify sentences for easy extraction [@pmid:21346999; @pmid:24850848].
Jonnalagadda et al. used a set of grammar rules inspired by constituency trees to reshape complex sentences with simpler versions [@pmid:21346999] and these simplified versions were manually curated to determine the presence of a relationship.
By simplifying sentences, this approach achieved high recall, but had low precision [@pmid:21346999].
Other approaches used simplification techniques to make extraction easier [@doi:10.1093/database/baw156; @doi:10.1186/1471-2105-15-285; @doi:10.1093/database/bav020; @doi:10.1371/journal.pcbi.1004391].
Tudor et al. simplified sentences to detect protein phosphorylation events [@doi:10.1093/database/bav020].
Their sentence simplifier broke complex sentences that contain multiple protein events into smaller sentences that contain only one distinct event.
By breaking these sentences down the authors were able to increase their recall; however, sentences that contained ambiguous directionality or multiple phosphorylation events were too complex for the simplifier.
As a consequence, the simplifier missed some relevant sentences [@doi:10.1093/database/bav020].
These errors highlight a crucial need for future algorithms to be generalizable enough to handle various forms of complex sentences.

Pattern matching is a fundamental approach used to detect relationship asserting sentences.
These patterns can consist of phrases from constituency trees, a set of keywords or some combination of both [@doi:10.1093/nar/gkx462; @doi:10.1186/s12859-018-2103-8; @doi:10.1371/journal.pone.0152725; @doi:10.1093/bioinformatics/btg449; @doi:10.1186/1471-2105-14-181; @doi:10.1109/TCBB.2014.2372765].
Xu et al. designed a pattern matcher system to detect sentences in PubMed abstracts that indicate drug-disease treatments [@doi:10.1186/1471-2105-14-181].
This system matched drug-disease pairs from ClinicalTrials.gov to drug-disease pairs mentioned in abstracts.
This matching process aided the authors in identifying sentences that can be used to create simple patterns, such as "Drug in the treatment of Disease" [@doi:10.1186/1471-2105-14-181], to match other sentences in a wide variety of abstracts.
The authors hand curated two datasets for evaluation and achieved a high precision score of 0.904 and a low recall score of 0.131 [@doi:10.1186/1471-2105-14-181].
This low recall score was based on constructed patterns being too specific to detect infrequent drug pairs.
Besides constituency trees, some approaches used dependency trees to construct patterns [@doi:10.1016/j.jbi.2015.08.008; @doi:10.1093/database/bay108].
Depending upon the nature of the algorithm and text, dependency trees could be more appropriate than constituency trees and vice versa.
The performance difference between the two trees remains as an open question for future exploration.

Rule-based methods provide a basis for many relationship extraction systems.
Approaches in this category range from simplifying sentences for easy extraction to identifying sentences based on matched key phrases or grammatical patterns.
Both require a significant amount of manual effort and expert knowledge to perform well.
A future direction is to develop ways to automate the construction of these hand-crafted patterns, which would accelerate the process of creating these rule-based systems.

![
A visualization of a constituency parse tree using the following sentence: "BRCA1 is associated with breast cancer" [@raw:eisenbach2006phpsyntaxtree].
This type of tree has the root start at the beginning of the sentence.
Each word is grouped into subphrases depending on its correlating part of speech tag.
For example, the word "associated" is a past participle verb (VBN) that belongs to the verb phrase (VP) subgroup.
](images/figures/constituency_parse_tree_example.png){#fig:constituency-parse-tree-example}

![
A visualization of a dependency parse tree using the following sentence: "BRCA1 is associated with breast cancer" [@raw:honnibal2017spacy].
For these types of trees, the root begins with the main verb of the sentence.
Each arrow represents the dependency shared between two words.
For example, the dependency between BRCA1 and associated is nsubjpass, which stands for passive nominal subject.
This means that "BRCA1" is the subject of the sentence and it is being referred to by the word "associated".
](images/figures/dependency_parse_example.png){#fig:dependency-parse-tree-example}

#### Extracting Relationships Without Labels

Unsupervised extractors draw inferences from textual data without the use of annotated labels.
These methods involve some form of clustering or statistical calculations.
In this section we focus on methods that use unsupervised learning to extract relationships from text. 

An unsupervised extractor can exploit the fact that two entities may appear together in text.
This event is referred to as co-occurrence and studies that use this phenomenon can be found in Table {@tbl:unsupervised-methods-text-mining}.
Two databases DISEASES [@doi:10.1016/j.ymeth.2014.11.020] and STRING [@doi:10.1093/nar/gks1094] were populated using a co-occurrence scoring method on PubMed abstracts, which measured the frequency of co-mention pairs within individual sentences as well as the abstracts themselves.
This technique assumes that each individual co-occurring pair is independent from one another.
Under this assumption mention pairs that occur more than expected were presumed to implicate the presence of an association or interaction.
This approach identified 543,405 disease gene associations [@doi:10.1016/j.ymeth.2014.11.020] and 792,730 high confidence protein-protein interactions [@doi:10.1093/nar/gks1094] but is limited to only PubMed abstracts.

Full text articles are able to dramatically enhance relationship detection [@doi:10.1371/journal.pcbi.1005962; @doi:10.1093/nar/gkt1207].
Westergaard et al. used a co-occurrence approach, similar to DISEASES [@doi:10.1016/j.ymeth.2014.11.020] and STRING [@doi:10.1093/nar/gks1094], to mine full articles for protein-protein interactions and other protein related information [@doi:10.1371/journal.pcbi.1005962].
The authors discovered that full text provided better prediction power than using abstracts alone, which suggests that future text mining approaches should consider using full text to increase detection power.

Unsupervised extractors often treat different biomedical relationships as multiple isolated problems.
An alternative to this perspective is to capture all different types at once.
Clustering is an approach that performs simultaneous extraction.
Percha et al. used a biclustering algorithm on generated dependency parse trees to group sentences within PubMed abstracts [@doi:10.1093/bioinformatics/bty114].
Each cluster was manually curated to determine which relationship each group represented.
This approach captured 4,451,661 dependency paths for 36 different groups [@doi:10.1093/bioinformatics/bty114].
Despite the success, this approach suffered from technical issues such as dependency tree parsing errors.
These errors resulted in some sentences not being captured by the clustering algorithm [@doi:10.1093/bioinformatics/bty114].
Future clustering approaches should consider simplifying sentences to prevent this type of issue.

Overall unsupervised methods provide a means to rapidly extract relationship asserting sentences without the need of annotated text.
Approaches in this category range from calculating co-occurrence scores to clustering sentences and provide a generalizable framework that can be used on large repositories of text.
Full text has already been shown to meaningfully improve the performance of methods that aim to infer relationships using cooccurrences [@doi:10.1371/journal.pcbi.1005962], and we should expect similar benefits for machine learning approaches.
Furthermore, we expect that simplifying sentences would improve unsupervised methods and should be considered as an initial preprocessing step.

| Study | Relationship of Interest | 
| --- | --- | 
| CoCoScore [@doi:10.1093/bioinformatics/btz490] | Protein-Protein Interactions, Disease-Gene and Tissue-Gene Associations |
| Rastegar-Mojarad et al. [@doi:10.1109/bibm.2015.7359766] | Drug Disease Treatments |
| CoPub Discovery [@doi:10.1371/journal.pcbi.1000943] | Drug, Gene and Disease interactions |
| Westergaard et al. [@doi:10.1371/journal.pcbi.1005962]| Protein-Protein Interactions |
| DISEASES [@doi:10.1016/j.ymeth.2014.11.020] | Disease-Gene associations|
| STRING [@doi:10.1093/nar/gku1003]| Protein-Protein Interactions |
| Singhal et al. [@doi:10.1371/journal.pcbi.1005017] | Genotype-Phenotype Relationships |

Table: Table of approaches that mainly use a form of co-occurrence. {#tbl:unsupervised-methods-text-mining}

#### Supervised Relationship Extraction

Supervised extractors use labeled sentences to construct generalized patterns that bisect positive examples (sentences that allude to a relationship) from negative ones (sentences that do not allude to a relationship).
Most of these approaches have flourished due to pre-labelled publicly available datasets (Table {@tbl:supervised-text-datasets}).
These datasets were constructed by curators for shared open tasks [@raw:biocreative/chemprot; @doi:10.1093/database/baw068] or as a means to provide the scientific community with a gold standard [@doi:10.1093/bioinformatics/btl616; @doi:10.1093/database/baw068; @doi:10.1186/1471-2105-14-323].
Approaches that use these available datasets range from using linear classifiers such as support vector machines (SVMs) to non-linear classifiers such as deep learning techniques.
The rest of this section discusses approaches that use supervised extractors to detect relationship asserting sentences.

Some supervised extractors involve the mapping of textual input into a high dimensional space.
SVMs are a type of classifier that can accomplish this task with a mapping function called a kernel [@doi:10.1186/s13326-017-0168-3; @doi:10.1371/journal.pcbi.1004630].
These kernels take information such as a sentence's dependency tree [@doi:10.1093/database/bay108; @doi:10.1093/bioinformatics/btw503], part of speech tags [@doi:10.1186/s13326-017-0168-3] or even word counts [@doi:10.1371/journal.pcbi.1004630] and map them onto a dense feature space.
Within this space, these methods construct a hyperplane that separates sentences in the positive class (illustrates a relationship) from the negative class (does not illustrate a relationship). 
Kernels can be manually constructed or selected to cater to the relationship of interest [@doi:10.1186/s13326-017-0168-3; @doi:10.1093/bioinformatics/btw503;@doi:10.1371/journal.pcbi.1004630; @doi:10.1371/journal.pcbi.1004630].
Determining the correct kernel is a nontrivial task that requires expert knowledge to be successful.
In addition to single kernel methods, a recent study used an ensemble of SVMs to extract disease-gene associations [@doi:10.1371/journal.pone.0200699].
This ensemble outperformed notable disease-gene association extractors [@doi:10.1016/j.jbi.2015.08.008; @doi:10.1186/s12859-015-0472-9] in terms of precision, recall and F1 score.
Overall, SVMs have been shown to be beneficial in terms of relationship mining; however, major focus has shifted to utilizing deep learning techniques which can perform non-linear mappings of high dimensional data.

Deep learning is an increasingly popular class of techniques that can construct their own features within a high dimensional space [@raw:GoodfellowDL; @doi:10.1038/nature14539].
These methods use different forms of neural networks, such as recurrent or convolutional neural networks, to perform classification.

Recurrent neural networks (RNN) are designed for sequential analysis and use a repeatedly updating hidden state to make predictions.
An example of a recurrent neural network is a long short-term memory (LSTM) network [@doi:10.1162/neco.1997.9.8.1735].
Cocos et al. [@doi:10.1093/jamia/ocw180] used a LSTM to extract drug side effects from de-identified twitter posts, while Yadav et al. [@doi:10.3233/978-1-61499-830-3-644] used an LSTM to extract protein-protein interactions.
Others have also embraced LSTMs to perform relationship extraction [@arxiv:1708.03743; @doi:10.1093/bioinformatics/btw486; @arxiv:1808.09101; @doi:10.1186/s12859-017-1609-9; @doi:10.1093/jamia/ocw180]. 
Despite the success of these networks, training can be difficult as these networks are highly susceptible to vanishing and exploding gradients [@doi:10.1109/ICNN.1993.298725; @doi:10.1016/j.physd.2019.132306].
One proposed solution to this problem is to clip the gradients while the neural network trains [@arxiv:1211.5063].
Besides the gradient problem, these approaches only peak in performance when the datasets reach at least tens of thousands of data points [@arxiv:1707.02968].

Convolutional neural networks (CNNs), which are widely applied for image analysis, use multiple kernel filters to capture small subsets of an overall image [@doi:10.1038/nature14539].
In the context of text mining an image is replaced with words within a sentence mapped to dense vectors (i.e., word embeddings) [@arxiv:1301.3781; @arxiv:1310.4546].
Peng et al. used a CNN to extract sentences that mentioned protein-protein interactions [@arxiv:1706.01556v2] and Zhou et al. used a CNN to extract chemical-disease relations [@doi:10.1186/s12859-019-2873-7].
Others have used CNNs and variants of CNNs to extract relationships from text [@doi:10.1177/0165551516673485; @doi:10.1093/database/bay073; @doi:10.1101/730085].
Just like RNNs, these networks perform well when millions of labeled examples are present [@arxiv:1707.02968]; however, obtaining these large datasets is a non-trivial task.
Future approaches that use CNNs or RNNs should consider solutions to obtaining these large quantities of data through means such as weak supervision [@doi:10.3115/1690219.1690287], semi-supervised learning [@doi:10.2200/S00196ED1V01Y200906AIM006] or using pre-trained networks via transfer learning [@doi:10.1109/TKDE.2009.191; @doi:10.1186/s40537-016-0043-6].

Semi-supervised learning [@doi:10.2200/S00196ED1V01Y200906AIM006] and weak supervision [@doi:10.3115/1690219.1690287] are techniques that can rapidly construct large datasets for machine learning classifiers. 
Semi-supervised learning trains classifiers by combining labeled data with unlabeled data.
For example, one study used a variational auto encoder with a LSTM network to extract protein-protein interactions from PubMed abstracts and full text [@arxiv:1901.06103v1].
This is an elegant solution for the small dataset problem but requires labeled data to start. 
This dependency makes finding under-studied relationships difficult as one would need to find or construct examples of the missing relationships at the start.

Weak or distant supervision takes a different approach by using noisy or even erroneous labels to train classifiers [@doi:10.3115/1690219.1690287; @doi:10.1093/bioinformatics/btv476; @doi:10.14778/3157794.3157797; @doi:10.1145/3209889.3209898].
Under this paradigm, sentences are labeled based on their mention pair being present (positive) or absent (negative) in a database and, once labeled, a machine learning classifier can be trained to extract relationships from text [@doi:10.3115/1690219.1690287].
For example, Thomas et al. [@raw:Thomas2011LearningTE] used distant supervision to train a SVM to extract sentences mentioning protein-protein interactions (PPI). 
Their SVM model achieved comparable performance against a baseline model; however, the noise generated via distant supervision was difficult to eradicate [@raw:Thomas2011LearningTE].
A number of efforts have focused on combining distant supervision with other types of labeling strategies to mitigate the negative impacts of noisy knowledge bases [@arxiv:1805.09927; @arxiv:1805.09929; @doi:10.18653/v1/W17-2323].
Nicholson et al. [@doi:10.1101/730085] found that, in some circumstances, these strategies can be reused across different types of biomedical relationships to learn a heterogeneous knowledge graph in cases where those relationships describe similar physical concepts.
Combining distant supervision with other types of labeling strategies remains an active area of investigation with numerous associated challenges and opportunities.
Overall, semi-supervised learning and weak supervision provide promising results in terms of relationship extraction and future approaches should consider using these paradigms to train machine learning classifiers.

| Dataset | Type of Sentences |
| --- | --- |
| AIMed [@doi:10.1016/j.artmed.2004.07.016] | Protein-Protein Interactions |
| BioInfer [@doi:10.1186/1471-2105-8-50] | Protein-Protein Interactions | 
| LLL [@raw:LLL] | Protein-Protein Interactions |
| IEPA [@raw:IEPA] | Protein-Protein Interactions |
| HPRD5 [@doi:10.1093/bioinformatics/btl616] | Protein-Protein Interactions |
| EU-ADR [@doi:10.1016/j.jbi.2012.04.004] | Disease-Gene Associations |
| BeFree [@doi:10.1186/s12859-015-0472-9] | Disease-Gene Associations |
| CoMAGC [@doi:10.1186/1471-2105-14-323] | Disease-Gene Associations | 
| CRAFT [@doi:10.1186/1471-2105-13-161] | Disease-Gene Associations |
| Biocreative V CDR [@doi:10.1093/database/baw068] | Compound induces Disease |
| Biocreative IV ChemProt [@raw:biocreative/chemprot] | Compound-Gene Bindings |

Table: A set of publicly available datasets for supervised text mining. {#tbl:supervised-text-datasets}


## Applying Knowledge Graphs to Biomedical Challenges

Knowledge graphs can help researchers tackle many biomedical problems such as finding new treatments for existing drugs [@doi:10.7554/eLife.26726], aiding efforts to diagnose patients [@arxiv:1611.07012] and identifying associations between diseases and biomolecules [@doi:10.1155/2017/2498957].
In many cases, solutions rely on representing knowledge graphs in a low dimensional space, which is a process called representational learning.
The goal of this process is to retain and encode the local and/or global structure of a knowledge graph that is relevant to the problem while transforming the graph into a representation that can be readily used with machine learning methods to build predictors.
In the following sections we review methods that construct a low dimensional space (Unifying Representational Learning Techniques) and discuss applications that use this space to solve biomedical problems (Unifying Applications).

### Unifying Representational Learning Techniques

Mapping high dimensional data into a low dimensional space greatly improves modeling performance in fields such as natural language processing [@arxiv:1301.3781; @arxiv:1310.4546] and image analysis [@arxiv:1512.03385].
The success of these approaches served as rationale for a sharper focus on representing knowledge graphs in a low dimensional space [@arxiv:1709.05584].
Methods of this class are designed to capture the essence of a knowledge graph in the form of dense vectors [@doi:10.1007/BF02288367; @doi:10.1162/089976603321780317].
These vectors are often assigned to nodes in a graph [@arxiv:1607.00653], but edges can be assigned as well [@raw:bordestranse].
Techniques that construct a low dimensional space often require information on how nodes are connected with one another [@raw:gongreplearn; @doi:10.1109/TKDE.2016.2606098; @raw:hanreplearn; @doi:10.1145/2806416.2806512], while other approaches can work directly with the edges themselves [@arxiv:1610.04073].
Once this space has been constructed, machine learning techniques can utilize the space for downstream analyses such as classification or clustering.
We group techniques that construct this space into the following three categories: matrix factorization, translational distance models, and neural network models (Figure {@fig:unifying_techniques_overview}).

![
Pipeline for representing knowledge graphs in a low dimensional space.
Starting with a knowledge graph, this space can be generated using one of the following options: Matrix Factorization (a), Translational Models (b) or Neural Network Models (c).
The output of this pipeline is an embedding space that clusters similar node types together.
](images/figures/unifying_techniques_overview.png){#fig:unifying_techniques_overview}

#### Matrix Factorization

Matrix factorization is a class of techniques that use linear algebra to map high dimensional data into a low dimensional space.
This projection is accomplished by decomposing a matrix into a set of small rectangular matrices (Figure {@fig:unifying_techniques_overview} (a)).
Notable methods for matrix decomposition include Isomap [@doi:10.1126/science.290.5500.2319], Laplacian eigenmaps [@doi:10.1162/089976603321780317] and Principal Component Analysis (PCA) [@doi:10/bm8dnf]/Singular Vector Decomposition (SVD) [@doi:10.1007/BF02288367].
These methods were designed to be used on many different types of data; however, we discuss their use in the context of representing knowledge graphs in a low dimensional space and focus particularly on SVD and laplacian eigenmaps.  

SVD [@doi:10.1007/BF02288367] is an algorithm that uses matrix factorization to portray knowledge graphs in a low dimensional space.
The input for this algorithm is an adjacency matrix ($A$), which is a square matrix where rows and columns represent nodes and each entry is a binary representation of the presence of an edge between two nodes. 
$A$ is constructed based on the knowledge graph's structure itself and collapses all edges between two nodes into one unique entity.
Following construction, $A$ is decomposed into the following three parts: a square matrix $Σ$ and a set of two small rectangular matrices $U$ and $V^{T}$.
Values within $Σ$ are called singular values, which are akin to eigenvalues [@doi:10.1007/BF02288367].
Each row in $U$ and each column in $V^{T}$ represents nodes within a low dimensional space [@doi:10.1007/BF02288367; @doi:10/bm8dnf].
In practice, $U$ is usually used to represent nodes in a knowledge graph and can be used as input for machine learning classifiers to perform tasks such as link prediction or node classification [@doi:10.1093/bioinformatics/btz718]; however, $V^{T}$ has also been used [@doi:10.1007/BF02288367; @raw:Jiezhon2018].
Typically, matrix factorization algorithms such as SVD are used for recommendation systems via collaborative filtering [@doi:10.1155/2009/421425]; however, this technique can also provide a standalone baseline for other relational learning approaches [@doi:10.1093/bioinformatics/btz718].

Laplacian eigenmaps assume there is low dimensional structure in a high dimensional space and preserves this structure when projecting data into a low dimensional space [@doi:10.1162/089976603321780317].
The first step of this technique is to preserve the low dimensional structure by representing data in the form of a graph where nodes are datapoints and edges are the distance between two points.
Knowledge graphs already provide this representation, so no additional processing is necessary at this stage.
The second step of this technique is to obtain both an adjacency matrix ($A$) and a degree matrix ($D$) from the graph representation.
A degree matrix is a diagonal matrix where each entry represents the number of edges connected to a node.
The adjacency and degree matrices are converted into a laplacian matrix ($L$), which is a matrix that shares the same properties as the adjacency matrix.
The laplacian matrix is generated by subtracting the adjacency matrix from the degree matrix ($L=D-A$) and, once constructed, the algorithm uses linear algebra to calculate the laplacian's eigenvalues and eigenvectors ($Lx = \lambda Dx$).
The generated eigenvectors represent the knowledge graph's nodes represented in a low dimensional space [@doi:10.1162/089976603321780317].
Other efforts have used variants of this algorithm to construct low dimensional representations of knowledge graphs [@raw:gongreplearn; @doi:10.1109/TKDE.2016.2606098; @arxiv:1905.09763].
Typically, eigenmaps work well when knowledge graphs have a sparse number of edges between nodes but struggle when presented with denser networks [@doi:10.1093/bioinformatics/btz718; @doi:10.1371/journal.pcbi.1005621; @arxiv:1905.09763].
An open area of exploration is to adapt these methods to accommodate knowledge graphs that have a large number of edges.

Matrix factorization is a powerful technique that represents high dimensional data in a low dimensional space.
The representation of a knowledge graph in this reduced space does not meet our definition of a knowledge graph; however, this representation supports many use cases including similarity-based (e.g., cosine similarity [@arxiv:1910.09129]) and machine learning applications.
Common matrix factorization approaches involve using SVD, Laplacian eigenmaps or variants of the two to decompose matrices into smaller rectangular forms.
Regarding knowledge graphs, the adjacency matrix ($A$) is the typical matrix that gets decomposed, but the laplacian matrix ($L=D-A$) can be used as well. 
Despite reported success, the dependence on matrices creates an issue of scalability as matrices of large networks may reach memory limitations.
Furthermore, the approaches we discussed consider all edge types as equivalent.
These limitations could be mitigated by new approaches designed to accommodate multiple node and edge types separately.

#### Translational Distance Models

Translational distance models treat edges in a knowledge graph as linear transformations.
For example, one such algorithm, TransE [@raw:bordestranse], treats every node-edge pair as a triplet with head nodes represented as $\textbf{h}$, edges represented as $\textbf{r}$, and tail nodes represented as $\textbf{t}$.
These representations are combined into an equation that mimics the iconic word vectors translations ($\textbf{king} - \textbf{man} + \textbf{woman} \approx \textbf{queen}$) from the word2vec model [@arxiv:1310.4546].
The described equation is shown as follows: $\textbf{h} + \textbf{r} \approx \textbf{t}$.
Starting at the head node ($\textbf{h}$), one adds the edge vector ($\textbf{r}$) and the result should be the tail node ($\textbf{t}$).
TransE optimizes vectors for $\textbf{h}$, $\textbf{r}$, $\textbf{t}$, while guaranteeing the global equation ($\textbf{h} + \textbf{r} \approx \textbf{t}$) is satisfied [@raw:bordestranse].
A caveat to the TransE approach is that it forces relationships to have a one to one mapping, which may not be appropriate for all relationship types.

Wang et al. attempted to resolve the one to one mapping issue by developing the TransH model [@raw:wangtransH].
TransH treats relations as hyperplanes rather than a regular vector and projects the head ($\textbf{h}$) and tail ($\textbf{t}$) nodes onto a hyperplane.
Following this projection, a distance vector ($\textbf{d}_{r}$) is calculated between the projected head and tail nodes.
Finally, each vector is optimized while preserving the global equation: $\textbf{h} + \textbf{d}_{r} \approx \textbf{t}$ [@raw:wangtransH].
Other efforts have built off of the TransE and TransH models [@raw:lintransR, @arxiv:1610.04073; @arxiv:1909.00672]. 
In the future, it may be beneficial for these models to incorporate other types of information such as edge confidence scores, textual information, or edge type information when optimizing these distance models.

#### Neural Networks

Neural networks are a class of machine learning models inspired by the concept of biological neural networks [@pmid:11084225].
These networks are reputable for making non-linear transformations of high dimensional data to solve classification and regression problems [@pmid:11084225].
In the context of knowledge graphs, the most commonly used structures are based on word2vec [@arxiv:1310.4546; @arxiv:1301.3781].
The word2vec term applies to a set of conceptually related approaches that are widely used in the natural language processing field.
The goal of word2vec is to project words onto a low dimensional space that preserves their semantic meaning.
Strategies for training word2vec models use one of two neural network architectures: skip-gram and continuous bag of words (CBOW).
Both models are feed-forward neural networks, but CBOW models are trained to predict a word given its context while skip-gram models are trained to predict the context given a word [@arxiv:1310.4546; @arxiv:1301.3781].
Once training is completed, words will be associated with dense vectors that downstream models, such as feed forward networks or recurrent networks, can use for input.

Deepwalk is an early method that represents knowledge graphs in a low dimensional space [@doi:10.1145/2623330.2623732]. 
The first step of this method is to perform a random walk along a knowledge graph.
During the random walk, every generated sequence of nodes is recorded and treated as a sentence in word2vec [@arxiv:1310.4546; @arxiv:1301.3781].
After every node has been processed, a skip-gram model is trained to predict the context of each node thereby constructing a low dimensional representation of a knowledge graph [@doi:10.1145/2623330.2623732].
A limitation for deepwalk is that the random walk cannot be controlled, so every node has an equal chance to be reached.
Grover and Leskovec demonstrated that this limitation can hurt performance when classifying edges between nodes and developed node2vec as a result [@arxiv:1607.00653].
Node2vec operates in the same fashion as deepwalk; however, this algorithm specifies a parameter that lets the random walk be biased when traversing nodes [@arxiv:1607.00653].
A caveat to both deepwalk and node2vec is that they ignore information such as edge type and node type.
Various approaches have evolved to fix this limitation by incorporating  node, edge and even path types when representing knowledge graphs in a low dimensional space [@doi:10.1145/3097983.3098061; @doi:10.1145/3097983.3098036; @arxiv:1809.02269; @arxiv:1808.05611].
An emerging area of work is to develop approaches that capture both the local and global structure of a graph when constructing this low dimensional space.

Though word2vec is the most common framework used to represent graphs, neural networks are sometimes designed to use the adjacency matrix as input [@arxiv:1310.4546; @arxiv:1301.3781].
These approaches use models called autoencoders [@doi:10.1109/DSAA.2018.00034; @arxiv:1611.07308; @arxiv:1802.04407].
Autoencoders are designed to map input into a low dimensional space and then back to a reconstruction of the same input [@doi:10.1016/j.neunet.2014.09.003; @raw:Baldi2011].
It is possible to layer on additional objectives by modifying the loss function to take into account criteria above and beyond reconstruction loss [@arxiv:1312.6114; @arxiv:1802.03480].
In the context of knowledge graphs, the generated space correlates nodes with dense vectors that capture a graph's connectivity structure [@doi:10.1109/DSAA.2018.00034; @arxiv:1611.07308; @arxiv:1802.04407].
Despite the high potential of autoencoders, this method relies on an adjacency matrix for input which can run into scalability issues as a knowledge graph asymptotically increases in size [@doi:10.1109/TKDE.2019.2951398].
Plus, Khosla et al. discovered that approaches akin to node2vec outperformed algorithms using autoencoders when undergoing link prediction and node classification [@doi:10.1109/TKDE.2019.2951398].

Overall, the performance of neural network models largely depends upon the structure of nodes and edges within a knowledge graph [@doi:10.1109/TKDE.2019.2951398].
Furthermore, when these approaches are used only nodes are explicitly represented by these vectors.
This means a represented knowledge graph no longer meets our definition of a knowledge graph; however, this representation can make it more suitable for many biomedical applications.
Future areas of exploration should include hybrid models that use both node2vec and autoencoders to construct complementary low dimensional representations of knowledge graphs.

### Unifying Applications

Knowledge graphs have been applied to many biomedical challenges ranging from identifying proteins' functions [@doi:10.1186/s12859-018-2163-9] to prioritizing cancer genes [@doi:10.1093/bioinformatics/bty148] to recommending safer drugs for patients [@arxiv:1710.05980; @doi:10.1609/aaai.v33i01.33011126] (Figure {@fig:unifying_applications}).
In this section we review how knowledge graphs are applied in biomedical settings and put particular emphasis on an emerging set of techniques that represent knowledge graphs in a low dimensional space.

![
Overview of various biomedical applications that make use of knowledge graphs.
Categories consist of: (a) Multi-Omic applications, (b) Pharmaceutical Applications and (c) Clinical Applications.
](images/figures/unifying_applications_overview.png){#fig:unifying_applications}

#### Multi-Omic Applications

Multi-omic applications employ knowledge graphs to study the genome, how genes are expressed in the transcriptome, and how the products of those transcripts interact in the proteome.
These graphs are used to establish connections between -omic entities as well as diseases.
Tasks in this context include gene-symptom prioritization [@doi:10.1093/jamia/ocy117], protein-protein interaction prediction [@doi:10.1089/cmb.2012.0273; @doi:10.1186/1752-0509-9-S1-S9] and detecting miRNA-disease associations [@doi:10.1155/2017/2498957].
We focus specifically on multi-omic applications that represent knowledge graphs in a low dimensional space to make connections.

Recommendation systems make use of knowledge graphs to establish links between RNA with disease and proteins with other proteins.
Shen et al. used an algorithm called collaborative filtering to establish an association between miRNA and diseases [@doi:10.1155/2017/2498957].
The authors constructed a miRNA-Disease network using the Human MicroRNA Disease database (HMDD) [@doi:10.1093/nar/gky1010] and generated an adjacency matrix with the rows representing miRNA and the columns representing diseases.
This matrix was decomposed into small rectangular matrices using SVD, then these small matrices were used to calculate similarity scores between miRNAs and diseases.
High scores implied a high likelihood that a given miRNA had an association with a given disease [@doi:10.1155/2017/2498957].
Other approaches built off of Shen et al.'s work by incorporating novel ways to perform matrix factorization [@doi:10.3390/genes10020080; @doi:10.1186/s12859-019-2956-5;@doi:10.1186/s12859-019-3260-0] or by integrating machine learning models in conjunction with matrix factorization [@doi:10.1109/TCBB.2019.2937774].
These approaches achieved high area under the receiver operating curve (AUROC), but new discoveries have been hard to validate as experiments in this space are costly and time consuming at best [@doi:10.1155/2017/2498957].
Apart from miRNA, collaborative filtering has been used to predict protein-protein interactions [@doi:10.1109/BIBM.2010.5706537; @doi:10.1089/cmb.2012.0273; @doi:10.1186/1752-0509-9-S1-S9].
Although extensive validation of newly generated candidates may be impractical, it would be helpful to see future efforts in this space include a blinded literature search for prioritized and randomly selected candidates as part of the standard evaluation pipeline.

Applications of neural network models have mainly used the node2vec model [@arxiv:1607.00653] or variants of it.
Yang et al. used node2vec to create a recommendation system to infer associations between genes and disease symptoms [@doi:10.1093/jamia/ocy117].
The authors constructed a gene-disease symptom knowledge graph by combining two bipartite graphs: genes with diseases and diseases with disease symptoms.
The generated graph was embedded via node2vec and similarity scores were calculated for every gene-symptom pair in the graph.
High scores implied a high likelihood of an association [@doi:10.1093/jamia/ocy117].
This approach outperformed methods that didn't use a knowledge graph; however, validation was difficult as it involved manual curation of the literature [@doi:10.1093/jamia/ocy117].
Similar approaches used variants of node2vec to predict gene-disease associations
[@doi:10.1093/bioinformatics/bty559; doi:10.3389/fgene.2019.00226 @doi:10.1186/s12920-019-0627-z; @doi:10.1109/BIBM47256.2019.8983134] analyze RNA-seq data [@doi:10.1093/nar/gkx750] and infer novel protein information [@doi:10.1093/bioinformatics/btx275; @doi:10.1007/978-3-030-00825-3_16; @doi:10.1016/j.artmed.2019.04.001; @doi:10.1186/s12859-018-2163-9].

Knowledge graphs benefited the multi-omics field as a resource for generating novel discoveries.
Most approaches to date use matrix factorization and node2vec to project knowledge graph into a low dimensional space, while translational models (Figure {@fig:unifying_techniques_overview} (b)) may be an untapped resource that could aid future efforts.
Another area of exploration could be incorporating multiple sources of information such as compounds, anatomic locations or genetic pathways to improve the specificity of findings (i.e., to predict that a protein-protein interaction happens in a specific cell type or tissue).

#### Pharmaceutical Applications

There are a multitude of examples where knowledge graphs have been applied to identify new properties of drugs.
Tasks in this field involve predicting drugs interacting with other drugs [@doi:10.1016/j.websem.2017.06.002], identifying molecular targets a drug might interact with [@doi:10.1155/2015/275045] and identifying new disease treatments for previously established drugs [@doi:10.7554/eLife.26726.001].
In this section we concentrate on applications that apply these graphs to discover new properties of drugs and focus on approaches that use these graphs in a low-dimensional space.

Similar to multi-omic applications, recommendation systems have utilized knowledge graphs to infer novel links between drugs and diseases.
Dai et al. used collaborative filtering to infer drug-disease associations [@doi:10.1155/2015/275045].
The authors constructed a drug-disease network by integrating two bipartite networks: a drug-gene interaction network and a disease-gene interaction network.
They integrated both networks under the assumption that drugs associated with a disease interact with the same gene of interest. 
Following construction, the authors generated an adjacency matrix where rows represent drugs and columns represent diseases.
This matrix was decomposed into two small rectangular matrices and these matrices were used to calculate similarity scores between all drugs and all diseases.
High values implied a high chance of an association [@doi:10.1155/2015/275045].
Related approaches used this technique to infer drug-target interactions [@doi:10.1109/TCBB.2016.2530062; @doi:10.1109/BIOCAS.2018.8584817; @doi:10.1093/bioinformatics/btaa010] and drug-disease treatments [@doi:10.1109/TCBB.2018.2830384; @doi:10.1371/journal.pcbi.1004760; @doi:10.1038/srep40376; @doi:10.1021/ci500340n; @doi:10.1186/s12859-018-2220-4].
In spite of reported success, these approaches are limited to the drugs and diseases contained in the graph.
Combining these approaches with representations of chemical structures might make it possible to one day make predictions about novel compounds.

Applications that use neural network models have used node2vec [@doi:10.1093/bioinformatics/btx160; @doi:10.1101/539643] and autoencoders [@arxiv:1804.10850v1; @doi:10.1093/bioinformatics/bty294] approaches to represent knowledge graphs in a low dimensional space.
Zong et al. used a node2vec-like model to predict drug-target associations [@doi:10.1093/bioinformatics/btx160].
The authors constructed a disease-target-disease network using drug centered databases: Drugbank [@doi:10.1093/nar/gkm958] and Diseasome [@doi:10.1073/pnas.0701361104].
Next, the authors applied a random walk to the graph and trained a skip-gram model to generate a low dimensional representation of the graph.
Lastly, the authors constructed a similarity metric that used this space to rank how similar drugs are to their targets [@doi:10.1093/bioinformatics/btx160].
A limitation to this approach is that their graph is missing information such as pharmacological class or drug chemical structure that could improve prediction performance.
Overall, neural networks provide a robust set of techniques that have been shown to outperform most linear approaches in this context [@doi:10.1186/s12859-019-3284-5; @doi:10.1145/3307339.3342161].

Applications that discover new properties of drugs have benefited from using knowledge graphs as a resource.
Most methods to date use matrix factorization and neural network models to produce a low-dimensional representation.
Due to the success of neural networks [@doi:10.1186/s12859-019-3284-5; @doi:10.1145/3307339.3342161] much of the field's focus has shifted to these techniques; however, a possible improvement is to use an ensemble of neural network models and linear methods to improve performance.
Another potential avenue for future work would be to incorporate entity-specific hierarchical information or similarity information to improve detection power.
For drugs, this could include pharmaceutical classes or chemical structure similarities.

#### Clinical applications

Clinical applications that use knowledge graphs are in early stages of development, but the long-term goal is to use analyses of these graphs to aid patient care.
Typically, graphs for these applications are constructed from electronic health records (EHR): nodes represent patients, drugs and diseases while edges represent relationships such as a patient being prescribed a treatment or a patient being diagnosed with a disease [@pmid:26306276; @doi:10.1145/2110363.2110415; @arxiv:1707.05340; @doi:10.1186/s12859-015-0549-5].
Tasks within this field range from improving patient diagnoses [@doi:10.1109/TKDE.2016.2605687;@arxiv:1709.06908] to recommending safer drugs for patients [@arxiv:1710.05980; @arxiv:1709.06908].
We briefly discuss efforts that use knowledge graphs to accomplish such tasks.

Early work in this field applied translational models (Figure {@fig:unifying_techniques_overview} (b)) to knowledge graphs with the goal of recommending safe drugs.
Wang et al. used a variant of the TransH [@raw:wangtransH] model to create such a system for patients [@arxiv:1710.05980].
They constructed a disease-patient-drug network by integrating a patient-disease bipartite network with a patient-drug bipartite network.
Every node in the newly constructed graph was embedded while satisfying the following equation: $\textbf{h} - \textbf{r} \approx \textbf{t}$.
Following the embedding step, the authors formulated their own similarity metric that selected drug combinations with a low number of interactions [@arxiv:1710.05980].
Researchers in [@arxiv:1909.00672] applied a similar variant of the TransH model to a medical knowledge graph and evaluated their model for link prediction rather than patient recommendation.

In contrast with most applications where node2vec and autoencoder models have become established, this field have focused on using graph attention models [@arxiv:1706.03762].
These models mimic machine translation models [@arxiv:1409.0473] and aim to simultaneously represent knowledge graphs in a low dimensional space and perform the task at hand.
Choi et al. used a graph attention model to predict patient diagnoses [@arxiv:1611.07012].
The authors constructed a directed graph using medical concepts from patient EHR data.
This directed graph was fed into a graph attention network and then used to predict a patient's likelihood of heart failure [@arxiv:1611.07012].
Other approaches have used graph attention models to perform clinical tasks such as drug safety recommendations [@doi:10.1609/aaai.v33i01.33011126] and patient diagnoses [@arxiv:1906.04716].

Knowledge graphs have shown promising results when used for clinical applications; however, there is still room for improvement.
Most approaches have run into the common problem of missing data within EHR [@arxiv:1611.07012; @arxiv:1710.05980; @doi:10.1609/aaai.v33i01.33011126].
Future directions for the field consist of designing algorithms that can fill in this missing data gap or construct models that can take missing data into account.


## Conclusion

Knowledge graphs are becoming widely used in biomedicine, and we expect their use to continue to grow.
At the moment, most are constructed from databases derived from manual curation or from co-occurrences in text.
We expect that machine learning approaches will play a key role in quickly deriving new findings from these graphs.
Representing these knowledge graphs in a low dimensional space that captures a graph's local and global structure can enable many downstream machine learning analyses, and methods to capture this structure are an active area of research.

As with any field, rigorous evaluation that can identify key factors that drive success is critical to moving the field forward.
In regard to knowledge graphs, evaluation remains difficult.
Experiments in this context require a significant amount of time and consequently resources [@doi:10.1093/jamia/ocy117; @doi:10.1155/2017/2498957].
Moving from open ended and uncontrolled evaluations that consist of describing findings that are consistent with the literature to blinded evaluations of the literature that corroborate predictions and non-predictions would be a valuable first step.
There are also well-documented biases related to node degree and degree distribution that must be considered for accurate evaluation [@url:https://greenelab.github.io/xswap-manuscript/].
Furthermore, the diversity of applications hinders the development of a standardized set of expected evaluations.

We anticipate that a fruitful avenue of research will be techniques that can produce low dimensional representations of knowledge graphs which distinguish between multiple node and edge types.
There are many different sources of bias that lead to spurious edges or incompleteness, and modeling these biases may support better representations of knowledge graphs.
It is a promising time for research into the construction and application of knowledge graphs.
The peer reviewed literature is growing at an increasing rate and maintaining a complete understanding is becoming increasingly challenging for scientists.
One path that scientists can take to maintain awareness is to become hyper-focused on specific areas of knowledge graph literature.
If advances in how these graphs are constructed, represented and applied can enable the linking of fields, we may be able to savor the benefits of this detailed knowledge without losing the broader contextual links.


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>
