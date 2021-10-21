## Light induction Violacein modeling
Our model was developed upon the model created by IISER-Pune-India's project in 2019 (1)

The ODEs for light induction violacein model is as below:

![ODEs of light](https://user-images.githubusercontent.com/87221166/138295088-8f279b11-c678-4839-b11c-b3ed884818d7.png)

### No Blue light

![I가0_YF1](https://user-images.githubusercontent.com/87221166/138298490-0c634bfc-217f-4818-83a6-0bbe3612afe1.png)

![I가0_FixJ](https://user-images.githubusercontent.com/87221166/138298547-1b7ed1e7-7b4d-4f12-9a5a-172f17b30b24.png)

![I가0_vio](https://user-images.githubusercontent.com/87221166/138298606-84f3119c-fdc2-41c8-8eb2-f594f7962968.png)


Refences
1. https://2019.igem.org/Team:IISER-Pune-India/Model/Mutator-plasmid

## IPTG induction Violacein modeling






## Kill switch construct
![image](https://user-images.githubusercontent.com/87188354/137716967-9e626c2c-8519-4f5e-9fc7-e5e306688dd5.png)
Above is a diagram of our quorum sensing Kill switch. The system is intended to produce the toxin MazF when a cell detaches from the colony and does not recieve enough LuxR/HSL dimers. 

## cI at different HSL/LuxR concentrations

In order to know understand the amount of protein(cI repressor) produced by the lux promoter at each transcription factor (HSL/LuxR dimers) levels, we used the Hill equation to plot the graph. For more information about the derivation of the Hill function, see Contributions. 

The Matlab code is as below 
[TF_vs_cI.zip](https://github.com/KUAS-Korea/KUAS-2021-igem/files/7364177/TF_vs_cI.zip)

The results is as below
![image](https://user-images.githubusercontent.com/87188354/134773893-b7194059-6af8-4751-ba8a-9c0f2fc21aeb.png)

The graph tells us that transcription factors(HSL/LuxR) should be in the range of 10~10^4 molecules and that half the maximum induction is achieved around 100 molecules. 

## Construct selection
Our initial design of the kill switch comprised of the J23100 promoters and B0034 RBS constitutively expressing both LuxI and LuxR. However, we were not sure if or design would achieve the proper induction at high densities. So, we created ODE models to evaluate the performance of constructs containing different combinations of promoters and RBSs. We created a single cell model to account for cells that have fallen off of the colony and a high density model for cells with in a colony. Constructs with low HSL/LuxR dimers in the single cell model and high HSL/LuxR dimers in the high density model would be chosen as our improved design.
First, when a single cell remains free in the environment, it would be reasonable to consider the external HSL as 0. Internal HSL concentration would be always higher than external HSL, so no HSL would return back into the cell. Thus, in this single cell model, external HSL concentration is fixed to 0. 

Our model was developed upon the model created by UPV Valencia's project in 2018 (1).
The ODEs for the single cell model is as below:
![Model Single Cell](https://user-images.githubusercontent.com/87221166/137178223-a3d765e0-58d2-4e31-88ba-e6ceb87d8b5a.png)
The code is as below:
[Single cell.zip](https://github.com/KUAS-Korea/KUAS-2021-igem/files/7350394/Single.cell.zip)
The results are in the word file below. In the file, the constructs are indicated in the form of R10034_I10632 which means luxR has J23100 as a promoter and B0034 as a RBS, while luxI has J23106 as a promoter and B0032 as a RBS. 

[Results_Single cell.docx](https://github.com/KUAS-Korea/KUAS-2021-igem/files/7363930/Results_Single.cell.docx)

The only constructs that had dimers below 10^2 was R10632_I10032 and R10632_I10632. 
![image](https://user-images.githubusercontent.com/87188354/137714734-7c294f5a-4d30-4603-b95a-e6322bd6dee6.png)
HSL/LuxR dimers(dimer) and internal HSL(int) levels for the construct R10632_I10032
![image](https://user-images.githubusercontent.com/87188354/137714747-3653e22b-664e-4506-903c-7b8b2dd7e9dd.png)
HSL/LuxR dimers(dimer) and internal HSL(int) levels for the construct R10632_I10632

### High density culture: closed 1nL env, cells 1(dark color) ~ 1e5(bright color) 

When cells are in high density, it would be fairly reasonable to imagine a region homogenous in HSL concentration. So in the high density model, we considered a nL of closed volume. When cells produce HSL, it will start to accumulate and at some point, HSL will flow back into the cell. The ODEs used in the model is as below. 

Model High Density

![image](https://user-images.githubusercontent.com/87221166/137867635-cec91503-6caa-4b0a-8a0f-9d9e480730fd.png)


Using the ODEs above, we plotted 5 graphs, each corresponding to 1 ~ 10^5 cells/nL, for each constructs. 
[HIghDensity.zip](https://github.com/KUAS-Korea/KUAS-2021-igem/files/7363816/HIghDensity.zip)

The results are in the word file below. 
[Results_ High Density.docx](https://github.com/KUAS-Korea/KUAS-2021-igem/files/7363951/Results_.High.Density.docx)

Among the different constructs, the only construct with promising modeling results was the construct with J23106 B0032 which showed around 10^1.5 dimers in at 1cell/nL and 10^2.7 dimers at 10^5cells/nL.

![image](https://user-images.githubusercontent.com/87188354/137712108-7675f544-5c59-49ba-bd36-64320905e597.png)
The graph above shows the internal(int) and external(ext) HSL in molecules
![image](https://user-images.githubusercontent.com/87188354/137711927-4eaa58a1-a28f-4216-9543-e7875d67a774.png)
The graph above shows the number of HSL/LuxR dimers over an hour.

Therefore our final design will use J23106 & B0032 for both luxR and luxI
![image](https://user-images.githubusercontent.com/87188354/137717150-3a532a67-31b9-4fb7-9d45-99388d7c6817.png)


References

1. http://2018.igem.org/Team:Valencia_UPV/Model
