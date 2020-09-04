---
layout: project
title: Chemical Reaction Predictor
permalink: /projects/chemical-reaction-predictor
start_date: '2020-07-30'
end_date: '2020-08-24'
related_projects: 
    - Chemical Reaction Yield Predictor
related_projects_url: 
    - chemical-reaction-yield-predictor
tags: 
    - drug-discovery
    - deep-learning
    - GCN
    - tensorflow
    - python
project_sort_order: 2
---

<p style="text-align: justify">
This project was related to the prediction of main- and side-products of a chemical reaction given the reactants, reagent(s), and solvent(s) using Deep Learning. The ability to anticipate reaction products correctly enables chemists to realize more quickly the chemical compounds that they desire which in turn enables them to design appropriate lab conditions, saving both time and money.</p>

<p style="text-align: justify">
I divided the task into two stages: First identifying the possible sites of reactivity and second evaluating their relative likelihoods of reaction. The <span style="color: #bf616a; background-color: #f9f9f9">Graph Convolutional Network(GCN)</span> was used as the model architecture and various atomic properties as base features for both the tasks. The trained model made ten predictions for each reaction and more than <span style="color: #bf616a; background-color: #f9f9f9">90%</span> of the time, correct products were among these predictions. Its performance was on par with expert chemists with many years of training.
</p>
