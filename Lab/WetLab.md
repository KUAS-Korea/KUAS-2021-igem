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












----------------------------------------------


## Protocol



### 1. Prepare pDawn vector with enzyme cut for Gibson Assembly(GA)
- plasmid enzyme cut -> check gel -> inactivation -> clean up


#### 1. Mix all below chemical substances to make total 50 ㎕ solution.

Total         | 50 ㎕ 
--------------|-------
pDawn         | 40 ㎕   
NdeI          | 1 ㎕    
NotI-HF       | 1 ㎕    
Cutsmart(10x) | 5 ㎕    
DW            | 3 ㎕ 


#### 2. Let mixture in 37℃ for 50 minutes.

#### 3. Check gel with uncut.

#### 4. Put mixture in 65℃ for 20 minutes.

#### 5. Clean up
- 1-1, 1-3 -> 50 ㎕ elution
- 2-1, 2-2, 2-3 -> 100 ㎕ elution











--------------------------------------------------



### 2. Prepare insert sequence "vio ABE" PCR for GA


#### 1. Mix all below chemical substances

Total            | 25 ㎕ 
--------------   | ----
template(1/10)   | 2 ㎕
reaction buffer  | 5 ㎕ 
dNTP             | 2 ㎕ 
Primer -Forward  | 1 ㎕ 
Primer -Reverse  | 1 ㎕
Q5 polymerase    | 0.2 ㎕ 
DW               | 13.8 ㎕ 

* plasmid: pETM6-G6-vioABE-4A6-vioC-3A2-vioD
* primer

(1) vioA(1.4 kb) : vioA_F(55℃), vioA_R(60℃)

(2) vioAB(4.7 kb) : vioA_F(55℃), vioAB_R(53℃)

(3) vioAB(vioABE)(3.5 kb) : vioA_F(55℃), vioABE_mid_R(56℃)

(4) vioBE(vioABE)(2.1 kb) : vioABE_mid_F(56℃), vioABE_R(54℃)

(5) vioABE(5.6 kb) : vioA_F(55℃), vioABE_R(54℃)



#### 2. Turn PCR.
![image](https://user-images.githubusercontent.com/79410957/138125700-d86c41f4-21d6-4c67-b16d-1c0c3b51d61d.png)

 - (1) 56℃ / 58℃ / 60℃ in 1 minute.

 - (2), (5) 53℃ / 55℃ / 57℃ in 3 minutes.

 - (3) 54℃ / 56℃ / 58℃ in 2 minutes.
P
 - (4) 53℃ / 55℃ / 57℃ in 1 and a half minute.

 - (1), (4) 53℃ / 56℃ / 60℃ in 1 and a half minute.
 
 => Mix and put DPN 1.5 ㎕ each of them.

 - (2), (3), (5) 53℃ / 56℃ / 58℃ in 3 minutes.
 
 => (5) showed 2 bands, so we redo with a little higher temperature.

 - (5) again 58℃ / 60℃ / 62℃ in 3 minutes.

 => It showed 2 bands again, and we figured out that vioA_F has overlapped sequence so that it resulted in 2 bands.
 
![image](https://user-images.githubusercontent.com/79410957/138127890-c71e1eeb-b9ee-48e0-94e6-8e22556ea161.png)

![image](https://user-images.githubusercontent.com/79410957/138127912-a6787096-09cf-43ad-81f4-1cce91052a83.png)











------------------------------------------------------




### 3. Combine vector and insert in order to do GA



#### 1. vioABE

pDawn(vector) | vioAB(vioABE) | vioBE(vioABE)
------------- |-----------    | -------------
7.1 kb        | 3.5 kb        | 2.1 kb
21 ng/㎕      | 47 ng/㎕      | 65 ng/㎕
0.0045 pmol   | 0.02 pmol     | 0.047 pmol

(1) Mix vioAB and vioBE with 2 : 1 ratio.

(2)

  \   | 1:2 | 1:3 
------|-----|-----
vector| 5\1 | 5\1.5

(3-1) 

Total           | 20 ㎕
-----           |------
pDawn           | 5 ㎕
insert          | 1 ㎕
HiFi master mix | 10 ㎕
DW              | 4 ㎕

(3-2) If insert is 0.03 to 0.2 pmol, follow below table. (This can make total amount in a half)

Total           | 20 ㎕
------          |------
pDawn           | 5 ㎕
insert          | 1.5 ㎕
HiFi master mix | 10 ㎕
DW              | 3.5 ㎕






#### 2. vioA

pDawn(vector) | vioA(insert) 
------------- |-----------    
7.1 kb        | 1.4 kb       
21 ng/㎕      | 54 ng/㎕      
0.0045 pmol   | 0.058 pmol    


(1)

  \   | 1:2   | 1:3 
------|-------|-----
vector| 6.5\1 | 6.5\1.5


(2-1)

Total           | 20 ㎕
-----           |------
pDawn           | 6.5 ㎕
vioA            | 1 ㎕
HiFi master mix | 10 ㎕
DW              | 2.5 ㎕

(2-2) 

Total           | 20 ㎕
------          |------
pDawn           | 6.5 ㎕
vioA            | 1.5 ㎕
HiFi master mix | 10 ㎕
DW              | 2 ㎕






#### 3. vioAB

pDawn(vector) | vioAB(insert) 
------------- |-----------    
7.1 kb        | 4.7 kb       
21 ng/㎕      | 30 ng/㎕     
0.0045 pmol   | 0.0097 pmol  

(1)

  \   | 1:2   | 1:3 
------|-------|-----
vector| 4\4   | 4\6


(2-1)

Total           | 20 ㎕
-----           |------
pDawn           | 4 ㎕
vioAB           | 4 ㎕
HiFi master mix | 10 ㎕
DW              | 2 ㎕

(2-2) 

Total           | 20 ㎕
------          |------
pDawn           | 4 ㎕
vioAB           | 6 ㎕
HiFi master mix | 10 ㎕



#### 4. control

Total | 10 ㎕
----- | -------
pDawn | 2.5 ㎕
DW    | 7.5 ㎕


#### 5. Put all in 50℃ for 15 minutes.

#### 6. transformation (DH5α)







---------------------------------------------------



### 4. vio ABE chemical transformation
 
#### 1. Mix competent cell 50 ㎕ and plasmid(pDawn_vio ABE) 2 ㎕.
#### 2. Incubate ice for 30 minutes.
#### 3. Incubate it in 43℃ for 40 seconds.
#### 4. Incubate it in ice for 5 minutes.
#### 5. Mix LB 1ml.
#### 6. Incubate in 37℃ for 1 hour.
#### 7. Centrifuge 13,500 rpm for 1 minute.
#### 8. Discard supernatant 800ul and resuspense leftover.
#### 9. Spread each of 100 ㎕ in LB/KAN plate.
#### 10. Separate each plate with light, and without light. So wrap with tinfoil plate without light.
#### 11. Incubate them in 37℃ through overnight.


## Results
 - We made vector and insert sequence that include vio genes into a single plasmid through Gibson assembly.
 - By inserting the plasmid into E. coli through transformation, it was possible to create a strain having vioABE that we wanted. This strain was observed to form colonies while growing them in medium.
 - In addition, the light was adjusted to confirm that it was sensitive to light conditions, and it was confirmed that the E. coli strain that gave the light grew finer but better. In addition, the light condition corresponding to the original AND gate was blue light, but failed to implement so the results are not remarkably succeed.
 - We can get some pictures after transformation that we gained the strain we wanted.

![10 12](https://user-images.githubusercontent.com/79410957/138143507-9a81f908-4393-42da-831d-8ba7b1afc561.jpg)

#### 12 Oct.  < immediately after transformation >

---------------------------------------------------------------------------------------------------------

![10 14 both](https://user-images.githubusercontent.com/79410957/138143456-fd19abd5-66fe-48e1-9d3f-e52060439c46.jpg)

#### 14 Oct.  < 2 days after transformation (both immediately after taking out of refrigerator) >

-----

![10 14 both open](https://user-images.githubusercontent.com/79410957/138144129-22d8e2e4-2226-442e-82ac-de5c3968c7ca.jpg)

#### 14 Oct.  < 2 days after transformation (both plates after removing tin foil from the plate grown without light) >

-----

![10 14 with light](https://user-images.githubusercontent.com/79410957/138143799-6384aa14-05c4-49af-ab76-1548bdee6c68.jpg)

#### 14 Oct.  < 2 days after transformation (plate grown with light) >

-----

![10 14 without light](https://user-images.githubusercontent.com/79410957/138144013-a1c68920-3b56-4c2e-b1dd-becc0f36171e.jpg)

#### 14 Oct.  < 2 days after transformation (plate grown without light) >



--------------------------------------------------------------------------------------------------------------


![10 18 both](https://user-images.githubusercontent.com/79410957/138144332-1665e426-2aad-47b9-ad47-c567952e39c3.jpg)

#### 18 Oct.  < 6 days after transformation (both immediately after taking out of refrigerator) >

-----

![10 18 both open](https://user-images.githubusercontent.com/79410957/138144433-20d6d046-8c09-4255-aaca-e7f6fecdc090.jpg)

#### 18 Oct.  < 6 days after transformation (both plates after removing tin foil from the plate grown without light) >

-----

![10 18 with light](https://user-images.githubusercontent.com/79410957/138144973-116bc7e2-0c24-42a4-b6bc-28093a0cd514.jpg)

#### 18 Oct.  < 6 days after transformation (plate grown with light) >

-----

![10 18 without light](https://user-images.githubusercontent.com/79410957/138144963-53af02d2-4c75-47c4-b48c-e0538dbf1feb.jpg)

#### 18 Oct.  < 6 days after transformation (plate grown without light) >










