
## LuxR, LuxI Constitutive Protein expression: J23100, B0034 
We tried to model HSL production from our design


Then we modeled the production of LuxR/HSL dimers(the transcription activator of pLux) in our original construct with strong promoters (J23100) for LuxR and LuxI.



However, there were too much dimers(In SkyBlue, over 10^2.5 dimers) that an induced increase in protein production could not be achieved. 



## Construct selection
In the previous model we only modeled the molecules with in the cytoplasm. However, it is necessary to consider the external environment too if we want to model the outcomes at different cell densities. In the updated model, we included a variable for the external HSL concentration. 
First, when there is only one cell in the environment, it would be reasonable to consider the external HSL as 0. Internal HSL concentration would be always higher than external HSL, so no HSL would return back into the cell. In the single cell model, external HSL concentration is fixed to 0. 

Our model was developed upon the model created by UPV Valencia's project in 2018 (1).
The ODEs for the single cell model is as below:
![Model Single Cell](https://user-images.githubusercontent.com/87221166/137178223-a3d765e0-58d2-4e31-88ba-e6ceb87d8b5a.png)
The code is as below:
[Single cell.zip](https://github.com/KUAS-Korea/KUAS-2021-igem/files/7350394/Single.cell.zip)
The results showed that among the products 


### High density culture: closed 1nL env, cells 1(dark color) ~ 1e5(bright color) 

When cells are in high density, it would be fairly reasonable to imagine a region homogenous in HSL concentration. So in the high density model, we considered a nL of closed volume. When cells produce HSL, it will start to accumulate. We plotted graphs with different number of cells in the volume with different combinations of promoters and RBS. Among the different constructs, the only construct with promising modeling results was the construct with J23106 B0032 which showed around 10^1.5 dimers in at 1cell/nL and 10^2.7 dimers at 10^5cells/nL.

![image](https://user-images.githubusercontent.com/87188354/135296285-d6b808c3-11e8-4cff-aed6-674428672736.png)
Dimers >1e 2.5
![image](https://user-images.githubusercontent.com/87188354/135296306-2c1edd0a-9f53-4468-bbee-e1bfce6c6a0d.png)


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
