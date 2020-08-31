---
layout: project
title: Chemical Reaction Predictor
permalink: /projects/chemical-reaction-predictor
start_date: '2020-07-30'
end_date: '2020-08-24'
related_projects: 
    - proj2
    - Covid Browser
related_projects_url: 
    - proj2
    - covid-browser
tags: 
    - drug-discovery
    - deep-learning
    - GCN
    - tensorflow
    - python
---

<p style="text-align: justify">
This project was related to the prediction of main- and side-products of a chemical reaction given the reactants, reagent(s), and solvent(s) using Deep Learning. The ability to anticipate reaction products correctly enables chemists to realize more quickly the chemical compounds that they desire which in turn enables them to design appropriate lab conditions, saving both time and money.</p>

<p style="text-align: justify">
I divided the task into two stages: First identifying the possible sites of reactivity and second evaluating their relative likelihoods of reaction. The Graph Convolutional Network(GCN) was used as the model architecture and various atomic properties as base features for both the tasks. The trained model made ten predictions for each reaction and more than 90% of the time, correct products were among these predictions. Its performance was on par with expert chemists with many years of training.
</p>
