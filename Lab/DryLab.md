# Reference
* AND gate (Light/Arabinose) [ACS Synbio](https://pubs.acs.org/doi/10.1021/acssynbio.8b00280)
* Model (check ODE equations) [ACS Synbio Suppplement](https://pubs.acs.org/doi/suppl/10.1021/acssynbio.8b00280/suppl_file/sb8b00280_si_001.pdf)
* Python module - [SynBioPython](https://github.com/Global-Biofoundries-Alliance/SynBioPython)
> Jupyternotebook - [AND gate modelling example](https://github.com/Global-Biofoundries-Alliance/SynBioPython/blob/master/examples/genbabel.ipynb)


## LuxR, LuxI Constitutive Protein expression: J23100, B0034 
We tried to model HSL production from our design

    %Parameters
    p.CN = 200;        % plasmid number  pSB1C3 (100-300 copies/cell)  
    p.d1 = 0.247;   % mRNA degradation rate  [1/min] 
    p.d2 = 0.008492;      % protein degradation rate [1/min] Gaston day >2018 UPV arbitary
    p.k2 = 0.082;      %  translation rate  [1/min] B0034
    p.VmaxL = 1.1;       % mol HSL per (mol LuxI) per (min) Imperial 2006
    p.k1 = 1.39;      %  transcription rate [1/min] J23100 UPV 2018
    %p.dR = 0.5;      % AHL,LuxR dimerization [1/uM(-3) 1/min] 2013 ZTH 2005 Basu
    p.kdRA = 100*10^(-9);   % dissociation constant of LuxR to A, https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3614889/    
    p.kdRA2 = 20*10^(-9);       % dissociation constant of LuxR·AI dimerization fitted, https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3614889/    
    p.k_RA = 10;         % unbinding rate LuxR to AHL [1/min] estimated https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3614889/ 
    p.kRA = p.k_RA/p.kdRA;     % binding rate      
    p.k_RA2 = 1;          % dissociation rate of dimer (LuxR·AI)2 [1/min] estimated https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3614889/ 
    p.kRA2 = p.k_RA2/p.kdRA2;   % dimerization rate
    
    %x1 = mRNA
    dxdt(1,1) =p.CN*p.k1-p.d1*x(1);
    %x2 = LuxI
    dxdt(2,1)=p.k2*x(1)-p.d2*x(2);
    %x3 = LuxR
    dxdt(3,1)= p.k2*x(1)-p.d2*x(3) -x(5);
    %x4 = HSL
    dxdt(4,1) = p.VmaxL*x(2) -x(5);
    
The resulting plot is as below. 

![image](https://user-images.githubusercontent.com/87188354/134769912-c4c253de-1b04-4a8b-84f8-08fc067cd724.png)

Then we modeled the production of LuxR/HSL dimers(the transcription activator of pLux) in our original construct with strong promoters (J23100) for LuxR and LuxI.

![image](https://user-images.githubusercontent.com/87188354/134772693-37ceb8e1-96cb-4489-b386-63b56a6a020e.png)

However, there were too much dimers(In SkyBlue, over 10^2.5 dimers) that an induced increase in protein production could not be achieved. 

So we tried a weaker promoter J23106. 

![image](https://user-images.githubusercontent.com/87188354/134774196-b8d865fb-a5cc-4188-8e66-e6696176cde1.png)

This promoter suits our purpose; HSL/LuxR dimers reached around 10^1.5 molecules which is low enough to expect enough induction at higher number of HSL/LuxR dimer molecules.


## Construct selection
In the previous model we only modeled the molecules with in the cytoplasm. However, it is necessary to consider the external environment too if we want to model the outcomes at different cell densities. In the updated model, we included a variable for the external HSL concentration. 
First, when there is only one cell in the environment, it would be reasonable to consider the external HSL as 0. Internal HSL concentration would be always higher than external HSL, so no HSL would return back into the cell. In the single cell model, external HSL concentration is fixed to 0. 



세포 하나일 때와 여러 개일때 dimer 의 농도가 다른 조합은 R100 34 / I106 32 밖에 없었다. 

[Results for each construct.docx](https://github.com/KUAS-Korea/KUAS-2021-igem/files/7252979/Results.for.each.construct.docx)
### Single cell: external HSL = 0
![image](https://user-images.githubusercontent.com/87188354/135295998-2e6ae6fe-4ebb-4ec2-a4a8-2bbf78ebb45b.png)
Dimers around 1e1.5

### High density culture: closed 1ml env, cells 1e-3(dark color) ~ 1e5(bright color) 

When cells are in high density, it would be fairly reasonable to imagine a region homogenous in HSL concentration. So in the high density model, we considered a mL of closed volume. When cells produce HSL it will start to accumulate. We plotted graphs with different number of cells in the volume with different combinations of promoters and RBS. Among the different constructs, the only construct with promising modeling results was the construct with J23106 B0034 which showed around 10^1.5 dimers in the single cell model and 10^2.7 dimers in the high density model.

![image](https://user-images.githubusercontent.com/87188354/135296285-d6b808c3-11e8-4cff-aed6-674428672736.png)
Dimers >1e 2.5
![image](https://user-images.githubusercontent.com/87188354/135296306-2c1edd0a-9f53-4468-bbee-e1bfce6c6a0d.png)


## cI at different HSL/LuxR concentrations
    
    p.Kd = MolesToMolecules(200*10^(-9)); % dissociation constant of (LuxR·AI)2 to the lux promoter 200[nM] fitted https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3614889/
    alpha = p.k2 * p.k1 * p.CN / p.d1; % Maximal Expression rate [molecules/min]   
    % Rest of the parameters are same as above
    Protein  = alpha ./p.d2 .* (TF.^2 ./ (p.Kd +TF.^2))
![image](https://user-images.githubusercontent.com/87188354/134773893-b7194059-6af8-4751-ba8a-9c0f2fc21aeb.png)

## ODEs

Model Single Cell
1.  ⅆ[mRNA_100 ]/ⅆt   = CN×k_1(100) − d_1×[mRNA_100 ]
2.  ⅆ[LuxI]/ⅆt  = k_2(34) ×[mRNA_100 ]  − d_2×[LuxI]
3.  ⅆ[LuxR]/ⅆt  = k_2(34) ×[mRNA_100 ]  − d_2×[LuxR]   − k_RA×[LuxR][HSL]  + k_RA×[HSL/LuxR]
4.  ⅆ[HSL]/ⅆt  = V_max×[LuxI]  − k_RA×[LuxR][HSL]  + k_RA×[HSL/LuxR]  −k_diff×[HSL]
5.  ⅆ[HSL/LuxR]/ⅆt  =  k_RA×[LuxR][HSL]  − k_RA×[HSL/LuxR]  −2×{k_((RA)_2 )×[HSL/LuxR]^2+ k_((RA)_2^− )×[HSL/LuxR D]}
6.  ⅆ[HSL/LuxR D]/ⅆt  =  k_((RA)_2 )×[HSL/LuxR]^2  − k_((RA)_2^− )×[HSL/LuxR D]
7.  ⅆ[mRNA_106 ]/ⅆt  =  CN×k_1(106) − d_1×[mRNA_106 ]
![image](https://user-images.githubusercontent.com/87221166/137178223-a3d765e0-58d2-4e31-88ba-e6ceb87d8b5a.png)

