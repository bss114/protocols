# **Qiagen DNeasy PowerSoil Pro kit**

**Purpose:** This protocol is designed for the simple and rapid isolation of inhibitor-free, PCR-quality host cell and microbial DNA from a variety of sample sources. The original Qiagen protocol has been modified to lyse host cells using the Zymo ZR BashingBead lysis tube (2.0mm) to maintain consistency between other extraction methods tested. It is likely that lysis of gram positive microbes will be achieved more efficiently through using the PowerBead Pro tubes provided by Qiagen as they contain a variety of bead sizes to facilitate mechanical lysis. 
A [host-depletion step](DNA_extraction/enrichment_gDNA_NEBNext_Microbiome_DNA_Enrichment_Kit.md) is recommended prior to microbiome sequencing.

Human lung samples (40-60mg) were processed using this kit and subsequently characterized for 16S; results indicate that host-depletion is necessary.


If desired, this protocol can be performed in 96w format using the [QIAcube HT](https://github.com/BisanzLab/OHMC_Colaboratory/blob/main/Protocols/Extraction/1_PowerSoil_QiaCubeHT.md).

**Supplies:**  

| Item                                           | Vendor      | Catalog number|
|:-----------------------------------------------|:------------|:---------------|
| DNeasy PowerSoil Pro kit                       | Qiagen      | [Cat #47014](https://www.qiagen.com/us/products/discovery-and-translational-research/dna-rna-purification/dna-purification/microbial-dna/dneasy-powersoil-pro-kit?catno=47014)|  
| ZR BashingBead Lysis Tube (2.0mm)              | Zymo        | S6003-50       |
| DNase/RNase free water                         | Invitrogen  | 10977-015      |

**Equipment:**

- Omni Bead Ruptor 96
- Microcentrifuge
- Vortex
- P1000, P200 , P20, P2 pipettors

## **Protocol:**

Things to do before starting:

[ ] 1. Bring buffer CD2 out of fridge

[ ] 2. Make sure that there is no precipitate in CD3 (SDS). If there is, heat at 60C until dissolved


**A. Sample Disruption**

[ ] 1. Add two empty tubes, one at beginning and one at end, for extraction controls; treat as samples but without tissue added. Add ≤ 250 mg tissue sample to each ZR BashingBead™ Lysis tube (2mm).  

[ ] 2. Add 800 µl CD1 Buffer.

[ ] 3. Secure in a bead beater and run for 1 min at 30Hz.

[ ] 4. Centrifuge at 15,000 x g for 1 min.

[ ] 5. Recover supernatant from bead tubes and transfer to a new tube.  (Note: avoid the pelleted beads/particles and pipet slowly; approximate recovery is around 400-500ul)

**B. Sample Lysis**

[ ] 1. Add 200ul/tube CD2. Vortex 5sec to mix.

[ ] 2. Centrifuge tubes at 15,000g x 1min.

[ ] 3. Recover supernatant from tubes and transfer to a new tube. (Note: avoid the pellet and pipet slowly; approximate recovery is around 600ul)

[ ] 4. Add 600ul/tube CD3. Vortex 5sec to mix.

**C. Isolation of genomic DNA**

[ ] 1. Transfer up to 650 µl each lysate onto a spin column..

[ ] 2. Centrifuge at 15,000 x g for 1 min.

[ ] 3. Discard flow-through; load any remaining lysate to column.

[ ] 4. Centrifuge at 15,000g x 1min.

[ ] 5. Discard flow-through and collection tube; place each column in a new collection tube.

[ ] 6. Add 500ul EA; Centrifuge at 15,000g x 1min.

[ ] 7. Discard flow-through and re-use same collection tube.

[ ] 8. Add 500ul C5; Centrifuge at 15,000g x 1min.

[ ] 9. Discard flow-through and collection tube; place each column in a new collection tube.

[ ] 10. Centrifuge at 15,000g x 2min to remove any residual wash buffer.

[ ] 11. Place columns into elution tubes; Add 50ul DNase/RNase free water directly to the center of the membrane. Allow to sit for 5 min.

[ ] 12. Centrifuge at 15,000g x 1min to elute DNA.

[ ] 13. Assess DNA concentration by Qubit.


## **Sample information**

| Tube ID     | Sample type | Weight (mg) | Concentration (ng/ul) 
|------------ | ----------- | ----------- | --------------------
|             |             |             |                     
|             |             |             |                     
|             |             |             |                     
|             |             |             |                     
|             |             |             |                     
|             |             |             |                     
|             |             |             |                     
|             |             |             |                     
|             |             |             |                     
|             |             |             |                     
|             |             |             |                     
|             |             |             |                     
|             |             |             |                     



## **Kit Contents**

| Item                        | Storage | Lot number   
|-----------------------------|---------|--------------
| CD1 buffer                  | RT      |  
| CD2 buffer                  | 4C      |  
| CD3 buffer                  | RT      |  
| spin columns                | RT      |  
| EA buffer                   | RT      |  
| C5 buffer                   | RT      |  
