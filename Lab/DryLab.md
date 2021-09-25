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

Then we modeled the production of LuxR/HSL dimer, which is the transcription activator of pLux.

![image](https://user-images.githubusercontent.com/87188354/134772693-37ceb8e1-96cb-4489-b386-63b56a6a020e.png)

However, there were too much dimers(over 10^2.5 dimers) that an induced increase in protein production could not be achieved. So we tried a weaker promoter and RBS combination and found that J23106 and 
B00 was the right choice.


## cI at different HSL/LuxR concentrations
    
    p.Kd = MolesToMolecules(200*10^(-9)); % dissociation constant of (LuxR·AI)2 to the lux promoter 200[nM] fitted https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3614889/
    alpha = p.k2 * p.k1 * p.CN / p.d1; % Maximal Expression rate [molecules/min]   
    % Rest of the parameters are same as above
    Protein  = alpha ./p.d2 .* (TF.^2 ./ (p.Kd +TF.^2))
![image](https://user-images.githubusercontent.com/87188354/134773893-b7194059-6af8-4751-ba8a-9c0f2fc21aeb.png)
