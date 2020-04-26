# Response to Reviwers

## Reviewer 1

>The authors review how knowledge graphs can be applied in the context of biomedical applications. I found the review to be well-written, highly organized and informative. I have no substantial suggestions and recommend acceptance.

>Minor suggestions which can be fixed by authors in the editorial process:

> - Table 1: What is the organizing principle behind the order of the databases? Would it be better to order them alphabetically?
> - "or though the use"?
> - "into a subphrases"?
> - Table 3: Maybe define or spell out the Types of Sentences.
> - "This values within"?
> - "uses a matrices"?
> - "other effots"?
> - "then determines how"?
> - Figure 5b: Font too small
> - "goal of recommend safe drugs"

We would like to thank the reviewer for noticing these. We have fixed the typos.

## Reviewer 2

>The manuscript attempts to review methods for knowledge graphs and their biomedical applications. 
>The review is too general. 
>It tries to combine disparate lines of research ranging from dimensionality reduction, manifold learning, to graph community detection and frame it under knowledge graph learning. 
>Although no established definition of knowledge graph exists, an essential property of a knowledge graph is that it models relations between nodes, which don't apply to dimensionality methods (SVD,PCA,,etc.) and other methods such as node2vec. 
>Almost all of the discussions in this manuscript deals with methods that don't model relations. 
>The only part that correctly refers to a class knowledge graph methods is translational distance methods.  

>The following are some comments: 

>**What specifically do you mean by techniques that represent KGs and machine learning methods that are used to learn low-dimensional vectors?

We implicate that techniques represent knowledge graphs by associating nodes and possibly edges to dense vectors.
These dense vectors can be utilized to perform task such as link predictions, node classification, node similarity calculations etc.
Machine learning methods be used to either make the association between nodes and these vectors or be used to make classification calls using these vectors as input.
In this revision we will clarify text to highlight this association and be distinct on the difference between machine learning methods that make the association and methods that are used to perform tasks.

>**at least references 1, 2, 5,6 and 2 are concerned with methods for graphs not necessarily knowledge graphs, in which the edge label (i.e., relation is essential to its definition).

We acknowledge that these references use general methods for knowledge graphs; however, we use these references to exemplify the fact that the graphs used are considered knowledge graphs.

>**Figure 1 doesn't show the relationship direction, For example, "causes", "binds" and other relations don't clearly specify the source and destination nodes which can be confusing.
>Ideally, a knowledge graph should show that. 
>Please have a look at some knowledge graphs reviews in literature. 
>For example, https://arxiv.org/pdf/1503.00759.pdf 

Figure one uses the same network schema as used in Project Rephetio (https://elifesciences.org/articles/26726).
The authors on that project intentionally kept the edges as undirected; however,
we agree that some relationships can have ambiguous directionality (e.g. upregulates/downregulates can infer gene upregulates disease or disease upregulates a gene).
For this revision, we plan to update the text to state that our example knowledge graph can have bidirectionality.

>**"relatively precise data, but in low quantifies"?

This statement means the quality of curated data is of high grade, but the amount of data inserted into databases is quite small. 
In other words, manual curation provides results that have high precision but low recall.
The quantifies is a typo and should be quantities and will be fixed when the revision processed is finished.

>**what you refer to as "unifying techniques" is relational learning, I don't see why you refer to it in such an ambiguous way. 
>Furthermore, grouping the techniques into three is so broad and doesn't correctly represent knowledge graphs methods. 
>For example, matrix factorization and deep learning. 
>Matrix factorizations such as isomap, PCA, SVD and others are not knowledge graph representation techniques, but dimensionality reduction techniques.
> More importantly, you don't show how they can be applied or used in the context of knowledge graphs as claimed?

We agree that the title for that section is a bit broad and we updated the text to accommodate the suggestion.
You are correct in stating that these methods are not knowledge graph specific; however, they can be used on knowledge graphs to associate nodes to dense vectors (low dimensional space).
We provided a reference that used SVD and other matrix factorization methods to perform this association for link prediction tasks and node classification tasks.
In this revision we will update text to be more explicit on how these class of methods can be used on knowledge graphs.

>**word2vec is a shallow neural network (one layer for projection, no activation or non-linearity is used in this layer), therefore it is deep learning, nor any of the methods which use similar techniques.

We agree that word2vec, node2vec and similar methods use a shallow neural network.
We have decided to update the title and text to refer to these models as "neural network models".
