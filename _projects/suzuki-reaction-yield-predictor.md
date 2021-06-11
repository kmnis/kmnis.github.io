---
layout: project
title: Suzuki Reaction Yield Predictor
start_date: '2019-02-03'
end_date: '2019-12-15'
permalink: /projects/suzuki-reaction-yield-predictor
tags: 
    - drug-discovery
    - GCN
    - tensorflow
    - deep-learning
    - quantum-computations
project_sort_order: 3
author: Manish Sihag
---

<p style="text-align: justify">Chemical reaction experimentations in a lab is a slow and expensive process. Even after getting the right products for a chemical reaction, chemists need to know how much of a product will form. Getting the actual yield of a reaction is needed for drug synthesis planning and is quite advantageous to decide on whether a synthesis path is to be preferred or avoided.</p>

<p style="text-align: justify">This project was related to predicting the yield of a Suzuki class of chemical reactions given the actual product. This was an 11 month long, end-to-end project which included tasks from acquiring and cleaning data from various sources to deploying deep learning models on servers for client usage.</p>

<p style="text-align: justify">With nearly 500+ machine learning and deep learning models trained, this project required steps from featurizing chemical molecules into numerical vectors to performing quantum computations.</p>

### Structuring the problem
There were mainly three approaches tried to structure the problem:

1. Predicting the yield of reactions
2. Classifying reactions into high- and low-yielding reactions
3. Ranking a given list of reactions in the order of their yields

### List of descriptors
Following descriptors were experimented in different combinations for modelling:

1. Occupancy descriptors
2. Potential energy in a grid
3. Unversal Force Field (UFF) parameters
4. ECFP features
5. Modified ECFP features
6. DFT-based properties
7. Atom Pair - Bond Pair (AP-BP) descriptors
8. Functional Group decmposition
9. Structural properties
10. Experimental conditions

### Models
Many models were tried for the problem. Some of them includes:

1. RandomForest
2. XGBoost
3. Feed Forward Neural Network
4. Graph Convolutional Network
5. Gated Graph Convolutional Network
6. Attention Graph Convolutional Network
7. Gated-Attention Graph Convolutional Network

<p style="text-align: justify">The implementation code is propriety property of <a href="https://aganitha.ai/" target="_blank">Aganitha Cognitive Solutions</a>.</p>
