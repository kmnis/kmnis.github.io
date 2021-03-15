---
layout: post
title: Mol2 file format explained for beginners (Cheminformatics Part 2)
excerpt_separator: <!--more-->
tags:
  - Cheminformatics
---

Welcome to the second blog in the 10 part [Cheminformatics for Beginners](/tags.html#cheminformatics) series. In the [last](/2021/02/13/smiles-strings-explained-for-beginners-part-1.html) blog, we saw a quick introduction to the SMILES notation. This post will introduce you to the mol2 format in cheminformatics.

### Introduction
One major setback from the SMILES notation was that it could not provide the positions of each atom in space, typically with X, Y, and Z cartesian coordinates. Mol2 file solves this problem. It is a plain text tabular format that represents a single or multiple chemical compounds and holds atomic coordinates, chemical bond information, and metadata of a molecule.

<!--more-->
### Anatomy of a mol2 file
A mol2 file consists of multiple sections with each section containing a part of the information about the molecule. For example, the section `@<TRIPOS>ATOM` contains atomic coordinates, and the section `@<TRIPOS>BOND` contains information about how atoms are connected

There are 32 sections in the file but for this tutorial, we'll restrict ourselves to only the 3 most important sections, namely: `@<TRIPOS>MOLECULE`, `@<TRIPOS>ATOM` and `@<TRIPOS>BOND`. Let's see a sample mol2 file for benzene and then jump into each of the sections in detail.

NOTE: Each line in the following example is numbered starting from 1 to end at 38. These numbers are not a part of the mol2 file but rather for easy reference in the following discussion.
```
1   # Name: benzene
2   # Creating user name: ChemicBook
3   # Creation time: Sat Mar 20 00:18:30 2021
4   
5   @<TRIPOS>MOLECULE
6   benzene
7    12 12 0 0 0
8   SMALL
9   NO_CHARGES
10  ****
11  Any comment about the molecule goes here. No need for a pound sign here
12  
13  @<TRIPOS>ATOM
14        1 C          -0.7600    1.1691   -0.0005 C.ar    1  BENZENE       0.000
15        2 C           0.6329    1.2447   -0.0012 C.ar    1  BENZENE       0.000
16        3 C           1.3947    0.0765    0.0004 C.ar    1  BENZENE       0.000
17        4 C           0.7641   -1.1677    0.0027 C.ar    1  BENZENE       0.000
18        5 C          -0.6288   -1.2432    0.0001 C.ar    1  BENZENE       0.000
19        6 C          -1.3907   -0.0751   -0.0015 C.ar    1  BENZENE       0.000
20        7 H          -1.3536    2.0792    0.0005 H       1  BENZENE       0.000
21        8 H           1.1243    2.2140   -0.0028 H       1  BENZENE       0.000
22        9 H           2.4799    0.1355   -0.0000 H       1  BENZENE       0.000
23       10 H           1.3576   -2.0778    0.0063 H       1  BENZENE       0.000
24       11 H          -1.1202   -2.2126   -0.0005 H       1  BENZENE       0.000
25       12 H          -2.4759   -0.1340   -0.0035 H       1  BENZENE       0.000
26  @<TRIPOS>BOND
27       1     1     2   ar
28       2     2     3   ar
29       3     3     4   ar
30       4     4     5   ar
31       5     5     6   ar
32       6     1     6   ar
33       7     1     7    1
34       8     2     8    1
35       9     3     9    1
36      10     4    10    1
37      11     5    11    1
38      12     6    12    1
```

### @\<TRIPOS\>MOLECULE
Each data record associated with this section consists of six data lines:
1. The first data line is the name of the molecule(line 6)
2. The second data line contains the number of atoms, bonds, substructures, features, and sets associated with the molecule(line 7)
3. The third data line is the molecule type(line 8). The supported types are `SMALL`, `BIOPOLYMER`, `PROTEIN`, `NUCLEIC_ACID`, and `SACCHARIDE`
4. The fourth data line tells the type of charges associated with the molecule(line 9). The supported types are `NO_CHARGES`, `DEL_RE`, `GASTEIGER`, `GAST_HUCK`, `HUCKEL`, `PULLMAN`, `GAUSS80_CHARGES`, `AMPAC_CHARGES`, `MULLIKEN_CHARGES`, `DICT_CHARGES`, `MMFF94_CHARGES`, and `USER_CHARGES`
5. The fifth data line contains the internal SYBYL status bits associated with the molecule(line 10). These should never be set by the user. Valid status bits are `system`, `invalid_charges`, `analyzed`, `substituted`, `altered` or `ref_angle`. This is optional.
6. The last data line contains any comment which may be associated with the molecule(line 11)

**Format:**
```
mol_name
num_atoms [num_bonds [num_subst [num_feat[num_sets]]]]
mol_type
charge_type
[status_bits
[mol_comment]]
```
The square bracket notation tells us that the inner value is present only when the outer value is provided. For example, `mol_comment` is provided only when `status_bits` is also provided.
Both the following examples are valid for Methane:
```
@<TRIPOS>MOLECULE              @<TRIPOS>MOLECULE
Methane                        Methane
 5 4 0 0 0                      5 4
SMALL                          SMALL
NO_CHARGES                     NO_CHARGES
****
Some comment about Methane
```

### @\<TRIPOS\>ATOM
Each data record associated with this section consists of a single data line. This data line contains all the information necessary to reconstruct one atom contained within the molecule. The atom ID numbers associated with the atoms in the molecule will be assigned sequentially when the .mol2 file is read into a mol2 parser software.

**Format:**
```
atom_id atom_name x y z atom_type [subst_id[subst_name [charge [status_bit]]]]
```
where

- atom_id (integer): The ID number of the atom at the time the file was created. This is provided for reference only and is not used when the .mol2 file is read into any mol2 parser software
- atom_name (string): The name of the atom
- x (real): The x coordinate of the atom
- y (real): The y coordinate of the atom
- z (real): The z coordinate of the atom
- atom_type (string): The SYBYL atom type for the atom
- subst_id (integer): The ID number of the substructure containing the atom
- subst_name (string): The name of the substructure containing the atom
- charge (real): The charge associated with the atom
- status_bit (string): The internal SYBYL status bits associated with the atom. These should never be set by the user. Valid status bits are `DSPMOD`, `TYPECOL`, `CAP`, `BACKBONE`, `DICT`, `ESSENTIAL`, `WATER`, and `DIRECT`

For any atom C, both the following configurations are correct:

```
@<TRIPOS>ATOM
      1 C           1.0817    0.0395   -0.0687 C.1     1  LIG1       0.000 BACKBONE|DICT|DIRECT
```
```
@<TRIPOS>ATOM
      1 C           1.0817    0.0395   -0.0687 C.1
```
In the first example, the atom has ID number `1` and is named `C` with XYZ-coordinates as `(1.0817, 0.0395, -0.0687)`. Its atom type is `C.3`(sp2 hybridization). It belongs to the substructure with ID `1` which is named `LIG1`. The charge associated with the atom is `0.000` and the SYBYL status bits associated with the atom are `BACKBONE`, `DICT`, and `DIRECT`. The second example is the minimal information necessary for the MOL2 command to create an atom.

### @\<TRIPOS\>BOND
Similar to the previous section, each data record associated here consists of a single data line that contains all the information necessary to reconstruct one bond in the molecule.

**Format:**
```
bond_id origin_atom_id target_atom_id bond_type [status_bits]
```
where
- bond_id (integer): The ID number of the bond at the time the file was created. This is provided for reference only and is not used when the .mol2 file is read into any mol2 parser
- origin_atom_id (integer): The ID number of the atom at one end of the bond
- target_atom_id (integer): The ID number of the atom at the other end of the bond
- bond_type (string): The SYBYL bond type. The supported bond types are:
  - 1 = single
  - 2 = double
  - 3 = triple
  - am = amide
  - ar = aromatic
  - du = dummy
  - un = unknown (cannot be determined from the parameter tables)
  - nc = not connected
- status_bits (string): The internal SYBYL status bits associated with the bond. These should never be set by the user. Valid status bit values are `TYPECOL`, `GROUP`, `CAP`, `BACKBONE`, `DICT`, and `INTERRES`

As an example, once again, both the following configurations are correct:
```
@<TRIPOS>BOND
     1     1     2    ar BACKBONE|DICT|INTERRES
```
```
@<TRIPOS>BOND
     1     1     2    ar
```
The bond in the first example has ID number `1` and connects atoms `1` and `2`. It is an `aromatic` bond. The status bits indicate the bond is part of the backbone chain, joins two residues, and that a dictionary was used when creating the molecule. The second example is a minimal representation of the same bond.

### Few important points

- Any line containing only white spaces is considered a blank line and is ignored by the MOL2 command
- A printable ASCII string beginning with a hash or pound sign (`#`) in column 1 is called a comment line. These lines are again ignored by the MOL2 command
- Comments are terminated by the end of the line and may not be continued to the next line
- The string `****` is used to indicate that a non-optional string field is empty

### References and Further Reading
- <a style="overflow-wrap: break-word" target="_blank" href="https://chemyang.ccnu.edu.cn/ccb/server/AIMMS/mol2.pdf">https://chemyang.ccnu.edu.cn/ccb/server/AIMMS/mol2.pdf</a>