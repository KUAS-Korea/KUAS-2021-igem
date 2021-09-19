This is the description of our project

Light dependent Violacein production: 
![alt text](https://github.com/KUAS-Korea/KUAS-2021-igem/blob/main/Light%20dependent%20Vio.%20production.PNG)

AND gate(light& cell density)
![alt text](https://github.com/KUAS-Korea/KUAS-2021-igem/blob/main/AND%20gate(Light%20and%20Cell%20density).png)

You can download the xml file from the link below and view it with SBOL canvas
[link](https://github.com/KUAS-Korea/KUAS-2021-igem/blob/main/Light%20dependent%20Vio%20production.xml)


# Mub:
To minimize the engineered cells from detaching and leaking out to the environment after inoculation, we had to increase the cells’ adherence to the outermost mucus layer of the amphibians’ skin. Therefore, we decided to display mucus binding domains on the outer membrane of the cells. 
While in search for mucus binding domains, we found that a lactobacillus strain(L. reuteri 1063) possessed adherence properties to intestinal mucus. However, since lactobacillus bacteria are gram-positive, we needed to use a different mechanism to display the domains on the outer-membrane of our gram-negative chassis. 
A well-known surface display protein OmpA was chosen as our means to display the mucus binding domains.
From various candidates of proteins involved in mucus binding (1), we chose Mub2 for surface display. 
The identification and initial characterization of these protein domains were done by Roos and Jonsson(2). lambda phage libraries were created from L.reuteri 1063’s DNA and the protein of interest was subsequently selected and identified. The protein contains a N terminal signal sequence, C teriminal LPTG anchoring motif, 6 Mub1 repeats(RI-RVI) and 8 Mub2 repeats(R1-R8). Both types of domains exhibited adhesive properties to pig gastric mucin.

![image](https://user-images.githubusercontent.com/87188354/130601413-f5ec9024-08cd-47aa-831c-993878bba80f.png)

Another research by MacKenzie et. al (3). highlights the role of this domain in binding to mucus by revealing that L. reuteri strains with mucus adhesive properties possess and express Mub domains.
Crystal structure of the Mub2 domain was revealed by MacKenzie et. al(4).
The domain is composed of two structurally similar subdomains: the N-terminal domain(B1) with a ubiquitin like beta-grasp fold, and the C terminal domain(B2) with a non-canonical version without an alpha helix. 
 
 ![image](https://user-images.githubusercontent.com/87188354/130601467-e77a0662-94a0-4501-9673-78af2b026b9f.png)

Since Mub1,2 domains were better characterized, we decided to fuse these domains to OmpA proteins (terminus? linker?)
Just as the we fused R4-7 Mub2 domains to the OmpA part…

# CadC:
For pathogen detection, receptor mediated detection was necessary since it was unclear whether the pathogen associated molecules would diffuse into the cell.
In search for a suitable system, we looked at previous igem projects.  
We found a few previous projects that included a receptor mediated detection system.
Various receptor based systems were tested by previous igem teams, but the one that was the most suitable overall for our project was the CadC-pCadBA used by team Uppsala (5). 
Their project was based on a previous research (6) which engineered the wild type CadC receptor by fusing caffein-binding single domain antibodies(VHHs) at the periplasmic portion. Upon ligand binding, the periplasmic domain(C-terminus) dimerizes and brings together the split DNA binding domains(DBDs) in the cytosolic side(N-terminus) to express genes under the pCadBA promoter.
This research further improved the design by testing different version of linkers and found that the removal of the juxtamembrane linker increased the fold change of the reporter gene expression. 


# CERK1, LYK5:
To use the CadC system, we needed to find domain that dimerizes upon the binding of the pathogen specific ligand. 
This property was found in the chitin binding receptor CERK1 of A. thaliana. This Not only the whole receptor, but also just the ectodomain(ECD) showed dimerizing properties in pull down and western blotting experiments when treated with chitin. No dimerization was observed when peptidoglycan was treated. Crystallization data revealed the presence of 3 LysM domains in atCERK1-ECD. It also enabled the identification of key residues of atCERK1 interacting with NAG of chitin. Structure of ECD can be viewed at PDB (7)
This domain will be fused at the periplasmic side of CadC. 

Also, a coreceptor LYK5 was shown to facilitate the dimerization. LYK5 showed even higher binding affinity towards chitin and LYK-CERK association in the presence of chitin was stronger than the dimerizing association of CERK1 monomers. Dimerization of CERK1 was absent in LYK5 mutant protoplasts (8). 
The dimerization of LYK5 is independent of chitin or CERK1 presence. Therefore, to prevent spontaneous dimerization of DBDs, LYK5 domains will be fused to CadC that is missing a DBD. 

With the information gathered we decided to fuse CERK1-ECD at the periplasmic side of the CadC protein. The chitin of the cell wall of the fungal pathogen Bd will trigger the dimerization of the CERK1-ECD and the subsequent dimerization of intracellular DBD and the activation of pCadBA. 
We also plan to express LYK5 fused CadCs to facilitate CERK1 dimerization. However, the dimerization of LYK5 is independent of chitin or CERK1 presence, so LYK5 domains will be fused to CadC that is missing a DBD.

One of the concerns during the design process was that while the CERK1-ECD is a N terminus domain, it had to be attached to the C terminus of CadC. However, we observed that the N & C terminus of CERK1-ECD is located close to each other (9). We thought that since the two termini are closely located, it wouldn’t make much of a difference whether the connection occurs in one or another. Though our intuition needs validation, we decided to proceed with the design. We also included a flexible GS linker between CERK-ECD and CadC so that CERK1-ECD is allowed more freedom in orientation while binding to chitin. 

# References
1. Juge N. Microbial adhesins to gastrointestinal mucus. Trends Microbiol. 2012 Jan;20(1):30-9. doi: 10.1016/j.tim.2011.10.001. Epub 2011 Nov 14. PMID: 22088901.

2. Roos S, Jonsson H. A high-molecular-mass cell-surface protein from Lactobacillus reuteri 1063 adheres to mucus components. Microbiology (Reading). 2002 Feb;148(Pt 2):433-442. doi: 10.1099/00221287-148-2-433. PMID: 11832507.

3. MacKenzie DA, Jeffers F, Parker ML, Vibert-Vallet A, Bongaerts RJ, Roos S, Walter J, Juge N. Strain-specific diversity of mucus-binding proteins in the adhesion and aggregation properties of Lactobacillus reuteri. Microbiology (Reading). 2010 Nov;156(Pt 11):3368-3378. doi: 10.1099/mic.0.043265-0. Epub 2010 Sep 16. PMID: 20847011.

4. MacKenzie DA, Tailford LE, Hemmings AM, Juge N. Crystal structure of a mucus-binding protein repeat reveals an unexpected functional immunoglobulin binding activity. J Biol Chem. 2009 Nov 20;284(47):32444-53. doi: 10.1074/jbc.M109.040907. Epub 2009 Sep 16. PMID: 19758995; PMCID: PMC2781659.

5. https://2020.igem.org/Team:UofUppsala/Design
6. Chang HJ, Mayonove P, Zavala A, De Visch A, Minard P, Cohen-Gonsaud M, Bonnet J. A Modular Receptor Platform To Expand the Sensing Repertoire of Bacteria. ACS Synth Biol. 2018 Jan 19;7(1):166-175. doi: 10.1021/acssynbio.7b00266. Epub 2017 Oct 30. PMID: 28946740; PMCID: PMC5880506.

7. Liu T, Liu Z, Song C, Hu Y, Han Z, She J, Fan F, Wang J, Jin C, Chang J, Zhou JM, Chai J. Chitin-induced dimerization activates a plant immune receptor. Science. 2012 Jun 1;336(6085):1160-4. doi: 10.1126/science.1218867. PMID: 22654057.

8. Cao Y, Liang Y, Tanaka K, Nguyen CT, Jedrzejczak RP, Joachimiak A, Stacey G. The kinase LYK5 is a major chitin receptor in Arabidopsis and forms a chitin-induced complex with related kinase CERK1. Elife. 2014 Oct 23;3:e03766. doi: 10.7554/eLife.03766. PMID: 25340959; PMCID: PMC4356144.


# Why tryptophol?
The first time we saw tryptopol was in salamander Plethodon cinereus experiments. 
In the experiment, Batrachochytrium dendrobatidis, which is symbiotic with Janthinobacterium lividium, was extracted from the supernatant of HPLC(High-performance liquid chromatography) and separated through NMR(Nuclear Magnetic Resonance) and HR-MS(High Resolution-Mass Spectrometer). These substances are tryptophol and violacein. In other words, a substance that inhibits Batrachochytrium dendrobatidis is tryptophol.
Our aim is to find and over-express substances that can inhibit Batrachochytrium dendrobatidis in frog skin, so tryptopol found in mucous skin which can inhibit Batrachochytrium dendrobatidis is sufficiently appropriate for our goal.


# What is Tryptophol and Violacein?
Tryptophol is synthesized from the amino acids phenylalanine, tryptophan, and tyrosine, respectively, by chemical degradation through a three-step biochemical reaction comprising transamination, decarboxylation, and reduction called Ehrlich pathway.
In Saccharomyces cerevisiae, tryptophol is Aro80p’s transcription activator. Tryptophol activates the transcription factor Aro80p and, consequently, the expression of the ARO9 and ARO10 transaminase and decarboxylase genes, which results in a positive feedback loop.
The number of Batrachochytrium dendrobatidis cells grown for 5 days in TGhL medium(control) decreases when high concentration and density in CM(conditioned medium). (Figure 1A, 1B)
Comparison with the supernatant solution of a particular size of the molecule filtering showed that no disruption to growth of Batrachochytrium dendrobatidis was measured at 500Da and 1000Da. In other words, the growth inhibitor of Batrachochytrium dendrobatidis is less than 500Da. (Figure 1C)
This time, they treated the tryptophol concentrations differently from 10, 23, 50, 100, 250, and 500 uM, and significant degradation occurred from more than 100 uM. (Figure 2B)

Furthermore, the relationship between Batrachochytrium dendrobatidis growth and the production of tryptophol was observed with different numbers of inoculated spores in the early stages, confirming that they were growing at a constant concentration regardless of the initial concentration. (Figure 3, 4)

 In addition, additional tryptopol production based on the initial tryptopol treatment concentration was observed to be directly proportional called autostimulation, which means that the more existing it is, the newer it is. (Figure 5)
 
 
 The bisindole alkaloid violacein is a natural bluepurple pigment isolated from Gram-negative bacteria. The violacein is an indole derived violet pigmented compound and a promising agent with following biological activities: antibacterial antifungal, antiprotozoan, and anticancer. These biological and pharmacological activities of violacein have made it attractive for biotechnology research. Several terrestrial and marine gram-negative bacteria were known to produce violacein including Chromobacterium violaceum, Janthionobacterium lividum and 7 other genus. Violacein is formed by enzymatic condensation of two tryptophan molecules, requiring the action of five proteins. The genes required for its production, vioABCDE, and the regulatory mechanisms employed have been studied within a small number of violacein-producing strains. In Massilia genus, three strains have been reported as producing violacein and recently, the complete genome of Massilia sp. strain NR 4-1 as well as five key enzymes of the violacein biosynthesis has reported.
 
 Recent study sought to engineer E. coli and its metabolic pathways to improve the violacein yields. For this, the authors overexpressed the genes related to tryptophan production and knocked out several genes and pathways which would detract the carbon flux away from this amino acid. The engineered E. coli strain, TRP11, produces about 20 𝜇mol tryptophan per gram DCW (gDCW). By comparison, the control wild-type strain only produced about 0.3 𝜇mol tryptophan/gDCW, representing an increase in the tryptophan concentration of more the 60-fold. They next introduced the vioD gene into the chromosome of this strain and a plasmid expressing the vioABCE genes. Performing fed batch fermentations over a 12-day period with this strain, which they designated as Vio-4, they were able to generate 710 mg/L violacein at more than 99% purity, demonstrating that E. coli can be used to produce high level concentrations of this bisindole specifically.


## Reference

* Brucker, Robert M., et al. “Amphibian Chemical Defense: Antifungal Metabolites of the Microsymbiont Janthinobacterium Lividum on the Salamander Plethodon Cinereus.” Journal of Chemical Ecology, vol. 34, no. 11, 2008, pp. 1422–1429., doi:10.1007/s10886-008-9555-7. 

* Verbrugghe, Elin, et al. “Growth Regulation in Amphibian Pathogenic CHYTRID Fungi by the Quorum Sensing Metabolite Tryptophol.” Frontiers in Microbiology, vol. 9, 2019, doi:10.3389/fmicb.2018.03277. 

* Myeong, Nu Ri, et al. (2016). "Complete genome sequence of antibiotic and anticancer agent violacein producing Massilia sp. Strain NR 4-1". Journal of Biotechnology. 223: 36–7. doi:10.1016/j.jbiotec.2016.02.027

* Choi, S.Y., et al. (2015). Violacein: properties andproduction of a versatile bacterial pigment. BioMed Res. Int. 2015, 465056.

* Haisheng Wang, et al. (2012). Biosynthesis and characterization of violacein, deoxyviolacein and oxyviolacein in heterologous host, and their antimicrobial activities

* Seong Yeol Choi, et al. (2015).  Violacein: Properties and Production of a Versatile Bacterial Pigment, Hindawi


# What is AND gate?
The AND gate gives a high output only if both the inputs are high and represented as A·B or AB. Therefore, using AND gate, input A and B are set to blue light sensor and cell density. And if both inputs exceed the threshold, the parts are activated.
사진3개 첨부
Our team used BBa_K568004.( http://parts.igem.org/Part:BBa_K568004이거 위키에 링크 첨부하면 좋을듯)

# Why we choose AND gate?
We want to produce violacein when frogs are exposed to chytridium in several conditions. Therefore, AND gate BBa_K568004 was used to produce violacein when frogs were exposed to these two conditions-normal activity->blue light, exposure to chytridium->chitin detection-corresponding.The first input uses the substance produced when detecting chytridium and then the supD tRNA produced from the previous input is available when exposed to blue light, so we can produce violacein only under the conditions we want.

# BLUE light sensor.
We chose the promoter that is regulated by the YcgF/E system as blue light sensor. The domains YcgE and YcgF are endogenously present in Escherichia coli. The domains are thought to regulate the biofilm formation when E.coli is exposed in an aquatic environment. Blue light induces the dimerization of YcgF that then directly bind to the repressor YcgE and releases the repressor from the operator. The expression of YcgE and YcgF and therefore as well the expression of the controlled gene is increased at low temperatures. (위키에 이 부분 각주 달아서 따온거 밝히기)->이거 문장 다듬어야합니다 따온부분임,

## Reference
http://parts.igem.org/Part:BBa_K568004
http://2011.igem.org/Team:TU_Munich/project/introduction


# Surface display (surface expression)

For the treatment of frog skin disease, we devised cells that produce violacein. To increase the efficiency of this method, our designed cells should be fixed on the surface of the frog skin to increase the concentration of cells near the skin. To implement this idea, we used a surface expression system.

Microbial cell-surface display is a method carried out by expressing a heterologous peptide or protein (the passenger protein) as a fusion protein with various anchoring motifs, which are usually cell-surface proteins or their fragments (carrier proteins). The surface expression method is used in various applications such as library screening, live vaccines, whole-cell biocatalysis, bioremediation, biosensor, and biofuel.

Many surface display systems have been developed for E.coli. Each method is based on a variety of anchoring motifs, and accordingly, the passenger protein must be fused in various ways. Among them, we investigated the method using autotransporter and the method using Lpp-OmpA hybrid.

Autotransporters are proteins located in the outer membrane without further cutting and are displayed through the Type Va Secretion method. It consists of three main parts – signal sequence located in N-terminal, the passive domain, and translocator domain in C-terminal.
The N-terminal signal domain directs the synthesized polypeptide itself to periplasm through Sec apparatus.
The C- terminal translocator domain consists of α-helical secondary structure and β-domain (250-300 amino acid residues, 14 antiparallel amphipathic β-strands) that make a hydrophilic pore in the outer membrane. Through this pore, the internal passenger domain connected with α-helix is displayed on the outer membrane.
Various types of protein domains such as adhesin, protease, esterase, and lipase are located in the passenger domain.
In summary, autotransporters move to outer membrane using signal domain after expression, the translocator domain creates a pore in the outer membrane, and the passenger domain passes through the pore to outer membrane and displayed. Therefore, If the passenger domain is converted into the gene of another protein domain in interest to be displayed, the changed protein domain will be displayed on the cell surface.
Since the Passenger domain is between the N-terminal signal domain and the C-terminal translocator domain, the use of autotransporter requires a sandwich fusion strategy that changes genes in between.

Unlike autotransporter, Lpp-OmpA hybrid uses a C-terminal fusion method. Lpp-OmpA hybrid consists of signal sequence, first nine N-terminal residues of the mature E. coli lipoprotein, and the residues 46–159 or 46–66 of the E. coli outer membrane protein A (OmpA).
Lpp part is necessary for proper localization to the outer membrane, and the OmpA part is responsible for the transportation of foreign proteins fused at the C-terminus across the outer membrane. 

As shown in the figure above, passenger domain can be fused into OmpA's C-terminal and transported across the outer membrane. Therefore, the C-terminal fusion strategy should be used in the Lpp-OmpA hybrid.

In 2008 iGEM, the Warsaw team synthesized the BBa_K103006 biobrick part, which consists of Lpp: Lipoprotein signal peptide, OmpA: Outer membrane protein A, linker (Gly-Ser-Gly), which enables us to attach the display domain behind the linker. Using this part, our designed protein can be easily synthesize just by attaching the protein domain we wanted to C-terminal. Therefore, we decided to use Lpp-OmpA hybrid system for our design.

추가할 내용 : OmpA + mucin 결합 단백질 내용, 실제 실험 내용 (warsaw 팀 파츠 사용, 실험방법까지), surface display 확인 실험 내용

