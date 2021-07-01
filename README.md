# Advanced_Physical_Design_using_OpenLANE_Sky130_Workshop

Advanced Physical Design using OpenLANE/Sky130 Workshop is a five day workshop conducted by VSD-IAT.

![image](https://user-images.githubusercontent.com/60011091/119861437-04d26000-bf35-11eb-9515-85b05a1788d5.png)  

![image](https://user-images.githubusercontent.com/60011091/123736349-992a3c80-d8be-11eb-8b7d-0595b9aec4ab.png)

## Day wise Workshop topics 

- [Day-1 Inception of open-source EDA OpenLANE and Sky130 PDK](https://github.com/Badboy1307/Advanced_Physical_Design_using_OpenLANE_Sky130_Workshop/blob/main/README.md#Day-1-Inception-of-open-source-EDA-OpenLANE-and-Sky130-PDK)
  *  [How to talk to computers](https://github.com/Badboy1307/Advanced_Physical_Design_using_OpenLANE_Sky130_Workshop/blob/main/README.md#How-to-talk-to-computers)
  * 
  * 
  * 
  * 


- [Day-2 Understand importance of good floorplan vs bad floorplan and introduction to library cells](https://github.com/Badboy1307/Advanced_Physical_Design_using_OpenLANE_Sky130_Workshop/blob/main/README.md#Day-2-Understand-importance-of-good-floorplan-vs-bad-floorplan-and-introduction-to-library-cells)
  *  
  *  
  *
  *
  
 - [Day-3 Design and characterize one library cell using Magic Layout tool and ngspice](https://github.com/Badboy1307/Advanced_Physical_Design_using_OpenLANE_Sky130_Workshop/blob/main/README.md#Day-3-Design-and-characterize-one-library-cell-using-Magic-Layout-tool-and-ngspice)
  * 
  * 
  *

  
  - [Day-4 Pre-layout timing analysis and importance of good clock tree](https://github.com/Badboy1307/Advanced_Physical_Design_using_OpenLANE_Sky130_Workshop/blob/main/README.md#DAY-4-Pre-layout-timing-analysis-and-importance-of-good-clock-tree)
  * 
  * 
  *
  *
  
  - [Day-5 Final steps for RTL2GDS](https://github.com/Badboy1307/Advanced_Physical_Design_using_OpenLANE_Sky130_Workshop/blob/main/README.md#Day-5-Final-steps-for-RTL2GDS)
  * 
  * 

  
 
## Day-1 Inception of open-source EDA OpenLANE and Sky130 PDK

### How to talk to computers

#### Introduction to QFN-48 Package,chips,pads,core,die and IPs


![141352](https://user-images.githubusercontent.com/60011091/123891647-db16b980-d976-11eb-9b08-95791ae9a9e9.png)


Here we can see an Arduino board which you might have bought from the market and even worked on it. This a typical electronic circuit. But here the field we are talking about is  inside the circled part that is the chip.



![image](https://user-images.githubusercontent.com/60011091/123920622-c866a980-d9a3-11eb-9ca3-e74bbe9b3422.png)


This image is the block diagram of the above arduino board image and the circled part in the previous image is shown in this figure as a Processor/SOC. 



![image](https://user-images.githubusercontent.com/60011091/123920490-a1a87300-d9a3-11eb-9a1e-a7089e404348.png)




When we open up the  IC from Arduino Board we will be seeing as the above image. We will be calling this as a package and it's named as QFN 48 (Quad Flat No-leads)


The image shown below shows where our chip will be located and how it's connected to the package.



![image](https://user-images.githubusercontent.com/60011091/123919556-a9b3e300-d9a2-11eb-9af8-e7eded559c15.png)



![image](https://user-images.githubusercontent.com/60011091/123921098-4925a580-d9a4-11eb-9929-5c76c11ccbb8.png)

This image shows the inside part of the chip which has pads, cores and dies. Pad is an component through which signal can be sent inside the chip. From the marked parts we see core which in the middle of the chip where all our digital logic circuits sits and logic circuits can be any basic gates, MUX's or can be any different kind of logics. Die is the size of the entire chip.


![image](https://user-images.githubusercontent.com/60011091/123922385-9b1afb00-d9a5-11eb-9540-4dd87a3f2c13.png)


This image is the example or sample of RISCV inside a chip.

###### Foundry and Foundry IPs

![image](https://user-images.githubusercontent.com/60011091/123939500-cf96b300-d9b5-11eb-9522-e3c244ded386.png)

This image depicts which are the components present in the above image are foundry related IPs like dac adc0, adc1, pll and SRAM. 

A mobile phone for example depends on the foundry. Foundry is like a factory with alot of machines where chips are manufactured.Then sir had shared his experience on working in a foundry of IIT Bombay where he and his team worked in lithography domain. As VLSI engineers our job is to continuously communicate with foundry.


##### RISCV Introduction


Here we see about RISCV Instruction Set Architecture (ISA) which is a language of the computer and this is the way we are going to talk to a computer. 


![tempsnip](https://user-images.githubusercontent.com/60011091/124063611-dde5dd00-da50-11eb-9f73-01bc2fe89c14.jpg)


From the above image we want to pass this C program to a hardware of the above layout in a certain way or in a certain flow. This is done by  firstly compiling C in its assembly language program ie RISCV assembly language program then this assembly language is converted to machine language which is basically the binary 1s and 0s understood by the hardware of the computer.

The above image also shows the output in hexadecimal format which is converted to binary format and finally these bits gets executed in the above layout of the hardware and we receive the required output. 

There is another interface required between RISCV Architecture and the layout of the hardware ie hardware description language which can be Verilog or VHDL or System verilog. We are implementing RISCV Architecture using some RTL but here we take an example of picorv32 cpu core which takes  RISCV Architecture as specifications and implements in hardware description language and finally from the RTL to layout which is nothing but a standard PnR or a standard RTL to GDS fLow.


##### Software Applications to Hardware


![image](https://user-images.githubusercontent.com/60011091/123945643-ffe15000-d9bb-11eb-8d78-48cefe7ba5bf.png)

The above image shows the Apps or Application Softwares used in our PC. These apps run in the computer hardware shown in the below image.


![image](https://user-images.githubusercontent.com/60011091/123946253-9f9ede00-d9bc-11eb-88bc-de2c3e39308b.png)


![image](https://user-images.githubusercontent.com/60011091/124062338-3071ca00-da4e-11eb-990f-7f2a6a185534.png)


The above image shows the flow of Application Software running in Hardware of Computer using System Softwares which consists of OS, Compiler and Assembler.


#### SOC and OpenLane

##### SOC Design using OpenLane

This lecture was given by Mohamed Shalan who talked about OpenLane and its features.

Designing digital application specific integrated circuits (ASIC) require certain elements like RTL IP's (which is a hardware description model or functions), EDA tools and 
Process Design Kits (PDKS). The same is shown in the image given below.

![image](https://user-images.githubusercontent.com/60011091/123952883-3ae78180-d9c4-11eb-9966-17f0ab7be254.png)

Some of the best websites to acquire RTL Designs include:

librecores.org
opencores.org
github.com

EDA Software tools include Qflow, OpenROAD and OpenLane.


PDK is the interface between FAB and the designers. It includes collection of files used to model a fabrication process for EDA tools used to design an IC such as:

- Process Design Rules: DRC, LVS, PEX
- Device Models
- Digital Standard Libraries
- I/O Libraries


On June 30, 2020 Google on collaboration with skywater technology released the first open source pdk ie 130nm process skywater to the masses.

![image](https://user-images.githubusercontent.com/60011091/123956209-0c6ba580-d9c8-11eb-9718-c56332c98ba1.png)


The above image demonstrates various steps involved in EDA Tools


##### Simplified RTL to GDSII Flow



![image](https://user-images.githubusercontent.com/60011091/123957671-b3047600-d9c9-11eb-974e-dbd6a039eca3.png)
This images shows the Simplified flow from RTL design to GDSII 

###### Synthesis

-Conversion of RTL design to a circuit out of components from Standard cell library (SCL). We have a small sample code of always block as shown below:



           always @ (posedge clk)
             if(c) q<=a;
             else q<=b;
             
             
             
![Flow_Workspace](https://user-images.githubusercontent.com/60011091/123964569-2bbb0080-d9d1-11eb-89bb-4908d7a07f44.jpg)


Standard Cells have regular layout. Each has different views/models 

-Electrical, HDL, SPICE,
-Layout (Abstracted and Detailed) 


###### Floor and Power Planning 


Chip Floorplanning - Patitioning the chip die between different system blocks and placing the I/O pads

![image](https://user-images.githubusercontent.com/60011091/123965874-830da080-d9d2-11eb-8801-bf2c87292754.png)

The above image describes the Chip Floorplanning

Macro Floorplanning - We define the macro dimensions, pin locations and row definitions.

![image](https://user-images.githubusercontent.com/60011091/123966387-03340600-d9d3-11eb-8a03-494b72f72228.png)




Power Planning - Power network is constructed typically by multiple VDD and GND pins. the Power pins are all connected through power rings, vertical and  horizontal metal straps.

Power rings- Power ring is designed around the core. Power rings contains both VDD and VSS rings. After the ring is placed a power is designed such that power reaches all the cells easily.


![image](https://user-images.githubusercontent.com/60011091/123967363-ddf3c780-d9d3-11eb-8b41-6f8f8ce56882.png)

This diagram shows the power planning components.

These parallel structures reduce resistance. To address electromagnetism the power distribution network uses upper metal layers as they are thicker than lower metal layers


###### Placement 

Placing the cell on the floorplan rows aligned with sites. Connected cells should be placed close to each other to reduce the interconnect delay. It is done in two steps ie Global and Detailed Placement. In global placement , the approximate locations for cells is decided by placing cells in global bins. In detailed placement, cells are Placed without over lapping.

![image](https://user-images.githubusercontent.com/60011091/123968734-22339780-d9d5-11eb-89eb-0ab9dfc5aca2.png)



###### CTS (Clock Tree synthesis)

Creating a clock distribution network :

-Delivering clock to all sequential elements.
- With Minimum skew 
- In Good shape 
- A tree (H,X etc)

![image](https://user-images.githubusercontent.com/60011091/123969507-eb11b600-d9d5-11eb-9a0d-affcbfc897e5.png)

###### Routing 

Implements interconnects using available metal layers. Metal tracks form a routing grid. Routing uses Divide and Conquer method.

There are two types of Routing ie
-Global routing: Generates routing guides
-Detailed routing: Uses routing guides to implement actual wiring.



![image](https://user-images.githubusercontent.com/60011091/123969880-40e65e00-d9d6-11eb-82aa-b60741c7a9af.png)



###### Sign Off

-Physical Verifications 

-> Design Rules Checking (DRC)
-> Layout vs Scchematic (LVS)

-Timing Verification

-> Static Timing Analysis (STA)



##### OpenLane and Strive chipsets

Open source ASIC flow tools we need to worry about:

-Tools Qualification
-Tools Calibration
-Missing Tools


Efabless decided to create Open source ASIC implementation and flow called as OpenLane which has a public repo in github and is having Apache Version 2.0 license. This OpenLane started as Open-Source Tape Out experiment. 

Strive-  a family of open everything SOCs ie Open PDK, Open EDA and Open RTL.

![image](https://user-images.githubusercontent.com/60011091/123983062-32517400-d9e1-11eb-8e73-354059050687.png)


![image](https://user-images.githubusercontent.com/60011091/123989279-5f545580-d9e6-11eb-9bc1-ca51ea4ac738.png)


This image shows the features of Strive SOCS and its features.


The main goal of OpenLane was to produce a clean GDSII without human interventions. So that means, No LVS Violations! NO DRC Violations! or Timing Issues.

OpenLane was tuned for the Skywater 130nm Open PDK. OpenLane is containerized for making it functional out of the box and for building instruction and running natively. Can be used to harden macros and Chips.

It has two modes of operations ie:

-Autonomous -> It is a push button flow where we configure the design and run the design and obtain the final GDSII along with reports for this flow.

-Interactive -> We run individual commands and steps one by one in an ordered fashion without skipping any step so we can do experimentation and get the idea of how our result will look like.

It has the feature of Design Space Exploration where we can find the best set of flow configurations.It has larger number of design examples which ia around 43 designs with best configurations and some more on the way.


###### OpenLane Detailed ASIC Flow 


![image](https://user-images.githubusercontent.com/60011091/123989549-a04c6a00-d9e6-11eb-835a-48e86fb0dd8c.png)
 This image shows the OpenLane Detailed ASIC Flow
 
 This Flow is based on OpenROAD, Klayout, Yosys, Magic, Qflow, Fault and ABC etc.
 
 
![image](https://user-images.githubusercontent.com/60011091/123990116-2072cf80-d9e7-11eb-99c9-9ef5d671b704.png)

![image](https://user-images.githubusercontent.com/60011091/123990295-44361580-d9e7-11eb-969c-9eb20616da38.png)


![image](https://user-images.githubusercontent.com/60011091/123990414-5dd75d00-d9e7-11eb-98bc-f0ddb3a5e7a5.png)



![image](https://user-images.githubusercontent.com/60011091/123990478-6e87d300-d9e7-11eb-964c-4db4cfae505c.png)
The above image is for Yosys. Yosys takes RTL code and .lib files as input and netlist as output.


![image](https://user-images.githubusercontent.com/60011091/123990753-ae4eba80-d9e7-11eb-8750-f028afe00541.png)


![image](https://user-images.githubusercontent.com/60011091/123991096-084f8000-d9e8-11eb-8b6b-7763f948481e.png)


###### Design Exploration 


![image](https://user-images.githubusercontent.com/60011091/123991469-60868200-d9e8-11eb-93c5-b8669fb9a2e0.png)


This image shows the design exploration details such as design name,total runtime for the design flow, cell counts and other details which is tabulated for users to understand the design explorations.


We can do regression testing for these designs as well. 



###### DFT

This step is optional in OpenLane which includes scan insertions, ATPGS, Test pattern compaction, fault coverge and fault simulation. 

![image](https://user-images.githubusercontent.com/60011091/123992809-8fe9be80-d9e9-11eb-9826-68a0852fa4c9.png)


###### Logic Equivalence Circuit (LEC)

This check is used to formally confirm that the function did not change after modifying the netlist.


###### Fake antenna diode insertion 

This step is done to deal with antenna violations caused during reaction ion etching which causes charge to accumlate metal wires which in turn damages the transition gates.

![image](https://user-images.githubusercontent.com/60011091/123994454-0509c380-d9eb-11eb-84b4-7f6ff936915c.png)



#### Open source EDA tools Lab


##### OpenLane directory Structure

OpenLane is a flow rather than atools which comprises of many open source EDA tools


![image](https://user-images.githubusercontent.com/60011091/123998643-4e5c1200-d9ef-11eb-9104-4d49016dd6a1.png)

![image](https://user-images.githubusercontent.com/60011091/123998685-5a47d400-d9ef-11eb-8625-116a61713dfc.png)

![image](https://user-images.githubusercontent.com/60011091/123999153-d3472b80-d9ef-11eb-859e-b58fc20fe150.png)


![image](https://user-images.githubusercontent.com/60011091/123999377-143f4000-d9f0-11eb-9adf-a9753964dce4.png)


![image](https://user-images.githubusercontent.com/60011091/123999668-654f3400-d9f0-11eb-9021-4798cf0f37c2.png)



![image](https://user-images.githubusercontent.com/60011091/124000056-d393f680-d9f0-11eb-8dbd-825813730b38.png)


![image](https://user-images.githubusercontent.com/60011091/124000551-53ba5c00-d9f1-11eb-8e06-02e28f538137.png)

![image](https://user-images.githubusercontent.com/60011091/124000624-63d23b80-d9f1-11eb-991d-3568657f13a4.png)


![image](https://user-images.githubusercontent.com/60011091/124000925-b7448980-d9f1-11eb-888a-92c6f81144ef.png)


##### Preparation of design 


Interactive flow of OpenLane 

![image](https://user-images.githubusercontent.com/60011091/124001831-a8120b80-d9f2-11eb-96a9-62c6a6f48a4d.png)

                 $make mount
                 bash-4.2$ pwd
                 bash-4.2$ ls -ltr
                 bash-4.2$ ./flow.tcl -interactive



The below images shows the designs in the OpenLane design folder

![image](https://user-images.githubusercontent.com/60011091/124002383-4b632080-d9f3-11eb-80f4-926802183ea9.png)


![image](https://user-images.githubusercontent.com/60011091/124002543-81a0a000-d9f3-11eb-8a4c-666c149b8b8e.png)


Picorv32a is the design and its contents are shown in the below images.


![image](https://user-images.githubusercontent.com/60011091/124002670-a5fc7c80-d9f3-11eb-8ba1-51f17b68d317.png)


![image](https://user-images.githubusercontent.com/60011091/124003865-05a75780-d9f5-11eb-8f97-b47eed575f61.png)


config.tcl file for picorv32a

![image](https://user-images.githubusercontent.com/60011091/124004206-6cc50c00-d9f5-11eb-9c99-50fc903e6867.png)


![image](https://user-images.githubusercontent.com/60011091/124003977-31c2d880-d9f5-11eb-8659-353934a7113f.png)

sky130_fd_sc_hd_config.tcl for picorv32a

![image](https://user-images.githubusercontent.com/60011091/124004461-a9910300-d9f5-11eb-8d36-dfca069981c1.png)



Preparation of design 

![image](https://user-images.githubusercontent.com/60011091/124005058-494e9100-d9f6-11eb-8b01-30b771ae1936.png)


![image](https://user-images.githubusercontent.com/60011091/124005417-aa766480-d9f6-11eb-9ee7-6c27221f4cb7.png)


![image](https://user-images.githubusercontent.com/60011091/124005608-e90c1f00-d9f6-11eb-8add-1ff8893dc000.png)


![image](https://user-images.githubusercontent.com/60011091/124005933-47d19880-d9f7-11eb-8310-f08b81415611.png)

merge.lef contents 

![image](https://user-images.githubusercontent.com/60011091/124006066-70599280-d9f7-11eb-83c6-1135fd4b1ac4.png)

![image](https://user-images.githubusercontent.com/60011091/124006158-8a937080-d9f7-11eb-8e36-748d512a2ca5.png)

![image](https://user-images.githubusercontent.com/60011091/124006205-967f3280-d9f7-11eb-84b8-9554af7f0e82.png)


config.tcl in reports directory

![image](https://user-images.githubusercontent.com/60011091/124006444-e8c05380-d9f7-11eb-92ee-a14571ac505a.png)

![image](https://user-images.githubusercontent.com/60011091/124006573-10afb700-d9f8-11eb-9418-5887c3ac7f3e.png)


![image](https://user-images.githubusercontent.com/60011091/124006677-2c1ac200-d9f8-11eb-8ed2-140d25937fdc.png)


![image](https://user-images.githubusercontent.com/60011091/124006723-3b017480-d9f8-11eb-9546-16b1375e38ad.png)


##### Synthesizing picorv32a design reports

![image](https://user-images.githubusercontent.com/60011091/124007257-d4c92180-d9f8-11eb-9c33-f07cc0eb7b00.png)

Utilization report


![image](https://user-images.githubusercontent.com/60011091/124007498-0b06a100-d9f9-11eb-96a4-fe4c62f3f0ba.png)

DFF Utilization report

![image](https://user-images.githubusercontent.com/60011091/124007742-4608d480-d9f9-11eb-893d-fcb1a169bed4.png)


DFF Ratio

![image](https://user-images.githubusercontent.com/60011091/124009117-d5fb4e00-d9fa-11eb-9ed5-a797804cca5a.png)


OPEN STA Timing report 

![image](https://user-images.githubusercontent.com/60011091/124009357-1f4b9d80-d9fb-11eb-8864-162977211f83.png)


![image](https://user-images.githubusercontent.com/60011091/124009412-325e6d80-d9fb-11eb-8586-75454f49df34.png)


![image](https://user-images.githubusercontent.com/60011091/124009587-6a65b080-d9fb-11eb-9488-fbad688d9eeb.png)



##### OpenLane Github link 


https://github.com/The-OpenROAD-Project/OpenLane

This is the link of the OpenLane with the latest version 0.21. 

OpenROAD has 37 repos and OpenLane is one of them. 

This project has a well documented installation procedures and how to work post OpenLane and PDKs installations. 

We have a lot of options and commands for Github like forking, cloning or download a particular repo in .zip format etc. 





## Day-2 Understand importance of good floorplan vs bad floorplan and introduction to library cells













## Day-3 Design and characterize one library cell using Magic Layout tool and ngspice









## Day-4 Pre-layout timing analysis and importance of good clock tree




## Day-5 Final steps for RTL2GDS
