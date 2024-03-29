---
title: Lennard-Jones potential
date: 2021-05-15T10:03
---

The **Lennard-Jones potential** is a model of the interatomic potential between two neutral atoms or molecules. 

$$ U(r) = 4\epsilon \left(\left(\frac{\sigma}{r}\right)^{12} - \left(\frac{\sigma}{r}\right)^6\right) ,$$

where $\epsilon$ is a *characteristic energy*, which is specific for the atoms we are modeling. $\sigma$ is a *characteristic length*.[^chem-libretexts]

The contributions come from the two main interactions:

- **[[Van der Waals interaction]]**: There is an attractive force between the atoms, with a potential proportional to $1/r^6$ ($r$ being the distance between them). 
- **[[Pauli repulsion]]**: Due to the possibility of overlapping orbitals, there are "quantum mechanical effects" (yup, that's way too diffuse) which cause repulsion between the atoms. This is modelled with a power law of the form $1/r^n$. A good approximation is $n = 12$.

[^chem-libretexts]: *Lennard-Jones Potential*. (2013, October 2). Chemistry LibreTexts. <https://chem.libretexts.org/Bookshelves/Physical_and_Theoretical_Chemistry_Textbook_Maps/Supplemental_Modules_(Physical_and_Theoretical_Chemistry)/Physical_Properties_of_Matter/Atomic_and_Molecular_Properties/Intermolecular_Forces/Specific_Interactions/Lennard-Jones_Potential>
