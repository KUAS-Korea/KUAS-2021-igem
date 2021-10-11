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


Possible imporvements
