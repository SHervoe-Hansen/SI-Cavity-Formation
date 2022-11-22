# Analytical Theory For The Solvation of Solute in Salt Solutions

## Definition of the Solvation Free Energy, the Solute, and the Solvent
We define the solvation Gibbs free energy as the free energy associated with turning on the interactions between the solute and solvent:
$$\Delta G_{\mathrm{sol}} = - k_{\mathrm{B}}T \ln\left( \frac{\int_{V} \int_{\Gamma_{\boldsymbol{q}}} e^{-\beta\left(U_t(\bar{q})+U_{o}(\boldsymbol{q})+U_{t,o}(\boldsymbol{\bar{q}},\boldsymbol{q})+PV\right)}\ \mathrm{d}\boldsymbol{\bar{q}}\ \mathrm{d}\boldsymbol{q} \ \mathrm{d}V}{\int_{V} \int_{\Gamma_{\boldsymbol{q}}} e^{-\beta\left(U_t(\bar{q})+U_{o}(\boldsymbol{q})+PV\right)}\ \mathrm{d} \boldsymbol{\bar{q}}\ \mathrm{d}\boldsymbol{q} \ \mathrm{d}V} \right).$$
Molecules can essentially be arbitrary classified as either *solute* or *solvent*.
From an experimental perspective the words *solute* or *solvent* are usually associated with the property of amount.
In specific we usually the most predominant species (highest molarity) as the solvent and the remaining low molarity species as the solutes.
However, from the perspective of free-energy calculations and in specific solvation free-energy calculations a more appropiate definition is for the solute to be defined as the molecular specie(s) undergoing alchemical transfomration, i.e. $\lambda$-dependent, and the solvent to remain constant, i.e. $\lambda$-independent.

## Definition of the Difference in Solvation Free Energy in Salt Solutions
We define the difference in solvation free energy in salt solutions, $\Delta \Delta G_{\mathrm{sol}}$, as:
$$\Delta \Delta G_{\mathrm{sol}} =  \Delta G_{\mathrm{sol}}(c) - \Delta G_{\mathrm{sol}}(c=0).$$
Here $\Delta G_{\mathrm{sol}}(c)$ is the solvation free energy in a aqueous solution of salt concentration $c$ and $\Delta G_{\mathrm{sol}}(c=0)$ is the solvation free energy in pure water.
This definition allows us to subtract the effect of bulk water and focus on the effect of salt.
The salt can influence the system by two means:
One option is the binding of the salt to the solute directly in which case the salt can provide increased solvation by acting as a bridge between the solute and water.
The second option is for salt to alter the properties of water to either favour or disfavour the interactions between the solute and the water.

## The Energy-Domains of the Solvation Free Energy & and the Solvation Process
*To be written*

## Statistical Mechanical Modelling of the Excluded Volume Component
For the modelling of the excluded volume component of the solvation process consider a box of volume $V$ filled with water and containing $N$ spherical co-solvent species.
Each of the $N$ co-solvent species occupies space by Born repulsion and alters the properties of water compared to bulk water by some distance $r$ from the co-solvent species.
The volume allocated by the co-solvent species and associated water layer around the co-solvent species we shall donate the *co-solvent local domain*.
For a solvation process the solute is attempted to be inserted with uniform probability across the whole box.
The probability that the solute is inserted into a co-solvent local domain is given by:
$$P_{\mathrm{CLD}} = \frac{N*V_{\mathrm{CLD}}}{V} = \frac{N * \frac{4}{3}\pi ( \sigma +r)^3}{V}$$ 
