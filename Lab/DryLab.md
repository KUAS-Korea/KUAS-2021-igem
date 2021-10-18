

## Construct selection
Our initial design of the kill switch comprised of the J23100 promoters and B0034 RBS constitutively expressing both LuxI and LuxR. However, we were not sure if or design would achieve the proper induction at high densities. So, we created ODE models to evaluate the performance of constructs containing different combinations of promoters and RBSs. We created a single cell model to account for cells that have fallen off of the colony and a high density model for cells with in a colony. Constructs with low HSL/LuxR dimers in the single cell model and high HSL/LuxR dimers in the high density model would be chosen as our improved design.
First, when a single cell remains free in the environment, it would be reasonable to consider the external HSL as 0. Internal HSL concentration would be always higher than external HSL, so no HSL would return back into the cell. Thus, in this single cell model, external HSL concentration is fixed to 0. 

Our model was developed upon the model created by UPV Valencia's project in 2018 (1).
The ODEs for the single cell model is as below:
![Model Single Cell](https://user-images.githubusercontent.com/87221166/137178223-a3d765e0-58d2-4e31-88ba-e6ceb87d8b5a.png)
The code is as below:
[Single cell.zip](https://github.com/KUAS-Korea/KUAS-2021-igem/files/7350394/Single.cell.zip)
The results are in the word file below.
[Results_Single cell.docx](https://github.com/KUAS-Korea/KUAS-2021-igem/files/7363930/Results_Single.cell.docx)


### High density culture: closed 1nL env, cells 1(dark color) ~ 1e5(bright color) 

When cells are in high density, it would be fairly reasonable to imagine a region homogenous in HSL concentration. So in the high density model, we considered a nL of closed volume. When cells produce HSL, it will start to accumulate. We plotted 5 graphs, each corresponding to 1 ~ 10^5 cells/nL, for each constructs. 
[HIghDensity.zip](https://github.com/KUAS-Korea/KUAS-2021-igem/files/7363816/HIghDensity.zip)

The results are in the word file below. 
[Results_ High Density.docx](https://github.com/KUAS-Korea/KUAS-2021-igem/files/7363951/Results_.High.Density.docx)

Among the different constructs, the only construct with promising modeling results was the construct with J23106 B0032 which showed around 10^1.5 dimers in at 1cell/nL and 10^2.7 dimers at 10^5cells/nL.

![image](https://user-images.githubusercontent.com/87188354/137712108-7675f544-5c59-49ba-bd36-64320905e597.png)
The graph above shows the internal(int) and external(ext) HSL in molecules
![image](https://user-images.githubusercontent.com/87188354/137711927-4eaa58a1-a28f-4216-9543-e7875d67a774.png)


## cI at different HSL/LuxR concentrations
    
    p.Kd = MolesToMolecules(200*10^(-9)); % dissociation constant of (LuxR·AI)2 to the lux promoter 200[nM] fitted https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3614889/
    alpha = p.k2 * p.k1 * p.CN / p.d1; % Maximal Expression rate [molecules/min]   
    % Rest of the parameters are same as above
    Protein  = alpha ./p.d2 .* (TF.^2 ./ (p.Kd +TF.^2))
![image](https://user-images.githubusercontent.com/87188354/134773893-b7194059-6af8-4751-ba8a-9c0f2fc21aeb.png)




Model High Density

![image](https://user-images.githubusercontent.com/87221166/137178718-45debb01-9621-4b02-b3ae-28088e90de0c.png)


References

1. http://2018.igem.org/Team:Valencia_UPV/Model
