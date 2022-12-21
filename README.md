# Kikkert_Pokrajac_ODonoghue_Steenhauer_2013
sedOlaFlow case setup for dam-break driven swash on a permeable slope (details of physical experiment refer to Kikkert et al., 2013, Coastal Engineering, https://doi.org/10.1016/j.coastaleng.2013.04.008). 
Modeling paper is under review in JGR: Oceans.

### How to Simulate ###
1. foamClearPolyMesh
* (2) blockMesh
* (3) snappyHexMesh -overwrite (If you want to skip the mesh refinement near the sediment pit, you can ignore this part)
* (4) extrudeMesh (This is to remove the redundant spanwise grids as an outcome of snappyHex)
* (5) go to 0 folder and make non-org files
*    cp -r alpha.water.org alpha.water
*     cp -r alpha.org alpha
* cp -r gamma.org gamma
* (6) setWaveField (to fill the water, in default waves2Foam searches alpha.water and U)
* (7) copy U to Ub & alpha.water to alpha1 (SedWaveFoam uses alpha1)
* cp -r U Ub
* cp -r alpha.water alpha1
* (8) funkySetFields -time 0 (to fill up the sediment and remove that portion in alpha1)
* (9) SedWaveRANSDEVFoam (you can make the parallel if you want)
