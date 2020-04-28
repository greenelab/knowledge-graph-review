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

**We would like to thank the reviewer for noticing these. We have fixed the typos.**

## Reviewer 2

>The manuscript attempts to review methods for knowledge graphs and their biomedical applications. 
>The review is too general. 
>It tries to combine disparate lines of research ranging from dimensionality reduction, manifold learning, to graph community detection and frame it under knowledge graph learning. 
>Although no established definition of knowledge graph exists, an essential property of a knowledge graph is that it models relations between nodes, which don't apply to dimensionality methods (SVD,PCA,,etc.) and other methods such as node2vec. 
>Almost all of the discussions in this manuscript deals with methods that don't model relations. 
>The only part that correctly refers to a class knowledge graph methods is translational distance methods.  

**We appreciate the reviewers perspective; however, we believe the scope of this review is within reason.
The focus of this review is to discuss the pros and cons of building knowledge graphs and representing them in a low dimensional space.
This space is constructed based on the edges that are shared between nodes, which means relational information is implicitly captured by techniques mentioned in this review.
We note that some techniques collapses edges into a single entity, which results in some relational information being lost.**

>The following are some comments: 

>What specifically do you mean by techniques that represent KGs and machine learning methods that are used to learn low-dimensional vectors?

**When we say "techniques that represet knowledge graphs in a low dimensional space", we allude to methods such as node2vec and translational distance models that associate nodes and possibly edges to list of numbers (i.e., dense vectors).
As previously mentioned these dense vectors implicitly capture relational information from the knowledge graph itself.
We also discuss in this review that these dense vectors can be used as input to machine learning methods for biomedical applications.**

>at least references 1, 2, 5,6 and 2 are concerned with methods for graphs not necessarily knowledge graphs, in which the edge label (i.e., relation is essential to its definition).

**We define knowledge graphs as the following: "a resource that integrates single or multiple sources of information into the form a graph where nodes repesent entities and edges represent relationships that are shared between two entities".
Based on our definition, the graphs in these resources are considered knowledge graphs.
The methods described in these resources collapse edges into a single entity, which means some relational information is lost; however, we highlight this flaw in our review.**

>Figure 1 doesn't show the relationship direction, For example, "causes", "binds" and other relations don't clearly specify the source and destination nodes which can be confusing.
>Ideally, a knowledge graph should show that. 
>Please have a look at some knowledge graphs reviews in literature. 
>For example, https://arxiv.org/pdf/1503.00759.pdf 

**We appreciate the reviewer pointing out this fact.
We updated our figure to reflect edge directionality and updated the text to note that some edges can be considered bidirectional.**

```diff
- A metagraph (schema) of the heterogeneous network used in the Rephetio project [..].
- This undirected network depicts pharmacological and biomedical information.
- The nodes (circles) represent entities and edges (lines) depict relational information between two entities.

+ The metagraph (i.e., schema) of the knowledge graph used in the Rephetio project [..].
+ The authors of this project refer to their resource as a heterogenous network (i.e., hetnet); however, we consider a hetnet to be synonymous to our definition of a knowledge graph.
+ This resources depicts pharmacological and biomedical information in the form of nodes and edges. 
+ The nodes (circles) represent entities and edges (lines) represent relationships that are shared between two entities.
+ Majority of edges in this metagraph are depicted as unidirectional, but some relationships can be considered bidirectional.
```

>"relatively precise data, but in low quantifies"?

**We like to thank the reviewer for pointing out this typo.
"Quantifies" should be "quantities" and this statement was designed to convey that manual curation results in high precision but suffers from low recall.
We updated the text to fix this issue.**

```diff
- Studies have shown that databases constructed in this fashion contain relatively precise data, but in low quantifies 
+ Studies have shown that databases constructed in this fashion contain relatively precise data but the recall is low
```

>what you refer to as "unifying techniques" is relational learning, I don't see why you refer to it in such an ambiguous way. 
>Furthermore, grouping the techniques into three is so broad and doesn't correctly represent knowledge graphs methods. 
>For example, matrix factorization and deep learning. 
>Matrix factorizations such as isomap, PCA, SVD and others are not knowledge graph representation techniques, but dimensionality reduction techniques.

**We appreciate the reviewer's perspective; however, given the scope of this review, we believe our technique groups are within reason.
We agree that the title for this section is a bit ambigious and we have changed our title to the following: "representational learning techniques" (diff provided below).
Given our defintion of knowledge graphs, we view that the methods we disucss can be applied to knowledge graphs.**

```diff
- In the next sections we review the unifying techniques that construct this low dimensional space and unifying applications that use this space to solve biomedical problems.

- Unifying Techniques

+ In the following sections we review methods that construct this low dimensional space (Unifying Representational Learning Techniques) and discuss applications that use this space to solve biomedical problems (Unifying Applications).

+ Unifying Representational Learning Techniques
```

> More importantly, you don't show how they can be applied or used in the context of knowledge graphs as claimed?

**We agree that the text wasn't explicit enough on definiting how some techniques apply to knoweledge graphs. 
We have updated our text to emphasize this point.**

```diff
- In practice $U$ is usually used to represent nodes in a knowledge graph, but $V^{T}$ can also be used [..;..].

+In practice $U$ is usually used to represent nodes in a knowledge graph and can be used as input for machine learning classifiers to perform tasks such as link prediction or node classification [@doi:10.1093/bioinformatics/btz718]; however,$V^{T}$ can also be used [..;..].
```

```diff
- Common approaches involve using SVD, Laplacian eigenmaps or variants of the two to construct low dimensional representations.

+ Common approaches involve using SVD, Laplacian eigenmaps or variants of the two to decompose matrices into smaller rectangular forms.
+ Regarding knowledge graphs, the adjacency matrix ($A$) is the typical matrix that gets decomposed, but the laplacian matrix ($L=D-A$) can be used as well.
```

>word2vec is a shallow neural network (one layer for projection, no activation or non-linearity is used in this layer), therefore it is deep learning, nor any of the methods which use similar techniques.

**We agree that word2vec, node2vec and similar methods use a shallow neural network, which means these models aren't considered deep learning.
We updated the title to be "Neural networks" and replaced instances of deep learning with neural networks.**

```diff
- Deep Learning

- Deep learning is a paradigm that uses multiple non-linear transformations to map high dimensional data into a low dimensional space.
- Many techniques that use deep learning on knowledge graphs are based on word2vec [..;..], a set of approaches that are widely used for natural language processing.

+ Neural Networks

+ Neural networks are a class of machine learning models inspired by the concept of biological neural networks [..].
+ These networks are reputable for making non-linear transformations of high dimensional data to solve classification and regression problems [..].

+ In the context of knowledge graphs, the most commonly used structures are based on word2vec [..;..].
```
