# Algorithmic Tools for Mining the Motif Structure of Networks  
# ECML-PKDD '22

Motifs are small subgraph patterns that play a key role towards understanding the structure and the function of biological and social networks. The current *de facto* approach towards assessing the statistical significance of a motif $\mathcal{M}$ relies on counting its occurrences across the network, and comparing that count to its expected count   under some null generative model. This approach can be misleading due to *combinatorial artifacts*.  That is, there may be a large count for a motif due to multiple copies sharing many vertices and edges connected to a subgraph, such as a clique, that completes the multiple copies of the motif.   In this repository we provide a set of tools for understanding the motif structure of networks. 

- We introduce the novel concept of an (f,q)-spanning motif. A motif is (f,q)-spanning if there exists a  q-fraction of the nodes that induces an f-fraction of the occurrences of the motif in $G$. Intuitively, when f is close to 1, and $q$ close to 0, most of the occurrences of the motif are localized in a small set of nodes, and  thus its statistical significance is likely to be due to a combinatorial artifact. We propose efficient heuristics for finding the maximum f for a given $q$ and minimum q for a given f for which a motif is (f,q)-spanning and evaluate them on real-world datasets. Our methods successfully identify combinatorial artifacts that otherwise go undetected using the standard approach for assessing statistical significance.   

- We provide an algorithm that can contrast two motifs, and outputs a motif that is dense in one, and sparse in the other. This tool allows us to find anomalies in in large networks, including bipartite cliques in social graphs, and subgraphs rated with distrust in Bitcoin  markets.  

- We perform an extensive experimental analysis of different generative models with respect to how they assess statistical significance. 

# Datasets

We upload the C. elegans - brain network in the dataset folder. For the rest datasets, links are provided.

PPI networks: http://interactome.dfci.harvard.edu/index.php?page=home

hamsterster: https://networkrepository.com/soc-hamsterster.php

Eris1176: https://networkrepository.com/power-eris1176.php

Bitcoin networks and LastFM, Twitch: https://snap.stanford.edu/data/index.html

# Code

To run all the notebooks, install Python3 and required packages. Note we recommend install graphtool using conda before adding other packages into the environment, see https://graph-tool.skewed.de/. 

Please add an empty \_\_init__.py file into the pattern_contrast folder if the corresponding modules cannot be found.

#### Competitors

We use spartan2 for most of the competitors evaluated in the paper for anomaly detection, see https://github.com/BGT-M/spartan2-tutorials.
