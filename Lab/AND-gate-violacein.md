## AND gate
* input1: blue light
* input2: IPTG
* output: prodeoxyviolacein
---
## Experimental procedure
1. order oligos (primers) for Gibson assembly (GA)
2. amplify plasmid DNAs in the lab - [`pDawn`](https://benchling.com/s/seq-Z2QcqMWAM62EOdHuCT2k) and [`pETM6-G6-vioABE-4A6-vioC-3A2-vioD`](https://benchling.com/s/seq-XvbNFlcd4VnKxoAddpuJ) at <b>Benchling</b> for preparation of template and backbone plasmid
3. prepare a linearized backbone plasmid - `pDawn` digested by `NdeI` and `NotI` restriction enzymes
4. amplify insert DNA fragments for GA by <b>PCR</b>
- vioA vioAB vioABE (actual final target is vioABE)
5. Gibson assembly (overlapping 40 bps)
- vioABE is too big (>5kb) to join by GA. The vioABE fragment was split into two pieces by middle overlapping region.
- three fragments (a linerized plasmid::`pDawn`, vioAB-partial and vioBE-partial::`PCR products`) will be joined by GA
6. Transform the gibson assembly products into <i>E. coli</i>
---
## Primers - [check primers](https://benchling.com/s/seq-XvbNFlcd4VnKxoAddpuJ) in `Benchling`
* Overhang size for GA: 40 bps
* Commerical GA kit for order - check two companies [Thermofisher Geneart](https://www.thermofisher.com/kr/ko/home/life-science/cloning/seamless-cloning-and-genetic-assembly/gibson-assembly.html) & [NEB](https://international.neb.com/applications/cloning-and-synthetic-biology/dna-assembly-and-cloning/gibson-assembly)
 
|Primer1/strand/poistion |	Primer2/strand/poistion	| Product Size |
|---|---|---|
|vioA-for	+ / 102 | vioA-rev	– / 1332 | 1370 |
|vioA-for	+ / 102 | vioABE-mid-rev	– / 3497 | 3488 |
|vioA-for	+ / 102 | vioAB-rev	– / 4646 | 4678 |
|vioA-for	+ / 102 | vioABE-rev – / 5527 | 5562 |
|vioABE-mid-for	+ / 3519 | vioABE-rev	– / 5527 | 2097 |

<img src="vio-procedure.jpeg" alt="experimental procedure">
---
