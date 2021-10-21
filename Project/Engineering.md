# Kill switch design
As a safety measure, we have designed a kill switch which is activated when the cell detaches from the colony. This mechanism will prevent the cells from surviving when they detach from the frog's mucus layer.
This composite part contains the luxR,luxI system, cI inverter, and a MazE,MazF toxin-antitoxin system. 
 파트 그림

According to this design, when cells exist in high densities, there should be enough HSL to induce the expression of cI repressors that would repress the expression of MazF toxin. 
On the other hand, for the detached cell, HSL must be in concentrations which is not enough to induce cI repressor expression. Without the repressor MazF toxin will increase and eventually kill the cell.

However, While designing our quorum sensing based kill switch, we were unsure of which combination of promoters and RBS to use for LuxR and LuxI expression. Therefore, we decided to create quorum sensing models with different combination of promoters(J23100,J23106) and RBS(B0034,B0032), and revise the design with the one with the most promising results.
We created two different models with Matlab for two different situations. The first model considers a situation when a single cell has detached from the colony and presumes that external concentration of HSL is 0. In this model, HSL/LuxR dimers must be low enough to prevent the expression of cI repressors.
The second model assmues a colony of cells in a closed 1mL of space. HSL produced by the cells will accumulate within this space and eventually will start to flow back into the cell and induce expression.
The results for the model must show enough HSL to induce cI production.


The following are the results for each combination of promoters and RBS.



The only construct that showed a significant difference of HSL/LuxR dimers at the two models contained 
Through this modeling process, we were able to finalize the design which is expected to show the most promising results. 


# Disabling CadC DBD

The dimerization of LYK5 is independent of chitin or CERK1 presence. Therefore, to prevent spontaneous gene experssion by the dimerization of DBDs, LYK5 domains have to be fused to CadC with a nonfunctional DBD.
Luckily, we found a research paper which characterized the binding mechanism of CadC DBDs. Schlundt A et. al. identified Aa residues involved in both specific and non specific DNA binding. 

![image](https://user-images.githubusercontent.com/87188354/138222383-11f06f11-80c7-43da-bf93-f96ee69576d9.png)

Figure source: Schlundt A et. al. Structure-function analysis of the DNA-binding domain of a transmembrane transcriptional activator. Sci Rep. 2017 Apr 21;7(1):1051. doi: 10.1038/s41598-017-01031-9. PMID: 28432336; PMCID: PMC5430869.
Open Access This article is licensed under a Creative Commons Attribution 4.0 International License, which permits use, sharing, adaptation, distribution and reproduction in any medium or format, as long as you give appropriate credit to the original author(s) and the source, provide a link to the Creative Commons license, and indicate if changes were made. 

Diagram (d) in the figure above shows the interaction of Aa residues and the DNA. Red dotted lines indicate specific binding while the black dotted lines indicate non-specific binding. Among the essential Aa residues Thr69 does not directly bind to DNA but stabilizes his66 and arg50 which are involved in DNA binding. Thus we decided to mutate Thr69 to inhibit DNA binding.

![image](https://user-images.githubusercontent.com/87188354/138248734-b19eca73-b097-4981-9210-68db8fde9feb.png)

Figure source: Schlundt A et. al. Structure-function analysis of the DNA-binding domain of a transmembrane transcriptional activator. Sci Rep. 2017 Apr 21;7(1):1051. doi: 10.1038/s41598-017-01031-9. PMID: 28432336; PMCID: PMC5430869.
Open Access This article is licensed under a Creative Commons Attribution 4.0 International License, which permits use, sharing, adaptation, distribution and reproduction in any medium or format, as long as you give appropriate credit to the original author(s) and the source, provide a link to the Creative Commons license, and indicate if changes were made. 

Experimental results from the diagram above shows that T69A mutation completely disables gene expression from the promoter cadBA. So we substituted thr69 with ala so that the dimer does not have cadBA activation in our part. Though we couldn't test this part this year, we hope our rational design process turns out to be successful. 
