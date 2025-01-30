
<!---
![Digital_VLSI_SoC_Design_ _Planning_(RTL2GDSII_Flow)1](https://github.com/sar123-del/soc-design-and-planning-nasscom-vsd/assets/63997454/92eb860b-7a88-4c6f-8143-ad3e09fd9c5b)
![Digital_VLSI_SoC_Design_ _Planning_(RTL2GDSII_Flow) (1)1](https://github.com/sar123-del/soc-design-and-planning-nasscom-vsd/assets/63997454/4285c5e4-d5df-43e4-b460-ead45ff67f9b)
-->
![Image](https://github.com/user-attachments/assets/31821cc8-a965-4d25-ac1c-98dfbc6ef849)
# Digital VLSI SoC Design and Planning
## DAY-1 - Inception of open-source EDA, OpenLANE and Sky130 PDK 
**LABS**
1. Run 'picorv32a' design synthesis 
2. Calculate the flop ratio.

```math
Flop\ Ratio = \frac{Number\ of\ D\ Flip\ Flops}{Total\ Number\ of\ Cells}
```
```math
Percentage\ of\ DFF's = Flop\ Ratio * 100
```
3. Comand to know what is inside a particular folder
4. Command to see what is inside a file

1.Commands to run the OpenLANE flow and perform synthesis

```bash
# Change directory to openlane flow directory
cd Desktop/work/tools/openlane_working_dir/openlane

# Lab password
docker
```
```tcl
#  We have entered the OpenLANE flow and we can run the OpenLANE flow in the Interactive mode using the following command
./flow.tcl -interactive

#  The required packages for proper functionality of the OpenLANE flow
package require openlane 0.9

# Now the OpenLANE flow is ready and initially we have to prepare the design creating some necessary files and directories for running a specific design 'picorv32a'
prep -design picorv32a

# Now the design is prepared and ready, we can run synthesis using following command
run_synthesis
```

Screenshots -
![Image](https://github.com/user-attachments/assets/2690e2b0-8ac6-49a7-a2de-69f55cccf866)
![Image](https://github.com/user-attachments/assets/ac32a9f6-edb5-4e37-a99d-433d27f731dd)
![Image](https://github.com/user-attachments/assets/71a2472b-68ff-470a-a548-441308b96a7b)
#### 2. Calculate the flop ratio.

Screenshots of synthesis statistics report file
![Image](https://github.com/user-attachments/assets/1bc70eb3-60ee-49d4-9608-591d547080bb)

Calculation of Flop Ratio and DFF % from synthesis statistics report file

```math
Flop\ Ratio = \frac{1613}{14876} = 0.108429685
```
```math
Percentage\ of\ DFF's = 0.108429685 * 100 = 10.84296854\ \%
```
#### 3. Comand to know what is inside a particular folder
```bash
# To see what is inside a folder
  ls -ltr
```
 To see what is in the runs folder
![Image](https://github.com/user-attachments/assets/a3d4b332-47c4-46e8-bce5-0a3a714f0507)
#### 4. Comand to see what is inside a particular file
```bash
# To see what is inside a file
  ls -ltr
```

To see what is inside config.tcl
![Image](https://github.com/user-attachments/assets/5ae00fbc-df7c-4c7a-b336-481193401fc2)
![Image](https://github.com/user-attachments/assets/2dc10ee1-51c7-4d93-ab63-498426d5f475)

## Theory
Package
The chip we see on a board is actually its package, not the real chip. The package is like a cover that protects the tiny chip inside.
The real chip is placed at the center of the package. It is connected to the package using very thin wires. This is called wire bonding.
So, the package keeps the chip safe and helps it connect to other parts of the board.
![Image](https://github.com/user-attachments/assets/f7f23daa-2a58-4890-831b-e77276aec0a4)

Chip
Inside the chip, signals from the outside world enter and exit through small points called pads.
The area inside the pads is called the core, where all the important digital work happens.
Together, the core and pads form the die, which is the main part of a semiconductor chip.
![Image](https://github.com/user-attachments/assets/a4063d5e-5716-4a92-b027-35d644236ab0)
Foundry

A foundry is a place where semiconductor chips are made.
Foundry IPs are special designs made for a specific foundry. Creating them needs a lot of knowledge and skill.
Repeatable digital logic blocks inside a chip are called macros.
![Image](https://github.com/user-attachments/assets/695c0fc5-ce24-4a3a-ab59-67f3a93c6c40)
OpenLANE - Open-source ASIC Design Flow
The goal of the ASIC Design Flow is to turn a design from RTL (Register Transfer Level) into GDSII, the final format needed to make the chip.
Some of the main steps are-
![Image](https://github.com/user-attachments/assets/761f5d34-0dfe-4eec-9a5f-3733f7805787)


**DAY-2  Good floorplan vs bad floorplan and introduction to library cells**
**LABS**
1. Run 'picorv32a' design floorplan 
2. Calculate the die area in microns
3. Exploring floorplan using magic tool
4. Run placement in openlane
5. Exploring placement using magic tool

```math
Area\ of\ die\ in\ microns = Die\ width\ in\ microns * Die\ height\ in\ microns
```


   ### 1.Commands to run 'picorv32a' design floorplan
   Once we are in the openlane flow and successfully run synthesis
   Run the following command

```bash
# To run floorplan
  run_floorplan
```
![Image](https://github.com/user-attachments/assets/360ee5f1-c75c-4d00-b10c-d1de8a3a769b)
![Image](https://github.com/user-attachments/assets/975822bc-c9af-4a13-a0fd-2ad794ed3b69)  

### 2. Calculate the die area in microns
   Screenshot of contents of floorplan.def
   ![Image](https://github.com/user-attachments/assets/cd177bec-b4e8-42ab-9775-efcf18235844)
   
   
```math
1000\ Unit\ Distance = 1\ Micron
```
```math
Die\ width\ in\ unit\ distance = 660685  = 660685
```
```math
Die\ height\ in\ unit\ distance = 671405 = 671405
```
```math
Distance\ in\ microns = \frac{Value\ in\ Unit\ Distance}{1000}
```
```math
Die\ width\ in\ microns = \frac{660685}{1000} = 660.685\ Microns
```
```math
Die\ height\ in\ microns = \frac{671405}{1000} = 671.405\ Microns
```
```math
Area\ of\ die\ in\ microns = 660.685 * 671.405 = 443587.212425\ Square\ Microns
```
#### 3. Exploring floorplan using magic

Commands, but use it in another teminal

```bash
# Change directory to path containing generated floorplan def
/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/28-01_11-24/results/floorplan

# Command to load the floorplan def in magic tool
magic -T/home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp//merged.lef def read picorv32a.floorplan.def &
```
After entering this command .It would look like this
[Image](https://github.com/user-attachments/assets/db688cf4-e4d7-4b15-8fd0-cdbabf52f3b4)

Images of verticle metal layer
![Image](https://github.com/user-attachments/assets/08e8a54d-4ab7-41b7-9d0a-da15f30c9bf2)

Images of horizontal meatl layer
![Image](https://github.com/user-attachments/assets/4ae4793d-d08c-4659-8ff9-51b45bc335f6)

We can use what command to see what is that particular object
```bash
  what
```
   





