Ionic liquid force field parameters (OPLS-2009IL)
=================================================

[Orlando Acevedo](http://www.acevedoresearch.com), University of Miami

**OPLS-AA force field parameters for ionic liquid simulations.**

Please reference the following papers:

1. [doi:10.1021/ct900009a](http://pubs.acs.org/doi/abs/10.1021/ct900009a)
2. [doi:10.1021/acs.jctc.7b00520](http://pubs.acs.org/doi/abs/10.1021/acs.jctc.7b00520)

Requirements
------------
* [Gromacs 5.0.7](http://www.gromacs.org/Downloads)
    * Tested with CUDA 7.5/8.0 and on CentOS 6.5/7.0
    
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
    * itp, top, and pdb folders

Tutorial
--------
Example on setting up an ionic liquid MD simulation is coming soon...


References
----------
Sambasivarao, S.V.; Acevedo, O. "Development of OPLS-AA Force Field Parameters for 68 Unique Ionic Liquids." *J. Chem. Theory Comput.*, **2009**, *5*, 1038-1050. [doi:10.1021/ct900009a](http://pubs.acs.org/doi/abs/10.1021/ct900009a)

Doherty, B.; Zhong, X.; Gathiaka, S.; Li, B.; Acevedo, O. "Revisiting OPLS Force Field Parameters for Ionic Liquid Simulations." *J. Chem. Theory Comput.*, **2017** *13*, 6131-6145. [doi:10.1021/acs.jctc.7b00520](http://pubs.acs.org/doi/abs/10.1021/acs.jctc.7b00520)

About
-----
**Contributing Authors**: Brian Doherty, Symon Gathiaka, Bin Li, S.V. Sambasivarao, Xiang Zhong, and Orlando Acevedo*

**Funding**: Gratitude is expressed to the National Science Foundation (NSF CHE-1562205 and NSF CHE-1149604) for funding the project.

**Software License**:
OPLS-2009IL.
Copyright (C) 2017  Orlando Acevedo

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details. <http://www.gnu.org/licenses/>
