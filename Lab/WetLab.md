# Wet Lab
## Design tools (drawing)
* [SBOLCanvas](https://pubs.acs.org/doi/10.1021/acssynbio.1c00096)
---

## Chitin detection
---

## AND gate, Violacein production
* AND gate example
1. [based on TF factors](https://bmcgenomics.biomedcentral.com/articles/10.1186/1471-2164-11-S4-S16)

### Designs for Experiments: 3-1/3-2/3-3 

#### Experiment 3-3 Design
![AND gate for violacein synthesis](https://user-images.githubusercontent.com/14289498/131956796-8ce9716c-a63b-43da-aae1-c37b9866843e.png)
* signal 1: light ([`pDawn`](https://www.sciencedirect.com/science/article/pii/S0022283612000113)) induces `vioAB` genes
>various optogenetic promoters can be considered:
1. [2017 Heidelberg team](http://2017.igem.org/Team:Heidelberg/Optogenetics) 
2. [single component light-sensing](https://academic.oup.com/nar/article/48/6/e33/5716458)

* signal 2: any signal (IPTG/arabinose/aTc/fungi sensing/fungi QS molecules) induces `vioCDE` genes (or vice versa)
* output: only if signal 1 & 2 are true, `violacein` will be synthesized

<img src=https://2019.igem.org/wiki/images/4/42/T--Guelph--VioPathwayDevin.png width=500 height=300>

| signal 1 | signal 2 | output |
| ---- | ---- | ---- |
|1|1|1|
|1|0|0|
|0|1|0|
|0|0|0|

* To do
1. signal receiver part1 - [`pDawn`](https://www.sciencedirect.com/science/article/pii/S0022283612000113)+`vioAB`
2. signal receiver part2 - `pLac`+ `vioCDE`
3. insulator - `pCon`+`LacI`
4. Design part 1,2,3 at Benchling
5. Combine parts into a single vector at Benchling
6. Order required primers/oligos/synthetic DNA/Build/test vectors

#### Experiment 3-1 Design
* 병꼴균 탐지 - tryptophan 농도 (QS) - E. coli trpR/trpL sensor/promoter
> [trpL](http://parts.igem.org/Part:BBa_K360124)
* To do
1. Sensor construction at Benchling - `trpL` + `vioABCDE`/`vioCDE`
2. Order synthetic DNA
3. Build/Test vector

#### Experiment 3-4
* violacein 농도측정 - [iGEM part registry](http://parts.igem.org/Part:BBa_K274002:Experience)
![TLC](http://parts.igem.org/wiki/images/7/71/Tlc_%28tinal%29.jpg)
* 필요한 최소농도는?
* 빛(신호1)과 신호2의 세기에 따라 조절가능한 프로모터를 찾아볼것.
* 프로모터조합으로 생합성되는 violacein의 양을 측정하고 최적의 농도를 만드는 프로모터조합확인
* 참고 - [promoter tuning - 2011 iGEM 북경대](http://2011.igem.org/Team:Peking_R/Project/Application/VIO)

#### Experiment 3-5 문헌조사 및 요약정리/제안

#### Experiment 3-6 design
* MazE (toxin), MazF (anti-toxin)을 이용
* AND gate (3-3) output (MazE) overexpression (일종의 inverter로 출력신호가 참인경우 궁긍적으로 kill)

| signal 1 | signal 2 | output (kill) |
| ---- | ---- | ---- |
|1|1|0|
|1|0|1|
|0|1|1|
|0|0|1|

---
## Adhesion
---

