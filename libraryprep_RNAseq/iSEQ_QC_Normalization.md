# **iSeq QC and Normalization for RNASeq libraries**

**Purpose:** 
This protocol is adapted from the [Bisanz lab protocol](https://github.com/BisanzLab/OHMC_Colaboratory/blob/main/Protocols/MetagenomeSeq/iSeq_QC_normalization.md) for normalizing metagenomic sequencing libraries. 
There are many ways to normalize a sequencing library, but it can be difficult (and expensive) to perfectly normalize a pool. Because there are many variables (such as size) that can affect clustering efficiency, one of the best ways to normalize a sequencing library is to... sequence it. This can be accomplished using an iSeq 100 which utilizes the same chemistry and flow cell as the NovaSeq x, but at a significantly lower cost and read depth. Essentially, in this protocol, 1 µL of each library is combined in a tube and run on the iSeq. The resulting read counts per sample are then used to adjust the pooling volumes for sequencing on a NovaSeq/NextSeq run. 
Note: libraries that were prepared in parallel (multichannel) from at least 30ng of starting material should be relatively well normalized already and it is possible to directly proceed to this protocol. For samples that might have extreme differences in yield (this can be determined by looking at the tapestation QC), a pre-normalization to 1nM should be performed. This can be achieved using the OT-2 script [PlateDilution.py](https://github.com/BisanzLab/OHMC_Colaboratory/blob/main/OT2_scripts/TransferAndDilute/PlateDilution.py); the [transfer.csv sample sheet](https://github.com/BisanzLab/OHMC_Colaboratory/blob/main/OT2_scripts/TransferAndDilute/transfers.csv) will be required.

## **Step 1: Prepare QC pool:**

Things to do before starting:

- [ ] 1. Remove Ampure beads to room temp for at least 15 min.
- [ ] 2. Prepare 80% ethanol.

**1.1 Consumables**

| Item                                   | Vendor      | Catalog number|
|:---------------------------------------|:------------|:---------------|
| Strip tubes                            | VWR         | 76468-978      |
| Qubit assay tubes                      | Thermo      | Q32856         |
| Qubit dsDNA HS assay kit               | Thermo      | Q32854         |
| D1000 ScreenTape                       | Agilent     | 5067-5582      |
| D1000 sample buffer                    | Agilent     | 5067-5602      |
| Illumina RSB                           |
| PhiX                                   | Illumina    | 15017666       |
| AmpureXP                               | Agilent     | A63881         |
| LoBind microcentrifuge tubes           | Eppendorf   |
| Ethanol                                |
| Nuclease-free water                    |

**1.2 Equipment:**

- Microcentrifuge
- Vortex
- P1000, P200 , P20, P2 pipettors and tips

**1.3 Procedure**

- [ ] Using a strip tube and careful pipetting, transfer 1 µL from each sample library into a tube. Alternatively: use the [OT2 BlindPool.py script](https://github.com/BisanzLab/OHMC_Colaboratory/blob/main/OT2_scripts/BlindPool/BlindPool.py) if you are working from libraries in 96w plates.
**You can also use the 1nM dilution plates for this step if they have been prepared.**
- [ ] Combine the individual wells of the strip tube into a single lo-bind Eppendorf tube.
- [ ] It is recommended to perform an Ampure bead clean up to remove any residual primer dimers from library prep.
  - [ ] Mix 100ul pooled library with 100ul beads, mix well by pipetting 20X. Incubate at room temp 5 minutes.
  - [ ] Capture on magnet 2 min; avoiding beads, carefully remove unbound material and discard. 
  - [ ] Wash with 200ul freshly made 80% ethanol. Do a quick spin to collect any liquid droplets and remove residual ethanol with a 10ul pipette tip while on magnet. 
  - [ ] Repeat wash.
  - [ ] Air dry 5 min, do not overdry! 
  - [ ] Resuspend beads in 25ul nuclease-free water, incubate at room temp 5 min. 
  - [ ] Capture on magnet 2 min, eluate contains cleaned up library. Keep this on ice.

- [ ] Measure concentration of pool using Qubit dsDNA kit:_____
- [ ] Mix 3 µL tapestation sample buffer with 1 µL of pooled library
- [ ] Run sample on tapestation. Integrate the region from 200 to 400 bp and record region molarity:  ______pM
- [ ] Record average insert size from tapestation: ______bp and use to calculate molarity from Qubit: ______pM
- [ ] Cross reference the reported sample concentration from the Qubit against the sample concentration reported. If these values are not within 20% of each other, proceed to use qPCR to measure library concentration. 
- [ ] Dilute library to 1 nM in RSB
- [ ] Obtain a 1 nM aliquot of PhiX (Note: Illumina supplies it at 10nM and diluted aliquots are stored in the lab freezer)
- [ ] RNASeq libraries cluster very well, thus a lower concentration of 75pM is used in combination with 7% phiX to add nucleotide diversity. Illumina recommends preparing the 1nM library with phiX first, then diluting to the loading concentration:
  - [ ] In a lo-bind tube, combine 15 µL of the 1nM library with 2.1 µL of the 1 nM PhiX (7% spikein). 
  - [ ] Add 182.9ul RSB to make the final concentration 75pM.

## **Step 2: Sequence pool:**

**2.1 Consumables**

| Item                                   | Vendor      | Catalog number|
|:---------------------------------------|:------------|:---------------|
| Illumina iSeq 300 cycle kit            | Illumina    | 20031371       |

**2.2 Equipment:**

- iSEQ100 sequencer

Things to do before starting:

- [ ] Thaw iSeq Cartridge the night before: At room temperature, cartridge needs to to be thawed for between 9-18h. This corresponds to starting to thaw at 5pm and starting the sequencing run before 11am the next day. See discussion [here](https://knowledge.illumina.com/instrumentation/iseq-100/instrumentation-iseq-100-reference_material-list/000002118).
  - [ ] Remove the cartridge from the box, but leave it in the tinfoil bag. 
  - [ ] Place the cartridge on top of the cardboard box so that air circulates on all sides. 
- [ ] Bring flow cell out from 4C and leave at room temperature for at least 15 minutes

**2.3 Procedure:**
- [ ] Pierce the appropriate well of the sequencing cartridge with a clean pipette tip.
- [ ] Pipette 20 µL of the library/phix into the bottom of the well- position the tip so that you touch the bottom and then pull up slightly.
- [ ] Follow the instructions on the iSeq to start run. **Note: the iSeq software makes uploading custom sample sheets difficult; the proper sample sheet can be uploaded after the run is done; however, we need to make sure it captures 151x10x10x151 bases, and this will ensure it does.
  - [ ] When setting up the run, select the library prep kit as "Illumina stranded mRNA Prep", and the index adapter kit as "Illumina DNA-RNA UD Indexes Set A Tagmentation (v3)". 
  - [ ] Put any sample name under the first row of the sample sheet, and select well position "A1". 
  - [ ] Monitor instrument for next 15 minutes as it does prerun checks. If any issues arise, immediately contact Illumina customer support.


## **Step 3: Analyze data**

- [ ] In [basespace](https://login.illumina.com/platform-services-manager/?rURL=https://basespace.illumina.com&clientId=basespace&clientVars=aHR0cHM6Ly9iYXNlc3BhY2UuaWxsdW1pbmEuY29tL2Rhc2hib2FyZA&redirectMethod=GET#/), find your run. Click the hourglass under the summary tab, and click requeue, then sample sheet. 
- [ ] Under the data section, copy and paste complete sample sheet that was exported from the "iSeq_samplesheet" tab of the RNASeq_RunTemplate.xlsx file(ADD_LINK).
- [ ] Click requeue (analysis will take approximately 10 minutes depending on system load)
- [ ] In basespace, on the indexing QC tab of the run, copy the Per Index results into the "iSeq_normalization" tab of the RNASeq_RunTemplate.xlsx file. Review for consistency and to make sure no samples dropped out.
- [ ] Adjust the minimum pipette volume to ensure that most samples can be pooled within the available range of 0.5 to 20 µL.
- [ ] Export the Loadings.csv tab to proceed to final loading.
- [ ] Remove any samples which are not required.

## **Step 4: Repool samples and clean up**

- [ ] On the Post PCR OT2, use the [Pool Equimolar libraries from CSV program](https://github.com/BisanzLab/OHMC_Colaboratory/blob/main/OT2_scripts/PoolLibs/PoolLibs.py) to pool samples uploading your loadings.csv file and following the instructions.
- [ ] Repeat the 1:1 Ampure bead clean up procedure as described in step 1.3.
- [ ] Store final library at -20˚C until QC/sequencing.

## **Step 5: Final QC**

- [ ] Run library on Tape Station to confirm final size distribution and concentration, integrate the region 200-400bp: _______pM
- [ ] Run on Qubit to get concentration: _____ng/ul
- [ ] Record average insert size from tapestation: ______bp and use to calculate molarity from Qubit: ______pM
- [ ] Dilute library to 1nM and store at -20C until running on NextSeq/NovaSeq.
