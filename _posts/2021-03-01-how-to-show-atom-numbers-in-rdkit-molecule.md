---
layout: post
title: How to show atom numbers in a RdKit molecule (or how to label atoms in a rdkit molecule)
excerpt_separator: <!--more-->
image: /_images/benzamide.svg
show_main_img_in_blog: false
author: Manish Sihag
social-share: true
tags:
  - RdKit
---

In RdKit, the method `SetProp` is used to set an atomic property for the atoms involved in the molecule. This method takes two arguments: the peroperty to set and its value. The idea is simple: Create an rdkit mol object from SMILES string, iterate over the atoms, and set the desired property to a custom value.

<!--more-->

For this article, we'll look at three different ways to show atom numbers. We'll take the example of Benzamide to show the modifications.
<img style="margin: auto" src="/_images/benzamide.svg">

First of all import the necessary packages:
```python
from rdkit import Chem
from rdkit.Chem.Draw import IPythonConsole
```

#### 1. Atom numbers along with the atoms
To show atom numbers along with the atom symbols, we need to set the `molAtomMapNumber` property of the atoms.

```python
# Create an rdkit mol object
mol = Chem.MolFromSmiles('c1ccccc(C(N)=O)1')

# Iterate over the atoms
for i, atom in enumerate(mol.GetAtoms()):
    # For each atom, set the property "molAtomMapNumber" to a custom number, let's say, the index of the atom in the molecule
    atom.SetProp("molAtomMapNumber", str(atom.GetIdx()+1))

mol
```
And the molecule, now, will look like:
<img style="margin: auto" src="/_images/numbered-atoms-benzamide.svg">

#### 2. Custom labels in place of the atoms
If you want to replace the atom symbols with a custom value, set the `atomLabel` property of the atoms to a desired value.

```python
# Create an rdkit mol object
mol = Chem.MolFromSmiles('c1ccccc(C(N)=O)1')

# Iterate over the atoms
for i, atom in enumerate(mol.GetAtoms()):
    # For each atom, set the property "atomLabel" to a custom value, let's say a1, a2, a3,...
    atom.SetProp("atomLabel", f"a{i+1}")

mol
```
The molecule will change as:
<img style="margin: auto" src="/_images/labeled-atoms-benzamide.svg">

#### 3. Atom numbers on top of the atoms
Both the previous methods have two issues: First, it can become overly crowded at times when adding the atom numbers and second, the visual appeal goes away. A better way to annotate the atoms is by showing the numbers separate from the atomic symbols. To achieve this, set the `atomNote` property of the atoms.

```python
# Create an rdkit mol object
mol = Chem.MolFromSmiles('c1ccccc(C(N)=O)1')

# Iterate over the atoms
for atom in mol.GetAtoms():
    # For each atom, set the property "atomNote" to a index+1 of the atom
    atom.SetProp("atomNote", str(atom.GetIdx()+1))

mol
```
And we'll get a much cleaner look for the molecule:
<img style="margin: auto" src="/_images/noted-atoms-benzamide.svg">

#### Summary
In this article, we saw three different ways to annotate atoms in RdKit. The annotation doesn't have to be a number but can be any label. This method is also useful when you want to annotate only a selected atoms. Let's say that you want to mark only the Nitrogen atom with a label, say `Nitrogen`. You can achieve this as follows:

```python
mol = Chem.MolFromSmiles('c1ccccc(C(N)=O)1')
for atom in mol.GetAtoms():
    if atom.GetSymbol() == "N":
        atom.SetProp("atomNote", "Nitrogen")
mol
```
<img style="margin: auto" src="/_images/n-marked-benzamide.svg">

And that's it for this article. If you have any doubts/suggestions/criticism, feel free to post them in the comments. Until next time.