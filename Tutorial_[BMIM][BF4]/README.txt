GROMACS Tutorial For Simulating Ionic Liquids

*****************************************************************************************************************************
I. Introduction

In this tutorial, the reader will learn how to run a molecular dynamics simulation on the [BMIM][BF4] ionic liquid system using the GROMACS software package. Provided with this tutorial are GROMACS input files, a pre-equilibrated box of [BMIM][BF4] that was constructed using the packmol software (http://www.ime.unicamp.br/~martinez/packmol/home.shtml), and output files to compare results. All simulations in this tutorial were run using GROMACS 5.0.7, which is highly recommended. 

*****************************************************************************************************************************
II. Setting up parameters in GROMACS

Since the parameters implemented in the simulation are not available in the force fields built into GROMACS, .itp files are necessary. The .itp files contain the nonbonded and bonded parameters for both the [BMIM] cation and [BF4] anion. It is also important to note the units for each parameter, as it is necessary to convert the traditional OPLS-AA units to GROMACS. The conversions are listed as followed.

Non-Bonded:
1)	Lennard-jones values are converted from Å to nm and kcal/mol to kJ/mol.

Bonded:
1)	Equilibrium bond distances are converted from Å to nm.
2)	Bond force constants are converted from kcal/mol Å^2 to kJ/mol nm^2. For this case multiply the force constants by 4.184*2*100.
3)	Angle force constants are converted from kcal/mol rad^2 to kJ/mol rad^2. For this case multiply the force constants by 4.184*2.
4)	Fourier coefficients are converted from kcal/mol to kJ/mol.

These conversions have already been made in the .itp files included with this tutorial and in the github repository. In order to call the .itp files for the simulation, GROMACS uses .top files. As you will see in the .top file, each of the .itp files are being sourced for both [BMIM] and [BF4]. Additionally, the .top file is where combination rules and fudge factors are stated, as well as the name of the system and how many of each individual molecule there are in the box. 

With the molecular parameters set up, the run parameters need to be selected for the simulations. This is done through the use of .mdp files. Using the .mdp file provided, a production run using a NPT ensemble will be executed for 40ns. If different run inputs are desired, the reader is referenced to the GROMACS user manual (ftp://ftp.gromacs.org/pub/manual/manual-5.0.7.pdf). 
*****************************************************************************************************************************
III. Running A GROMACS Simulation

The main integration engine of GROMACS is a tool called ‘mdrun’, which requires a pre-processed run input file with the extension .tpr. This file contains the system’s coordinates, topology, and run parameters. Therefore the following files are needed:

.gro - coordinate file for the system of interest 
.top - topology file that contains molecule/ion parameters
.cpt - checkpoint file from a previous molecular dynamics run
.mdp - file that contains the run parameters for the simulation

To create the .tpr file use the command:

grompp –f grompp_prod.mdp –c input.gro –p input.top  -t input.cpt –o output.tpr

Make sure there are no errors in the output. If everything is correct the .tpr can now be used.

To submit the molecular dynamics job, use the following command:

mdrun –deffnm output.tpr –v

the flag –deffnm will set default names for all of the output files and –v will include more output information in the .log file. As the simulation is running you can track it by looking into the .log file to see how many steps have been performed. Once the simulation is finished the following output files should be available:

-	Output.edr
-	Output.cpt
-	Output.xtc
-	Output.trr
-	Output.log

*****************************************************************************************************************************
IV. Post Trajectory Analysis

There are many properties that can be calculated once a production run is completed in GROMACS. In this tutorial the density and heat of vaporization will be determined for the [BMIM[BF4] system. 

#######
Density
#######

To determine the density of the system, the ‘g_energy’ tool can be used. To use g_energy type the following command:

g_energy –f output.edr > density.log

A menu will pop up where density can then be selected for GROMACS to analyze. In the density.log file, the average density, error estimation, RMSD, and total drift of the trajectory will be provided. 

####################
Heat of Vaporization
####################

The heat of vaporization can be calculated using the following equation:

Hvap= E(gas)-E(liq)+RT

E(gas) is the potential energy of a single ion pair in the gas phase, E(liq) is the potential energy of the bulk liquid phase, R is the gas constant, and T is the temperature. E(liq) can be taken directly from the production run using g_energy and selecting the potential option. The potential energy should be for an ion pair, so the E(liq) obtained from g_energy is divided by 500. E(gas) requires an additional simulation that involves a single ion pair of [BMIM][BF4]. The box is provided in this tutorial, labeled bmim_bf4_hvap.gro. Additionally, a new .mdp file is needed where periodic boundary conditions are turned off. This is labeled grommp_hvap_10ns.mdp. Lastly, in the .top file the user will have to change the number of molecules from 500 to 1 for both [BMIM] and [BF4]. With these inputs the user can then build the .tpr file using the following command:

grommp –f grommp_hvap_10ns.mdp –c bmim_bf4_hvap.gro –p bmim_bf4.top –o output.tpr

Using ‘mdrun’, a 10ns trajectory will be run and upon completion the user can utilize ‘g_energy’ to obtain  by selecting the potential option. The heat of vaporization can then be calculated using the equation above. 

