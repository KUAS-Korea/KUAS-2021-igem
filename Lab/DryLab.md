# Reference
* AND gate (Light/Arabinose) [ACS Synbio](https://pubs.acs.org/doi/10.1021/acssynbio.8b00280)
* Model (check ODE equations) [ACS Synbio Suppplement](https://pubs.acs.org/doi/suppl/10.1021/acssynbio.8b00280/suppl_file/sb8b00280_si_001.pdf)
* Python module - [SynBioPython](https://github.com/Global-Biofoundries-Alliance/SynBioPython)
> Jupyternotebook - [AND gate modelling example](https://github.com/Global-Biofoundries-Alliance/SynBioPython/blob/master/examples/genbabel.ipynb)

Protein expression: J23100, B0034 
%Parameters
    p.CN = 17;        % plasmid number  pACYC184 (17 copies/cell)  
    p.d1 = 0.247;  % mRNA degradation rate  [1/min]
    p.d2 = 0.008492;      % protein degradation rate [1/min]
    p.k2 = 0.082;      %  translation rate  [1/min] 
    p.k1 = 1.1081616;      %  transcription rate [1/min]
    
%x1 = mRNA
dxdt(1,1) =p.CN*p.k1-p.d1*x(1);
%x2 = Protein
dxdt(2,1)=p.k2*x(1)-p.d2*x(2)

![image](https://user-images.githubusercontent.com/87188354/134359194-2146e708-b212-48ba-97ef-8a4148aa181f.png)
