[![CC BY 4.0][cc-by-shield]][cc-by]

# On The Free Energy Penalty of Cavity Formation In Salt Solutions: Rethinking the Terms “Kosmotropic” and “Chaotropic”. 

## Research plan
See `PROJECT_DESCRIPTION.md` for a more detailed account on the background behind the research project.
### Computations and analysis
1. [ ] Conduct MD simulations of pure water using the OPC model (will serve as our reference state for ermod later)
2. [ ] Conduct MD simulations of salt solutions (≤ 1 M) (will serve as our reference state for ermod later)
3. [ ] Analyze the simulations of the salt solutions and pure water in terms of radial distribution function (RDF) between the ions-water and water-water and establish the "local domain" in which water is perturbed by the ions.
4. [ ] Conduct MD simulations of a hydrophobic solute (start with an LJ sphere) with varying sizes (sigma) ranging from below and above the "local domain cutoff" previously established. In case of LJ sphere keep epsilon fixed. The simulations should be conducted in both pure water and salt solutions.
5. [ ] Determine the solvation free energy of the hydrophobic solute in water and salt solutions using ERMOD.
6. [ ] Illustrate how the difference in solvation free energy of the hydrophobic solute between water and salt solutions is varying with solute size. 

### Hardware and software
Since we are conducting molecular dynamics (MD) simulations, we benefit substantially from GPU acceleration. Because the majority of the group is conducting MD simulations with parallel computing on CPUs, the GPUs on our local machines are mainly idling thus leaving the possibility to use 5-7 GPUs. These can be found on nu-g01, nu-g02, kappa-g01, and possibly iris01.

Regarding software, Stefan is predominantly working with OpenMM due to the flexibility in creating custom forces, testing of new MD algorithms, and so on. However, this project can with ease be conducted using the GROMACS software package. For trajectory analysis and visualization of data Stefan highly recommends the usage of Python and Jupyter notebooks. This mainly serves the purpose of having easy transparency of the simulations and analysis conducted, but more important it also serves the purpose of improving your programming skills!

For the storage of data such as inputs, topology files, and other files which are not super large in size (such as trajectory files) I recommend we use Github. This allows easy collaboration between you and Stefan. For an introduction to Git and Github Stefan is more than happy to help.

### Details regarding molecular dynamics
When conducting molecular dynamics there are a ton of factors one can choose with examples including choice of force field, ensemble, barostat, thermostat, system, etc. My personal opinion is that one must conduct molecular dynamics with the goal to _attempt_ to choose the optimal conditions for the purpose of the simulations. Consequently you are free to choose whichever parameters you think are well suited for the study. Below I will give my recommendations, however I encourage you to choose differently if you believe it is better.

#### Stefan's MD recommendation:
**Ensemble**: Isothermal-Isobaric (NPT) ensemble.  
**Thermostat**: [Langevin dynamics](https://manual.gromacs.org/current/reference-manual/algorithms/stochastic-dynamics.html).  
**Barostat**: [Parrinello-Rahman barostat](http://www.sklogwiki.org/SklogWiki/index.php/Parrinello-Rahman_barostat).  
**System size**: ~7.500 - 10.000 water (Adjust number of ions according to approximately desired concentration).  
**Integrator**: 2 fs time step, constraints on water and all bonds involving hydrogen.  
**Length of simulation**: Preliminary run for pure water (10 ns), salt + water (100 ns). Run longer if the primary observables (slvfe, rdfs, etc.)  are not converged.  
**Force fields**: Water - [OPC](https://doi.org/10.1021/jz501780a), Ions: [Li & Merz parameters](10.1021/ct400146w).  
**Electrostatic interactions**: PME (6th order B-spline with an Ewald tolerance 1e-5).  
**Lennard Jones interactions**: Usage of shifting functions, or you may follow the ermod tutorial.  
**Hydrophobic solute**: Hydrocarbons (methane to n-hexane). 
**Analysis**: Solvation Free Energy, Average Pair Energy, Energy-domain decomposition (see PCCP 2022), RDF (solute-water, solute-ions, water-ions)

### License
This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg
