
<!---
![Digital_VLSI_SoC_Design_ _Planning_(RTL2GDSII_Flow)1](https://github.com/sar123-del/soc-design-and-planning-nasscom-vsd/assets/63997454/92eb860b-7a88-4c6f-8143-ad3e09fd9c5b)
![Digital_VLSI_SoC_Design_ _Planning_(RTL2GDSII_Flow) (1)1](https://github.com/sar123-del/soc-design-and-planning-nasscom-vsd/assets/63997454/4285c5e4-d5df-43e4-b460-ead45ff67f9b)
-->
![Image](https://github.com/user-attachments/assets/31821cc8-a965-4d25-ac1c-98dfbc6ef849)
# Digital VLSI SoC Design and Planning
## Section 1 - Inception of open-source EDA, OpenLANE and Sky130 PDK (26/01/2025 )



#### Package

* In any embedded board, the component we typically recognize as the "chip" is actually the package—a protective casing designed to shield the actual chip. The actual manufactured chip resides at the center of this package. The package serves as a bridge, connecting the chip to external circuits using the wire bond method, which involves simple wired connections.
  ![Image](https://github.com/user-attachments/assets/63da06ea-46bc-4815-bfbc-5f75fd4fda2f)
  #### Chip

 * Inside the chip, all signals entering or leaving are routed through pads. These pads surround the core, which houses all the digital logic of the chip. Together, the core    and pads form the die, the fundamental manufacturing unit of a semiconductor chip.
 ![Image](https://github.com/user-attachments/assets/61ba8d2a-273b-4d04-9d6c-b4a5232efa2b)

* **FOUNDRY**
Semiconductor chips are manufactured in a foundry, a specialized facility for chip production. Foundry IPs (Intellectual Properties) are designs tailored to a specific foundry and require a high level of expertise to develop. On the other hand, reusable digital logic blocks are referred to as **macros**.
![Image](https://github.com/user-attachments/assets/2a8cc585-254e-49fb-ad5b-3622df2cfaf0)
#### Open-source Implementation

*Open-source ASIC design requires the following enablers:

1.RTL Designs
2.EDA Tools
3.PDK Data

Initially, IC design and fabrication were tightly coupled and handled by a few companies like TI and Intel.

In 1979, Lynn Conway and Carver Mead introduced the idea of separating design from fabrication using λ-based design rules, leading to the first VLSI textbook, Introduction to VLSI Systems, and the birth of VLSI education.

This separation gave rise to fabless companies (design-only) and pure-play fabs (fabrication-only).

Designers and fabs began interacting through Process Design Kits (PDKs), which include device models, technology data, design rules, libraries, etc.

PDKs, distributed under NDAs, were inaccessible to the public until Google partnered with SkyWater Technology to open-source the 130nm PDK. This historic release occurred on June 30, 2020.
![Image](https://github.com/user-attachments/assets/6f6f7878-f877-4998-bb46-66d053f281e1)
#### OpenLANE Open-source ASIC Design Implementation Flow
* The primary goal of the ASIC design flow is to transform a design from the RTL (Register Transfer Level) stage to the GDSII format, which represents the final layout used for chip fabrication.
  ![Image](https://github.com/user-attachments/assets/52c8f912-dbc6-41d3-915a-67d3cde7b70d)
* Here are the steps to implement the ASIC design flow
![Image](https://github.com/user-attachments/assets/ac686517-a427-467d-bc87-13947b63ccb4)
![Image](https://github.com/user-attachments/assets/420c5ae1-6ed0-4fae-b700-bfabf4689152)
![Image](https://github.com/user-attachments/assets/74148927-20d1-4249-b84d-ef8648fff034)
![Image](https://github.com/user-attachments/assets/39cbf524-ded3-4469-a7d9-ad4d8f77e5e9)
![Image](https://github.com/user-attachments/assets/65df2ceb-61e6-41fc-8b74-0fa0833a4154)
![Image](https://github.com/user-attachments/assets/c6b58f52-cb09-426f-8368-c02928824f47)
![Image](https://github.com/user-attachments/assets/efa25de1-165b-42d9-aede-03a077fe2b59)

**Section 1 tasks:-** 
1. Run 'picorv32a' design synthesis using OpenLANE flow and generate necessary outputs.
2. Calculate the flop ratio.

```math
Flop\ Ratio = \frac{Number\ of\ D\ Flip\ Flops}{Total\ Number\ of\ Cells}
```
```math
Percentage\ of\ DFF's = Flop\ Ratio * 100
```

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


