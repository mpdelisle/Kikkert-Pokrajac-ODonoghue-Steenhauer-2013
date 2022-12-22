# Kikkert_Pokrajac_ODonoghue_Steenhauer_2013
sedOlaFlow case setup for dam-break driven swash on a permeable slope (details of physical experiment refer to Kikkert et al., 2013, Coastal Engineering, https://doi.org/10.1016/j.coastaleng.2013.04.008). 
Modeling paper is under review in JGR: Oceans.

### How to Simulate ###
1. foamCleanPolyMesh  
2. blockMesh  
3. snappyHexMesh -overwrite  
4. go to 0 folder and make non-org files  
 cp -r alpha.water.org alpha.water    
5. setFields  
6. SedGWOlaFlow_v1 (can be run in parallel)
