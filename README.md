
# computationalchemistry

The work (training material) carried out on a set of first-principles quantum mechanical and molecular dynamics programs is summarised in the form of HPC submission scripts, as well as of tables describing the actual progress with the packages, and of the full input/output file set for specific calculations. Therefore, the main point of this repository is:

1. Slurm job submission scripts for calculations with the various software packages have been uploaded.
1. Tables depicting the progress achieved with the various computational chemistry programs are regularly updated
   - The first few uploaded tables were enclosed as a single document.
   - At some point, I decided to extend their size, and ended up uploading separate documents for each table.
1. Compressed tar files containing the complete set of input and output files for a calculation are continously added.

The sets of input/output tar files for specific calculations include the following:

 - **Sequential** ABINIT calculation of the as provided example "tbasepar_1", located within abinit-test/tutorial ("Lead crystal - parallelism over k-points"): 
   *sequentialABINITtbasepar_1.tar.gz* (Genius)
 - **Sequential** ABINIT calculation of the as provided example "tbasepar_2", located within abinit-test/tutorial ("FCC 4-atom A1-phonon deformed ferromagnetic Fe 
   crystal" - parallelism over spin): *sequentialABINITtbasepar_2.tar.gz* (Genius)
 - **MPI** ABINIT calculation of the as provided example "tdfpt", located within abinit-test/tutoparal ("DFPT phonon calculation for Aluminium crystal - step 1: 
   ground-state electronic structure calcuation - step 2: phonon calculation": *mpiABINITtdfpt1and2.tar.gz* (DSI laptop guest2; no batch job script used)
 - **Sequential** ASE convex hull determination of a CuxPt1-x(111) surface slab by means of a genetic algorithm calculation (global optimization): 
   *sequentialASEgenalgCuPt111slab.tar.gz* (Genius)
 - **MPI** ASE water-box equilibration as a strong-scaling **MPI** test: *mpiASE_STRONGSCALING_waterboxequi.tar.gz* (Genius)
 - **MPI** LAMMPS calculation of c-HfO2: *mpiLAMMPScHfO2.tar.gz* (Genius)
 - **OpenMP** (strong-scaling) and **KOKKOS-hybrid** LAMMPS ethanol-box equlibration: *openmpLAMMPSstrongscalingETHANOLBOX.tar.gz* and  
   KOKKOSPARALLhybrid36and2ethanol.tar.gz (Genius)
 - **Sequential** LAMMPS Monte-Carlo relaxation of a two-dimensional deformed hexagonal lattice: *sequentialLAMMPSmc.tar.gz* (Genius)
 - **MPI** LAMMPS calculation of quartz amorphisation via melting/quenching temperature ramps, as an **MPI** strong-scaling case: *mpiLAMMPSstrongscalsilicaamorph.tar.gz* (Genius)
 - **Sequential**, **MPI**, **OpenMP** and **hybrid** LAMMPS NVT calculation for a Lennard-Jones fluid: *sequentialLAMMPSlj.tar.gz*, *mpiLAMMPSlj.tar.gz*, 
   *openmpLAMMPSlj.tar.gz* and *hybridLAMMPSlj.tar.gz* (Genius),
 - **Sequential** QE (PWscf) GaAs calculation under PAW: *sequentialQEgaas.tar.gz* (Genius),
 - **MPI** QE (PWscf) SiH4 -molecule in a box- calculation under Hamann's ONCV pseudopotentials: *mpiQEsih4.tar.gz* (Genius),
 - **MPI** QE (PWscf) *Immm* Ag2PdO2 calculation under ultrasoft pseudopotentials: *mpiQE_Ag2PdO2.tar.gz* (Genius),
 - **MPI** QE (PWscf) calculation of 112 atom-cell model of unreconstructed Au(110), from the PRACE benchmark (UEABS): *mpiQEgoldsurface.tar.gz* (Genius)
 - **MPI** QE (PWscf) calculation of 443-atom cell model of a graphene monolayer suspended on Ir(111) under PAW, from the PRACE benchmark: *mpiQEiridiumcarbide.tar.gz* (Genius)
 - **MPI** GPAW (LCAO) calculation (weak scaling analysis) of Ag (FCC) nanoparticles of increasing size with both octahedral and cuboctahedral shape: *count.tar.gz* and *nanoparticlessilver.tar.gz* (Genius)
 
Eventually, the software list as exhibited in the reported tables will extend by including to-be-installed ab-initio/MD packages and pre- and post- processing tools. On the one hand, simple packages that read the input structures in well known formats (CIF - pdb - xyz - POSCAR) and produce outputs that become input files of the correct format for the specific programs, are envisioned (cif2cell). On the other, packages that generate supercells as well as defects of different dimensionality are being considered: point defects, dislocations, grain boundaries and surfaces (ASE). Moreover, atomistic geometries crucial for the current materials science ecosystem require more involved input geometry processing: disordered/amorphous solids and glasses, solid solutions, simultaneous multi-phase models, polycrystalline models, bubble nucleation models. The *atomic simulation environment* is a good example of such tools, as well as its big-data driven high-troughput computational materials science sister package (the *atomic simulation recipes* (ASR)). Other HTCMS packages (aiida - materials cloud; materials genome - pymatgen, JARVIS, AFLOW; pyiron) - are being looked into. At this stage, we are certainly not talking about simple tools, HTCMS corresponding to a full infrastructure including a large collection of tools for data mining, AI (ML potentials), pre- and post-processing, databases of materials, HPC and online high-througput ab-initio/MD/kinetics calculations. Given the complexity of the various scientific directions to be followed (HTCMS is probably the best example), it is my opinion that at some point, it becomes unavoidable keeping in touch with academics working in the respective fields, if you intend to keep doing sound training material development work. The way I see it, this work would benefit from contact with people working in the fields:

1. Theoretical Materials Science
1. Big-Data driven High-Throughput Computational Materials Science
1. Computational Statistical Mechanics

HPC for computational chemistry (physics) is not justified unless large-scale problems are considered and actually solved. Key to the HPC user in this field is seeing what software developers never show: The large-scale case alongside the new specific problems you are to face. Unless sufficiently challenging training material is presented to the user, he/she will not buy the story. In that sense, the webpage https://www.nsc.liu.se/~pla/blog/2014/01/30/vasp9k/ represents what I consider a model for VASP HPC training material (Peter Larsson, PhD - Computational Scientist - National Supercomputer Centre at Linköping University). They seem to be doing that for a huge collection of software packages within both first-principles quantum-mechanical calculations and molecular dynamics. On the other hand, the ENCCS (National Competence Centre Sweden) consortium organises fully-fledged HPC computational materials workshops as free training events, in collaboration with the MAX Centre of Excellence ("Efficient materials modelling on HPC with QUANTUM ESPRESSO, Yambo and BigDFT", November 14-17 2022; https://enccs.se/events/2022-11-efficient-materials-modelling/), another example of training activities for the National Competence Centre Belgium.

There is one aspect of this work that requires further clarification, ie the computational statistical mechanics direction. On the one hand, it seems obvious that molecular dynamics is a tool for computational statistical mechanics, and that in combination with rare event sampling and/or Markov-Chain Monte-Carlo provides some of the most advanced kinetic simulation methods currently available. On the other, atomistic geometry file creation, in many ocassions, goes through computational statistical mechanics methodology: From straight Monte-Carlo optimisations to "cluster expansion" (ATAT) special quasirandom structure algorithms.
It is my opinion that much of the statistical mechanics software has not gone into the HPC stage (even the computational stage!), and therefore, part of our training material development work could consist in identifying specific cases, certainly in collaboration with academics working in the computational field.

A range of personal scientific interests lies behind this description. In case we decide to get started on running calculations with the different software packages other than the examples the various distributions provide, this non-exhaustive list should serve as a starting point:

 - *Hydrated proteins*:
   Protein solvation seems to be a very productive field, including both implicit and explicit water molecule models. It seems that PDB files 
   of proteins in water do not contain the explicit solvent molecules. On the other hand, there exist critical details regarding the chemical terminations 
   of protein groups, including zwitterionic states, acidic H states and H-bonds, that need to 
   be addressed correctly. Moreover, it is key to note that H atoms in proteins cannot be assumed to be present in PDB files [^1], since this 
   happens only in some cases. The off-the-shelf PDB protein file always needs to be modified before running MD/ab-initio calculations with the 
   water molecules explicitly included:

    1. The Hydrogen addition process could follow the procedure in [^2] (EMBL - Heidelberg)
    1. The water addition process, chemical termination rearrangement and box build-up for calculation would follow the procedure described in 
       the pAPRika website [^3]. This software is based on both GROMACS and PLUMED programs (part of our set of installed programms) for free 
       energy calculations.

 - *Solvated molecules as models for the study of hydrated proteins*:
   Water solutions of peptidic molecules and oligomers are key systems in order to understand the mechanics of calculations for proteins. In fact, hydrated 
   **alanine dipeptide** has been denominated (PG Bolhuis) "The Hydrogen atom of molecular simulation".

 - *MD calculations of AuCd solid solution models*:
   The starting point would be the generation of atomistic geometries for those models (the picture below illustrates the concept of chemical 
   ordering, which underpins solid solutions and the randomness operating behind them), including:

   1. ATAT cluster expansion or special quasirandom structure [^4] calculations,
   2. The solid solution geometry builder within the HTCMS software PYIRON

   A Statistical Field Theory for Non-Affine Lattice Deformations (see Alessio Zaccone and Matteo Baggioli) is currently being developed. 
   Phenomena like rubber (entropic) non-linear elasticity, soft matter dynamics or the glass transition are being investigated under that 
   theory, which is expected to explain properties like anomalous phonon softening or Peierls deformation. 

![](chemicalordering.gif)

- *Dynamics of the interface solid surface - liquid water*:
Following the ASE tutorial material, generating atomistic geometries for water interfaces seems trivial, which will allow to get started in computing the dynamics of solved/adsorbed proteins. No work on the influence of a metal surface seems to have been located in the literature.

NOTE: The intern is considering the possibility of adding a regularly updated entry to this document for databases in tabular form, including structural aspects, property-wise listings, etc. For the time being the following database for ions in solution (many ions/many solvents) on the basis of first-principles molecular dynamics data, seems worth mentioning:

[](https://ionsolvr.newcastle.edu.au/solutes.html#Database)

For computational testing purposes in molecular modelling, the valuable structural aspect of this database is obvious. 

TO DO LIST: Since the intern has lagged behind regarding weekly report uploading, the following list of software for HPC calculations is required:

 - Alphafold;
 - GROMACS and PLUMED;
 - The OpenKim set of force-fields for BCC metals (W) under ASE;
 - Interfaces with liquid water (TIP potentials) of both FCC and BCC metals;
 -  `atomsk` and `DIST-tools` atomistic model building for extended defects in materials science (metals) as well as ASE, LAMMPS and GPAW calculations;
 - The comprehensive GPAW test suite (only a simple as-provided test has been run so far);
 - PRACE (UEABS) benchmarks for GPAW;
 - Following the GPAW weak scaling study on Ag nanoparticles, and in order to contribute further to the discussion on GPAW optimisation, the intern is considering the installation of a code not mentioned so far: Either SIESTA or ONETEP. Both are linear-scaling codes which overcome the $N^3$ dependence of first-principles quantum mechanical density-functional theory calculations. Both have really attractive computational features, the only practical difference being at this point that while SIESTA is open-source, ONETEP requires a licence application (although it is for free). Their comparison with the GPAW output would be in order. Conda installations have been discarded for these purposes, since performance would not be a reliable measure; for the same token, HPC calculations with the the CASINO code for quantum Monte-Carlo (QMC) would offer the chance of completing a nice comparative study, considering it is known to exhibit $N^7$ scaling, although QMC is a completely different electronic structure theory to DFT;
 - WULFFPACK, and
 - SSCHA

[^1]: https://www.umass.edu/microbio/chime/beta/x1.07/protexpl/help_hyd.htm
[^2]: http://swift.embl-heidelberg.de/servers2/
[^3]: https://github.com/GilsonLabUCSD/pAPRika/blob/master/docs/index.rst
[^4]: https://nanohub.org/tools/sqsatat/
