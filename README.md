
<!---
![Digital_VLSI_SoC_Design_ _Planning_(RTL2GDSII_Flow)1](https://github.com/sar123-del/soc-design-and-planning-nasscom-vsd/assets/63997454/92eb860b-7a88-4c6f-8143-ad3e09fd9c5b)
![Digital_VLSI_SoC_Design_ _Planning_(RTL2GDSII_Flow) (1)1](https://github.com/sar123-del/soc-design-and-planning-nasscom-vsd/assets/63997454/4285c5e4-d5df-43e4-b460-ead45ff67f9b)
-->
![Image](https://github.com/user-attachments/assets/8d6a6a03-c821-4f18-9ed0-b326b01e6fb5)
# Digital VLSI SoC Design and Planning
## Section 1 - Inception of open-source EDA, OpenLANE and Sky130 PDK (26/01/2025 )



#### Package

* In any embedded board, the component we typically recognize as the "chip" is actually the package—a protective casing designed to shield the actual chip. The actual manufactured chip resides at the center of this package. The package serves as a bridge, connecting the chip to external circuits using the wire bond method, which involves simple wired connections.
  ![Image](https://github.com/user-attachments/assets/cbae27d0-03ab-4f2e-a779-126775787b1f)
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









