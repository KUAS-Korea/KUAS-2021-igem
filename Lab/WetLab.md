# Wet Lab

## Violacein AND gate
The original design for the AND gate was to use an igem part T7 polymerase AND gate (BBa_K568004). However this part along with the Vio operon would result a part that is almost 15kb. Our PI noted us of the difficulties of transforming a part of such size an suggested a different AND gate design. His AND gate design was a split vio operon which had few vio genes under control of one promoter and the rest of the genes under the control of a different promoter. Thus, the full violacein pathway is constituted only when both of the promoters are activated. 
As described in the Description page, we decided to use light as one of the inputs for violacein production. For the second input, for simplification and reliability, the IPTG inducible lac promoter was used. 
Gibson assembly was used to connect two addgene plasmids: 

[Violacein `addgene' vector](https://www.addgene.org/73440/)

[Violacein `addgene' vector](https://www.addgene.org/43796/)
 
The final construct is as follows. 
![image](https://user-images.githubusercontent.com/87188354/137825930-f057ebca-0942-45a7-8f6b-6c5e437be36e.png)
Though it would be the best to include the full violacein pathway, the gibson process would be a lot more complicated. Thus, our PI suggested a proof of concept plasmid which has vioA under the control of pDawn system and vioB and vioE under the control of the IPTG inducible system. 


Due to time constraints and the fact that there were no experienced wet lab member in our team, our wet lab instructors Sera Kang and Xiaoyue conducted the assembly and transformation proccess. 

The protocols for the experiments can be seen below.

## Protocol
### 1. Prepare pDawn vector with enzyme cut for Gibson Assembly(GA)
- plasmid enzyme cut -> check gel -> inactivation -> clean up
1. Mix all below chemical substances to make total 50㎕ solution.

Total         | 50㎕ 
--------------|-------
pDawn         | 40㎕   
NdeI          | 1㎕    
NotI-HF       | 1㎕    
Cutsmart(10x) | 5㎕    
DW            | 3㎕ 


2. Let mixture in 37℃ for 50 minutes.

4. Check gel with uncut.

6. Put mixture in 65℃ for 20 minutes.

8. Clean up
- 1-1, 1-3 -> 50㎕ elution
- 2-1, 2-2, 2-3 -> 100㎕ elution

### 2. Prepare insert sequence "vio ABE" PCR for GA
1. Mix all below chemical substances

Total            | 25㎕ 
--------------   | ----
template(1/10)   | 2㎕
reaction buffer  | 5㎕ 
dNTP             | 2㎕ 
Primer -Forward  | 1㎕ 
Primer -Reverse  | 1㎕
Q5 polymerase    | 0.2㎕ 
DW               | 13.8㎕ 

* plasmid: pETM6-G6-vioABE-4A6-vioC-3A2-vioD
* primer

(1) vioA(1.4kb) : vioA_F(55℃), vioA_R(60℃)

(2) vioAB(4.7kb) : vioA_F(55℃), vioAB_R(53℃)

(3) vioAB(vioABE)(3.5kb) : vioA_F(55℃), vioABE_mid_R(56℃)

(4) vioBE(vioABE)(2.1kb) : vioABE_mid_F(56℃), vioABE_R(54℃)

(5) vioABE(5.6kb) : vioA_F(55℃), vioABE_R(54℃)

2. Turn PCR.
![image](https://user-images.githubusercontent.com/79410957/138125700-d86c41f4-21d6-4c67-b16d-1c0c3b51d61d.png)

(1) 56℃/58℃/60℃ in 1 minute.

(2), (5) 53℃/55℃/57℃ in 3 minutes.

(3) 54℃/56℃/58℃ in 2 minutes.

(4) 53℃/55℃/57℃ in 1 and a half minute.

(1), (4) 53℃/56℃/60℃ in 1 and a half minute.
 => Mix and put DPN 1.5㎕ each of them.

(2), (3), (5) 53℃/56℃/58℃ in 3 minutes.
 => (5) showed 2 bands, so we redo with a little higher temperature.

(5) again 58℃/60℃/62℃ in 3 minutes.
 => It showed 2 bands again, and we figured out that vioA_F has overlapped sequence so that it resulted in 2 bands.
 
![image](https://user-images.githubusercontent.com/79410957/138127890-c71e1eeb-b9ee-48e0-94e6-8e22556ea161.png)
![image](https://user-images.githubusercontent.com/79410957/138127912-a6787096-09cf-43ad-81f4-1cce91052a83.png)

### 3. Combine vector and insert in order to do GA
1. vioABE

pDawn(vector) | vioAB(vioABE) | vioBE(vioABE)
------------- |-----------    | -------------
7.1 kb        | 3.5 kb        | 2.1kb
21 ng/㎕      | 47 ng/㎕      | 65ng/㎕
0.0045 pmol   | 0.02 pmol     | 0.047 pmol

(1) Mix vioAB and vioBE with 2 : 1 ratio.

(2)

  -   | 1:2 | 1:3 
------|-----|-----
vector| 5\1 | 5\1.5

(3-1) 

Total           | 20㎕
-----           |------
pDawn           | 5㎕
insert          | 1㎕
HiFi master mix | 10㎕
DW              | 4㎕

(3-2) If insert is 0.03 to 0.2 pmol, follow below table. (This can make total amount in a half)

Total           | 20㎕
------          |------
pDawn           | 5㎕
insert          | 1.5㎕
HiFi master mix | 10㎕
DW              | 3.5㎕




### 4. vio ABE chemical transformation
 
1. competent cell 50ul + plasmid(pDawn_vio ABE) 2ul
2. ice 30m incubation
3. 43℃ 40s incubation
4. ice 5m incubation
5. Mix LB 1ml
6. 37℃ 1h incubation
7. centrifuge 13,500rpm 1m
8. supernatant 800ul 버리고, 나머지 resuspension
9. 빛O/X 조건으로 나눠서 100ul씩 LB/KAN 배지에 spreading
10. 37℃ overnight incubation

