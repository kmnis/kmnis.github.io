---
layout: post
title: Introduction to different datasets available in Computational Chemistry
excerpt_separator: <!--more-->
---

The advances in Machine Learning field have proven useful ranging from applications in Natural Language Processing to Computer Vision. These remarkably successful demonstrations have drawn high interests from the physical and biological science communities.

For instance, ML-enhanced abilities to predict molecular properties with high precision, efficient generations of novel molecular structures, and better strategies in synthesis planning and rectrosynthesis will significantly accelerate drug design and novel material discovery. However, the scarcity of high-quality datasets and the lack of transferability of ML techniques impede the wide-scale adoption of molecular ML techniques in practice.
<!--more-->
Here, I introduce a collection of most common datasets which can be used in the field.

<h4> Tox21</h4>
The goal of this dataset is to check if compounds' interference in biochemical pathways using only chemical structure data can be predicted. In simple words, it’s to check if a particular assay is toxic to human health or not. It contains data for 12 assays for 10,000 compounds. Check it out <a target="_blank" href="https://tripod.nih.gov/tox21/challenge/data.jsp">here</a>.

#### QM9
This dataset contains computed geometric, energetic, electronic, and thermodynamic properties for 134k stable small organic molecules made up of CHONF(Carbon - Hydrogen - Oxygen - Nitrogen - Fluorine). These molecules correspond to the subset of all 133,885 species with up to nine heavy atoms (CONF) out of the GDB-17 chemical universe of 166 billion organic molecules. The geometries are, according to authors, minimal in energy, corresponding harmonic frequencies, dipole moments, polarizabilities, along with energies, enthalpies, and free energies of atomization. Check it out <a target="_blank" href="http://quantum-machine.org/datasets/">here</a>.

#### ZINC-15
ZINC-15 is a dataset of commercially available molecules. It has over 750 million molecules and is one of the standard sets used by research and biotech companies. In addition to the SMILES, it also holds other information about each molecule such as its physicochemical properties and commercial sales related information. Check it out <a target="_blank" href="http://zinc15.docking.org">here</a>.

#### PCBA
This is a comprehensive dataset including 128 assays for over 400k molecules. In the file pcba.csv there are 130 columns, in which the first 128 columns represent the outcomes for these essays. In other word, each column contains labels(0 or 1) for an individual task(assay). The last 2 columns are identifiers for molecules. Smiles representation of molecules is used to represent and featurize them. Download it <a target="_blank" href="https://raw.githubusercontent.com/deepchem/deepchem/master/datasets/pcba.csv.gz">here</a>.

#### Maximum Unbiased Validation (MUV)
MUV consists of assay data from 17 targets, each with 30 actives and 15000 decoys. Actives were selected from confirmatory screens and were chosen to be maximally
spread based on simple descriptors and embedded in decoys. The decoys were selected from a primary screen for the same target. In short, these data sets were designed to be difficult for VS methods. Download it <a target="_blank" href="https://s3-us-west-1.amazonaws.com/deepchem.io/datasets/muv.csv.gz">here</a>.
