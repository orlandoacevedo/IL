Ionic liquid force field parameters (OPLS-2009IL and OPLS-VSIL)
=================================================

[Orlando Acevedo](http://www.acevedoresearch.com), University of Miami

This repository holds two different sets of OPLS-AA parameters for use in ionic liquid simulations. 

**1) Unscaled and 0.8 scaled OPLS-AA force field parameters (2009IL).**
Please see the following references for technical details:
1. [doi:10.1021/ct900009a](http://pubs.acs.org/doi/abs/10.1021/ct900009a)
2. [doi:10.1021/acs.jctc.7b00520](http://pubs.acs.org/doi/abs/10.1021/acs.jctc.7b00520)

**2) Virtual site OPLS-AA force field parameters (VSIL).**
Please see the following reference for technical details:

3. [doi:10.1021/acs.jpcb.7b11996](http://pubs.acs.org/doi/abs/10.1021/acs.jpcb.7b11996)
4. [doi:10.3390/ijms21041190](https://www.mdpi.com/1422-0067/21/4/1190)
5. [doi:10.1021/acs.jpcb.2c01636](https://doi.org/10.1021/acs.jpcb.2c01636)

**IMPORTANT**: The 2009IL and VSIL parameters should NOT be mixed! VSIL anion parameters were specifically parameterized to work exclusively with the virtual site cations.

Requirements
------------
* [Gromacs 5.0.7](http://www.gromacs.org/Downloads)
    * Tested with CUDA 7.5/8.0 and on CentOS 6.5/7.0
    * Heat capacity DoS calculations (g_dos) requires Gromacs 5.1.4 due to a known bug in version 5.0.7
    
Download
-----
```
git clone git://github.com/orlandoacevedo/IL.git
```

Parameters Available
--------------------
* **Cations**
    * 1-ethyl-3-methylimidazolium [EMIM]
    * 1-butyl-3-methylimidazolium [BMIM]
    * 1-octyl-3-methylimidazolium [OMIM]
* **Anions**
    * acetate [ACE]
    * benzoate [BNZ]
    * bis(pentafluoroethylsulfonyl)amide [NPf2]
    * bis(trifluoromethylsulfonyl)amide [NTf2]
    * bromide [Br]
    * chloride [Cl]
    * dicyanamide [DCA]
    * formate [HCOO]
    * hexafluorophosphate [PF6]
    * methylsulfate [MS]
    * nitrate [NO3]
    * perchlorate [ClO4]
    * propionate [PROP]
    * tetrachloroaluminate [AlCl4]
    * tetrafluoroborate [BF4]
    * thiocyanate [SCN]
    * tricyanomethanide [TCM]
    * trifluoromethanesulfonate [TFO]
    
* **2009IL** - unscaled OPLS-2009IL bonded and nonbonded parameters
  
* **0.8*2009IL** - 0.8-scaled OPLS-2009IL bonded and nonbonded parameters

* **VSIL** - Virtual site OPLS bonded and nonbonded parameters
    * itp, top, and pdb folders

Tutorial
--------
A brief tutorial is provided in the Tutorial_[BMIM][BF4] directory. A README file will guide the user through the contruction of a [BMIM][BF4] box composed of 500 ion pairs using the OPLS-2009IL parameter set. GROMACS input files are provided to run a 40 ns MD simulation and output files are also provided for comparison. The user is guided on how to compute both the density and the heat of vaporization for the ionic liquid system.


References
----------
Sambasivarao, S.V.; Acevedo, O. "Development of OPLS-AA Force Field Parameters for 68 Unique Ionic Liquids." *J. Chem. Theory Comput.*, **2009**, *5*, 1038-1050. [doi:10.1021/ct900009a](http://pubs.acs.org/doi/abs/10.1021/ct900009a)

Doherty, B.; Zhong, X.; Gathiaka, S.; Li, B.; Acevedo, O. "Revisiting OPLS Force Field Parameters for Ionic Liquid Simulations." *J. Chem. Theory Comput.*, **2017**, *13*, 6131-6145. [doi:10.1021/acs.jctc.7b00520](http://pubs.acs.org/doi/abs/10.1021/acs.jctc.7b00520)

Doherty, B.; Zhong, X.; Acevedo, O. "A Virtual Site OPLS Force Field for Imidazolium-Based Ionic Liquids" *J. Phys. Chem. B*, **2018**, *122*, 2962-2974. [doi:10.1021/acs.jpcb.7b11996](http://pubs.acs.org/doi/abs/10.1021/acs.jpcb.7b11996)

Velez, C.; Doherty, B.; Acevedo, O. "Accurate Diels-Alder Energies and Endo Selectivity in Ionic Liquids using the OPLS-VSIL Force Field" *Int. J. Mol. Sci.*, **2020**, *21*, 1190. [doi:10.3390/ijms21041190](https://www.mdpi.com/1422-0067/21/4/1190)

Yue, K.; Doherty, B.; Acevedo, O. "Comparison between Ab Initio Molecular Dynamics and OPLS-Based Force Fields for Ionic Liquid Solvent Organization" *J. Phys. Chem. B*, **2022**, *126*, ASAP. [doi:10.1021/acs.jpcb.2c01636](https://doi.org/10.1021/acs.jpcb.2c01636)

About
-----
**Contributing Authors**: Brian Doherty, Symon Gathiaka, Bin Li, S.V. Sambasivarao, Caroline Velez, Xiang Zhong, and Orlando Acevedo*

**Funding**: Gratitude is expressed to the National Science Foundation (NSF CHE-2102038, NSF CHE-1562205, and NSF CHE-1149604) for funding the project.

**Software License**:
OPLS-2009IL and OPLS-VSIL.
Copyright (C) 2022 Orlando Acevedo

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details. <http://www.gnu.org/licenses/>
