---
layout: post
title: Different methods to represent Chemical Molecules (Part 1)
excerpt_separator: <!--more-->
---

<!-- - SMILES
- mol2
- InChi/InChiKey
- Open Babel
- RdKit
- DeepChem
- ECFP Fingerprints
- Atomic Features
- Adjacency Matrix
- NWChem -->

### SMILES String
SMILES (Simplified molecular-input line-entry system) is a line notation method to represent molecules as well as reactions. It is also the most common method to represent molecules because of its simplicity and readability to the human eye.

Below are a few examples just to give you an idea about the notation. Don't worry, we will go into details next on how to write these notations.
```yaml
Propane: CCC
Butane:  CCCC
Ethene:  C=C
```
<!--more-->

#### Atoms
All non-Hydrogen atoms are represented by their atomic symbols. In a SMILES string, any unfulfilled valency of an atom is assumed to be Hydrogen. For example, writing a simple `C` means that it's actually a CH<sub>4</sub> (Methane) and not an elemental Carbon. Similarly, `N` is NH<sub>3</sub> (Ammonia) and `O` is H<sub>2</sub>O (Water). 

To represent elemental atoms, a `[]`(Square bracket) notation is used. For example, `[S]` is elemental Sulfur. In case you want to explicitly add the Hydrogens to a SMILES string, the square bracket can be used here as well. For example, Methane and Ethane can be written as `[CH4]` and `[CH3][CH3]` respectively. 

#### Bonds
Single, double, and triple bonds are represented by the symbols `-`, `=`, and `#`, respectively. Same as Hydrogens, single bonds are often omitted for simplicity. Adjacent atoms are assumed to be connected by a single or aromatic bond. 

NOTE: As you may have guessed by now, there can be multiple ways to represent a molecule in the SMILES string. For example, all the following notations are correct for Ethane: `CC`, `C-C`, `[CH3]-[CH3]`, `[CH3]-C`

Here are a few more examples:

<table>
  <caption style="caption-side:bottom; margin-top: 5px">Table 1</caption>
  <thead>
    <tr>
      <th>Molecule</th>
      <!-- <th>Chemical Formula</th> -->
      <th>SMILES</th>
      <th>Alternate SMILES</th>
      <th>Structure</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Ethene</td>
      <!-- <td>CH<sub>2</sub>-CH<sub>2</sub></td> -->
      <td>C=C</td>
      <td>[CH2][CH2]</td>
      <td><img style="margin: auto" src="/_images/ethene.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Formaldehyde</td>
      <!-- <td>CH<sub>2</sub>O</td> -->
      <td>C=O</td>
      <td>[CH2]=O</td>
      <td><img style="margin: auto" src="/_images/formaldehyde.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Carbon Dioxide</td>
      <!-- <td>CO<sub>2</sub></td> -->
      <td>O=C=O</td>
      <td>C(=O)=O</td>
      <td><img style="margin: auto" src="/_images/carbondioxide.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Hydrogen Cyanide</td>
      <!-- <td>HCN</td> -->
      <td>C#N</td>
      <td>[CH]#N</td>
      <td><img style="margin: auto" src="/_images/hydrogencyanide.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Ethanol</td>
      <!-- <td>CH<sub>3</sub>CH<sub>2</sub>OH</td> -->
      <td>CCO</td>
      <td>CC[OH]</td>
      <td><img style="margin: auto" src="/_images/ethanol.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Propionic Acid</td>
      <!-- <td>CH<sub>3</sub>CH<sub>2</sub>CO<sub>2</sub>H</td> -->
      <td>CCC(=O)O</td>
      <td>[CH3][CH2]C(O)=O</td>
      <td><img style="margin: auto" src="/_images/propionicacid.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Methyl Isocyanate</td>
      <!-- <td>CH<sub>3</sub>NCO</td> -->
      <td>CN=C=O</td>
      <td>[CH3]N=C=O</td>
      <td><img style="margin: auto" src="/_images/methylisocyanate.svg" width="50%"/></td>
    </tr>
  </tbody>
</table>

#### Charged Molecules
In case of charged atoms or molecules, the square bracket notation is the way to go again. The positive charge is represented by a `+` sign and a negative charge by `-` sign. Some examples to clarify:

<table>
  <caption style="caption-side:bottom; margin-top: 5px">Table 2</caption>
  <thead>
    <tr>
      <th>Molecule</th>
      <th>SMILES</th>
      <th>Structure</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Sodium Ion</td>
      <td>[Na+]</td>
      <td><img style="margin: auto" src="/_images/sodiumion.svg" width="30%"/></td>
    </tr>
    <tr>
      <td>Ammonium Cation</td>
      <td>[NH4+]</td>
      <td><img style="margin: auto" src="/_images/ammoniumcation.svg" width="30%"/></td>
    </tr>
    <tr>
      <td>Hydroxyl Anion</td>
      <td>[OH-]</td>
      <td><img style="margin: auto" src="/_images/hydroxylanion.svg" width="30%"/></td>
    </tr>
  </tbody>
</table>

#### Branched Molecules
In some of the molecules in Table 1, you might have noticed a `()`(parentheses) in some of the SMILES. These parentheses indicate a branch in the molecule.

Let's take the example of Propionic Acid. If the green highlighted atoms are taken as a base chain then yellow highlighted atoms will become a branch.

<img style="margin: auto" src="/_images/propionicacidhighlight1.svg" width="20%" style="float: left"/>
<img style="margin: auto" src="/_images/propionicacidhighlight2.svg" width="20%"/>

In either case, there's a branch and like we just discussed, parentheses are used to create a branch in the SMILES string. So both the following strings are correct for Propionic Acid: `CCC(=O)O`, `CCC(O)=O`

#### Cyclic Structures/Ring Molecules
All the examples we have seen so far were noncyclic structures. Now, we'll see how to represent cyclic structures. Ring structures are written by breaking each ring at an arbitrary point to make an acyclic structure and adding numerical ring closure labels to show connectivity between non-adjacent atoms.

Let's take the example of Cyclohexane. If we break the structure at the marked bond, it'll become a linear structure.
<img style="margin: auto" src="/_images/cyclohexane.png" width="20%"/>

Then we assign a number to both the atoms between which the bond was broken. In this case, the structure is symmetric and hence it doesn't matter which bond we break. The SMILES string will now become `C1CCCCC1`.

What if there are 2 rings? Then we break one bond each from both the rings and assign separate numbers to each involved atom. Let's take a look at a few examples to understand it better.

<table>
  <caption style="caption-side:bottom; margin-top: 5px">Table 3</caption>
  <thead>
    <tr>
      <th>Molecule</th>
      <th>SMILES</th>
      <!-- <th>Alternate SMILES</th> -->
      <th>Structure</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1,4-Cyclohexadiene</td>
      <td>C1=CCC=CC1</td>
      <!-- <td>C1C=CCC=C1</td> -->
      <td><img style="margin: auto" src="/_images/1,4-cyclohexadiene.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Benzene</td>
      <td>C1=CC=CC=C1</td>
      <!-- <td></td> -->
      <td><img style="margin: auto" src="/_images/benzene.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Toluene</td>
      <td>C1=C(C)C=CC=C1</td>
      <!-- <td>C1=CC=CC(C)=C1</td> -->
      <td><img style="margin: auto" src="/_images/toluene.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Decalin</td>
      <td>C1CCC2CCCCC2C1</td>
      <!-- <td>C2CCC1CCCCC1C2</td> -->
      <td><img style="margin: auto" src="/_images/decalin.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Bicyclohexyl</td>
      <td>C1CCC(C2CCCCC2)CC1</td>
      <!-- <td>C1CCC(CC1)C2CCCCC2</td> -->
      <td><img style="margin: auto" src="/_images/bicyclohexyl.svg" width="50%"/></td>
    </tr>
  </tbody>
</table>

#### Aromatic Compounds
The aromatic compounds can be represented by the methods we have learned so far. However, there is a preferred way to represent them: aromatic atoms are represented by lowercase letters. For example, aromatic Carbon by `c`, Nitrogen by `n`, Boron by `b`, and so on.

Let's start with the famous molecule, Benzene. In Table 3, we already showed that Benzene can be represented by `C1=CC=CC=C1`. By this new method, now Benzene can be written as `c1ccccc1`. Here, adjacent atoms are not assumed to be connected by a single bond but rather the lowercase letters tells us that this is a aromatic ring signifying alternate single and double bonds. Let's look at few more examples below:

<table>
  <caption style="caption-side:bottom; margin-top: 5px">Table 4</caption>
  <thead>
    <tr>
      <th>Molecule</th>
      <th>SMILES</th>
      <!-- <th>Alternate SMILES</th> -->
      <th>Structure</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Phenol</td>
      <td>c1cc(O)ccc1</td>
      <!-- <td>C1(O)C=CCC=C1</td> -->
      <td><img style="margin: auto" src="/_images/phenol.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Pyridine</td>
      <td>c1ccncc1</td>
      <!-- <td>C1=CC=NC=C1</td> -->
      <td><img style="margin: auto" src="/_images/pyridine.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Benzoic Acid</td>
      <td>c1cc(C(O)=O)ccc1</td>
      <!-- <td>C1=CC(C(O)=O)=CC=C1</td> -->
      <td><img style="margin: auto" src="/_images/benzoicacid.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Isoquinoline</td>
      <td>c1ccc2cnccc2c1</td>
      <!-- <td>C2=CC=C1C=NC=CC1=C2</td> -->
      <td><img style="margin: auto" src="/_images/isoquinoline.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Biphenyl</td>
      <td>c1ccc(-c2ccccc2)cc1</td>
      <!-- <td>C1=CC=C(C2=CC=CC=C2)C=C1</td> -->
      <td><img style="margin: auto" src="/_images/biphenyl.svg" width="50%"/></td>
    </tr>
  </tbody>
</table>

#### Disconnected Structures
The ions in the ionic molecules are not connected by a covalent bond with each other. Such disconnected compounds are written as individual structures separated by a `.` (period). For example, Sodium Hydroxide will be written as `[Na+].[OH-]`.

The order in which ions or ligands are listed is arbitrary. There is no implied pairing of one charge with another, nor is it necessary to have a net-zero charge. Below are a few examples to understand it better.

<table>
  <caption style="caption-side:bottom; margin-top: 5px">Table 5</caption>
  <thead>
    <tr>
      <th>Molecule</th>
      <th>SMILES</th>
      <th>Structure</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Sodium Phenoxide</td>
      <td>[Na+].[O-]c1ccccc1</td>
      <td><img style="margin: auto" src="/_images/sodiumphenoxide.svg" width="50%"/></td>
    </tr>
    <tr>
      <td>Sodium Chloride</td>
      <td>[Na+].[Cl-]</td>
      <td><img style="margin: auto" src="/_images/sodiumchloride.svg" width="50%"/></td>
    </tr>
  </tbody>
</table>
