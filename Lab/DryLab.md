# Reference
* AND gate (Light/Arabinose) [ACS Synbio](https://pubs.acs.org/doi/10.1021/acssynbio.8b00280)
* Model (check ODE equations) [ACS Synbio Suppplement](https://pubs.acs.org/doi/suppl/10.1021/acssynbio.8b00280/suppl_file/sb8b00280_si_001.pdf)
* Python module - [SynBioPython](https://github.com/Global-Biofoundries-Alliance/SynBioPython)
> Jupyternotebook - [AND gate modelling example](https://github.com/Global-Biofoundries-Alliance/SynBioPython/blob/master/examples/genbabel.ipynb)


## Constitutive Protein expression: J23100, B0034 
%Parameters
    p.CN = 17;        % plasmid number  pACYC184 (17 copies/cell)  
    p.d1 = 0.247;  % mRNA degradation rate  [1/min]
    p.d2 = 0.008492;      % protein degradation rate [1/min]
    p.k2 = 0.082;      %  translation rate  [1/min] 
    p.k1 = 1108.1616;      %  transcription rate [1/min]
    
%x1 = mRNA
dxdt(1,1) =p.CN*p.k1-p.d1*x(1);
%x2 = Protein
dxdt(2,1)=p.k2*x(1)-p.d2*x(2)

![image](https://user-images.githubusercontent.com/87188354/134359194-2146e708-b212-48ba-97ef-8a4148aa181f.png)

## cI at different HSL/LuxR concentrations
    p.IC50 = 4.45;      % IC50 of plux on agar plates 2013 Zurich [nM]
    p.Kd =  p.IC50;     %p.koff/p.kon Disosiation constant [molecules], IC50^2
    alpha = p.k2 * p.k1 * p.CN / p.d1; % Maximal Expression rate [molecules/min]
    
Rest of the parameters are same as above
Protein  = alpha ./p.d2 .* (TF.^2 ./ (p.Kd +TF.^2))

![image](https://user-images.githubusercontent.com/87188354/134527931-3da1d566-b31f-44af-9259-cf3d084975a1.png)
