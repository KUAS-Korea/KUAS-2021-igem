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


# Frog skin composition 
Chytridomycosis is an infectious disease of amphibians caused by the chytrid fungus (Batrachochytrium dendrobatidis). Batrachochytrium dendrobatidis is transmitted through the skin of amphibians and has a critical effect on survival, causing rapid population decline. Amphibian skin is unique because it is physiologically active, allowing the skin to tightly regulate respiration, water, and electrolytes. It is not yet known exactly how the fungus kills amphibians but it is thought that it may cause mortality through disrupting the normal function of the skin resulting in electrolyte depletion and osmotic imbalance.

Our team plans to study focuses on the frogs of amphibians. Frog skin is composed of epidermal and dermal layers, with each layer predominantly consisting of epithelial and fibroblastic cells.The epidermal layer consists of stratum germinativum, stratum spinosum, stratum granulosum, and stratum corneum, and the mucosal layer exists at the outermost part of the epidermis.

![image](https://www.frontiersin.org/files/Articles/433806/fimmu-09-03128-HTML/image_m/fimmu-09-03128-g001.jpg)

Stratum germinativum is the innermost layer of the epidermis, composed of mitotically proliferating keratinocytes, melanocytes (pigment-producing), Langerhans cells (involved in immunity) and Merkel cells (tactile receptors). It actively divides to provide new cells for skin loss due to normal exfoliation and provides Keratinocytes to the stratum spinosum, which migrate to the stratum corneum, the uppermost layer of the skin.
<br/>Stratum spinosum comprised of distinctive keratinocytes (called prickle cells). Fibrillary proteins required for desmosome formation are synthesized and keratinization begins in this layer.
<br/>Stratum granulosum consists of granular keratinocytes migrated from the stratum spinosum. These keratinocytes contain keratohyalin granules that aid in the binding of keratin filaments and also have lamellar bodies filled with lipids. These keratinocytes secrete them as they migrate from stratum spinosum to the upper layers of the epidermis. At the same time, when they reach the stratum corneum, they lose their nuclei and organelles and become corneocytes.
<br/>Stratum corneum is the outermost layer of the epidermis composed of keratinocytes and is responsible for most of the protective barrier function of the skin. The stratum corneum has 10 to 30 corneocytes layers and has a thickness of 10 to 40 μm. When the keratinocyte becomes a corneocyte, it becomes filled with keratin proteins. Corneocytes are held together through corneodesmosomes. 
<br/>The outermost mucosal layer consists of mucus, and Mucus contains several interdependent host factors including antimicrobial peptides (AMPs), lysozymes and mucosal antibodies as well as microbial-community factors, including symbiotic skin bacteria producing antifungal metabolites.

#  Bd infection process and pathology

Exposure to Bd occurs when the defense mechanisms of the epidermis (AMP, bacteria, etc.) are insufficient. Zoospore penetrates the mucus layer, and zoosporangia developing occurs in the deeper host cell skin layer.

![image](http://revistabionatura.com/images/2021.06.01.28-Figure1.png)

Generally, Bd has an endobiotic life cycle in which the fungus grows inside the host. Zoospores inhabit the skin and develop a germ tube that penetrates the host cell membrane to transfer genetic material. The distal end of the germinal tube then swells and produces a new intracellular chytrid talus and sporangium. This process is repeated, each time burrowing into deeper layers of the host's epidermis. Once fully penetrated, immature sporangia are transported to the skin surface. When the sporangia finally mature, discharge tubes release mature zoospores into the environment to infect new individuals. 

(좀 더 자세한 설명)Upon colonization of the host epidermis, the zoospores encyst; the flagellum is absorbed and a cell wall is formed. Next, the zoospore cyst germinates and develops a germ tube that invades the host epidermis. At the tip of the germtube a new sporangium arises. Subsequently, the fungus proliferates intracellularly, within the cells of the stratum corneum and the stratum granulosum. Immature sporangia are carried from the deeper skin layers to the skin surface by differentiating epidermal cells. At the time sporangia have developed discharge tubes and contain mature zoospores, they finally occur in stratum corneum where the zoospores are released in the environment.
Bd can also have an epibiotic life cycle, growing on the surface of the host's skin, where the zoospores are encysted and form anucleated rhizoids. The cyst matures in a zoosporangium and releases zoospores in a matter of only four days. 

Infection is mainly associated with a mild to severe irregular thickening (hyperkeratosis) of the outermost keratinized layers of the epidermis (the stratum corneum and stratum granulosum), erosion of the stratum corneum, and increased tissue growth (hyperplasia) of the stratum spinosum which lies beneath the keratinized superficial skin layers.
Also ulceration of the skin may occur. Other pathological changes in the epidermis adjacent to the foci of infection include mild focal necrosis, intercellular edema (spongiosis), cytoplasmic degeneration with minimal to mild inflammation and vacuolation of the deeper cell layers.


# Why tryptophol?
The first time we saw tryptopol was in salamander Plethodon cinereus experiments. 
In the experiment, Batrachochytrium dendrobatidis, which is symbiotic with Janthinobacterium lividium, was extracted from the supernatant of HPLC(High-performance liquid chromatography) and separated through NMR(Nuclear Magnetic Resonance) and HR-MS(High Resolution-Mass Spectrometer). These substances are tryptophol and violacein. In other words, a substance that inhibits Batrachochytrium dendrobatidis is tryptophol.
Our aim is to find and over-express substances that can inhibit Batrachochytrium dendrobatidis in frog skin, so tryptopol found in mucous skin which can inhibit Batrachochytrium dendrobatidis is sufficiently appropriate for our goal.


# What is Tryptophol?
Tryptophol is synthesized from the amino acids phenylalanine, tryptophan, and tyrosine, respectively, by chemical degradation through a three-step biochemical reaction comprising transamination, decarboxylation, and reduction called Ehrlich pathway.
In Saccharomyces cerevisiae, tryptophol is Aro80p’s transcription activator. Tryptophol activates the transcription factor Aro80p and, consequently, the expression of the ARO9 and ARO10 transaminase and decarboxylase genes, which results in a positive feedback loop.
The number of Batrachochytrium dendrobatidis cells grown for 5 days in TGhL medium(control) decreases when high concentration and density in CM(conditioned medium). (Figure 1A, 1B)
Comparison with the supernatant solution of a particular size of the molecule filtering showed that no disruption to growth of Batrachochytrium dendrobatidis was measured at 500Da and 1000Da. In other words, the growth inhibitor of Batrachochytrium dendrobatidis is less than 500Da. (Figure 1C)
This time, they treated the tryptophol concentrations differently from 10, 23, 50, 100, 250, and 500 uM, and significant degradation occurred from more than 100 uM. (Figure 2B)

Furthermore, the relationship between Batrachochytrium dendrobatidis growth and the production of tryptophol was observed with different numbers of inoculated spores in the early stages, confirming that they were growing at a constant concentration regardless of the initial concentration. (Figure 3, 4)

 In addition, additional tryptopol production based on the initial tryptopol treatment concentration was observed to be directly proportional called autostimulation, which means that the more existing it is, the newer it is. (Figure 5)
