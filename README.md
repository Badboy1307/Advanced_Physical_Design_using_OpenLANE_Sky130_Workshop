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

OpenLane is a flow rather than a tool which comprises of many open source EDA tools.


        $ cd Desktop/work/tools
        $ ls -ltr
        $ cd openlane_working_dir


![image](https://user-images.githubusercontent.com/60011091/123998643-4e5c1200-d9ef-11eb-9104-4d49016dd6a1.png)


       
        $ ls -ltr
        $ cd pdks 
        $ ls -ltr 
        $ cd sky130A
        $ ls -ltr




![image](https://user-images.githubusercontent.com/60011091/123998685-5a47d400-d9ef-11eb-8625-116a61713dfc.png)




![image](https://user-images.githubusercontent.com/60011091/123999153-d3472b80-d9ef-11eb-859e-b58fc20fe150.png)





           $ ls -ltr
           $ cd libs.ref
           $ ls -ltr 
           $ cd ../
           $ cd libs.tech
           $ ls -ltr
           $ cd ../libs.ref
           $ cd sky130_fd_sc_hd
           $ ls -ltr
           




![image](https://user-images.githubusercontent.com/60011091/123999377-143f4000-d9f0-11eb-9adf-a9753964dce4.png)




![image](https://user-images.githubusercontent.com/60011091/123999668-654f3400-d9f0-11eb-9021-4798cf0f37c2.png)





![image](https://user-images.githubusercontent.com/60011091/124000056-d393f680-d9f0-11eb-8dbd-825813730b38.png)





              
           $ ls -ltr
           $ cd lib
           $ ls -ltr
              
           
           

![image](https://user-images.githubusercontent.com/60011091/124000551-53ba5c00-d9f1-11eb-8e06-02e28f538137.png)




![image](https://user-images.githubusercontent.com/60011091/124000624-63d23b80-d9f1-11eb-991d-3568657f13a4.png)






##### Preparation of OpenLane


Interactive flow of OpenLane 



          $ cd../../
          $ cd../../../
          $ cd openlane_working_dir
          $ cd openlane



![image](https://user-images.githubusercontent.com/60011091/124000925-b7448980-d9f1-11eb-888a-92c6f81144ef.png)

        
        
        
         $make mount
         bash-4.2$ pwd
         bash-4.2$ ls -ltr
         bash-4.2$ ./flow.tcl -interactive


![image](https://user-images.githubusercontent.com/60011091/124001831-a8120b80-d9f2-11eb-96a9-62c6a6f48a4d.png)







The below images shows the designs in the OpenLane design folder


         $ cd designs
         $ ls -ltr



![image](https://user-images.githubusercontent.com/60011091/124002383-4b632080-d9f3-11eb-80f4-926802183ea9.png)





![image](https://user-images.githubusercontent.com/60011091/124002543-81a0a000-d9f3-11eb-8a4c-666c149b8b8e.png)




Picorv32a is the design and its contents are shown in the below images.




         $ cd picorv32a
         $ ls -ltr 
         $ cd src
         $ ls -ltr
         


![image](https://user-images.githubusercontent.com/60011091/124002670-a5fc7c80-d9f3-11eb-8ba1-51f17b68d317.png)





![image](https://user-images.githubusercontent.com/60011091/124003865-05a75780-d9f5-11eb-8f97-b47eed575f61.png)








config.tcl file for picorv32a





        $ less config.tcl




![image](https://user-images.githubusercontent.com/60011091/124004206-6cc50c00-d9f5-11eb-9c99-50fc903e6867.png)





![image](https://user-images.githubusercontent.com/60011091/124003977-31c2d880-d9f5-11eb-8659-353934a7113f.png)





sky130_fd_sc_hd_config.tcl for picorv32a

![image](https://user-images.githubusercontent.com/60011091/124004461-a9910300-d9f5-11eb-8d36-dfca069981c1.png)








Preparation of design 


      % pacakge require openlane 0.9
      % prep -design picorv32a

![image](https://user-images.githubusercontent.com/60011091/124005058-494e9100-d9f6-11eb-8b01-30b771ae1936.png)

      
      
      
      $ ls -ltr
      $ cd runs
      $ ls -ltr
      $ cd 30-06_17-25
      $ ls -ltr
      
      
 The below images shows all the runs of the design specific to date the design was run under run folder from picorv32a design. 


![image](https://user-images.githubusercontent.com/60011091/124005417-aa766480-d9f6-11eb-9ee7-6c27221f4cb7.png)






![image](https://user-images.githubusercontent.com/60011091/124005608-e90c1f00-d9f6-11eb-8add-1ff8893dc000.png)






![image](https://user-images.githubusercontent.com/60011091/124005933-47d19880-d9f7-11eb-8310-f08b81415611.png)







merge.lef contents 


      
      

![image](https://user-images.githubusercontent.com/60011091/124006066-70599280-d9f7-11eb-83c6-1135fd4b1ac4.png)




![image](https://user-images.githubusercontent.com/60011091/124006158-8a937080-d9f7-11eb-8e36-748d512a2ca5.png)





![image](https://user-images.githubusercontent.com/60011091/124006205-967f3280-d9f7-11eb-84b8-9554af7f0e82.png)






config.tcl in reports directory



     $ cd reports
     $ ls -ltr


![image](https://user-images.githubusercontent.com/60011091/124006444-e8c05380-d9f7-11eb-92ee-a14571ac505a.png)






![image](https://user-images.githubusercontent.com/60011091/124006573-10afb700-d9f8-11eb-9418-5887c3ac7f3e.png)






![image](https://user-images.githubusercontent.com/60011091/124006677-2c1ac200-d9f8-11eb-8ed2-140d25937fdc.png)






![image](https://user-images.githubusercontent.com/60011091/124006723-3b017480-d9f8-11eb-9546-16b1375e38ad.png)








##### Synthesized picorv32a design reports

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

### Chip Floorplanning considerations


#### Utilization Factor and Aspect Ratio




Core is the section of the chip where the fundamental logic of the design are placed

Die which consist of core is a small semiconductor material specimen on which the fundamental circuit is fabricated.


![image](https://user-images.githubusercontent.com/60011091/124116318-75b4ec80-da8c-11eb-91b8-ee30364f44d7.png)


-Netlist occupies the core area leading to 100% utilization.


     Utilization Factor = Area occupied by the Netlist/ Total Area of the core 
       
       
-Whenever the Utilization Factor=1, the core is fully occupied and we are not allowed to ad any extra cells in our design and the core will take square shaped structure.


     Aspect Ration= Height/ Width
       
       
-Whenever the Aspect Ratio = 1, it signifies that the chip is square shaped. But whenever the Aspect Ratio or Utilization Factor is not 1, then  the chip will take rectangular shaped structure.


####  Preplaced Cells

      


![IPs_Workspace](https://user-images.githubusercontent.com/60011091/124118719-3e940a80-da8f-11eb-8e60-e6f5b8c704b7.jpg)

-The arrangement of IP's in a chip is called Floorplanning.

-These IP's/blocks have user defined locations and so these are placed in chip before automated placement and routing and are called as pre-placed cells.

-Automated placement and routing tools places the remaining logic cells in the design onto the chip.

#### Lab for Floorplanning 

##### Running floorplan in OpenLane


Configuration folder of OpenLane 

       
       $ cd configuration
       $ pwd
       $ ls -ltr 



![image](https://user-images.githubusercontent.com/60011091/124123465-fc6dc780-da94-11eb-9cbf-89a837b8e6cd.png)



![image](https://user-images.githubusercontent.com/60011091/124124108-af3e2580-da95-11eb-91ce-e1fed9c16612.png)





README.md File




![image](https://user-images.githubusercontent.com/60011091/124123717-3e970900-da95-11eb-81d3-e29abf1acbab.png)



![image](https://user-images.githubusercontent.com/60011091/124123809-5a021400-da95-11eb-9146-20f882f3036e.png)



![image](https://user-images.githubusercontent.com/60011091/124123890-6be3b700-da95-11eb-9b0e-e9b43ff35a7a.png)

       
       
 ![image](https://user-images.githubusercontent.com/60011091/124123987-874ec200-da95-11eb-97af-612121f1eb7f.png)



floorplan.tcl file 


![image](https://user-images.githubusercontent.com/60011091/124124208-cc72f400-da95-11eb-9b30-17a7c1cbffa4.png)



![image](https://user-images.githubusercontent.com/60011091/124124263-dbf23d00-da95-11eb-8011-107280370ef1.png)



picorv32a Folder contents 

         
     $ cd designs/picorv32a
     $ pwd
     $ ls -ltr 
     


![image](https://user-images.githubusercontent.com/60011091/124124648-558a2b00-da96-11eb-9212-06c426f5f2b9.png)


So the precendence is lowest prioriy is system defaults ie all the tcl files for configuration in OpenLane. The next priority is for config.tcl and the last priority is sky130A_sky130_fd_sc_hd_config.tcl.


Config.tcl for picorv32a

![image](https://user-images.githubusercontent.com/60011091/124125278-0e506a00-da97-11eb-964e-5c17675398b5.png)


Running Floorplanning


    % run_floorplan

![image](https://user-images.githubusercontent.com/60011091/124125504-4b1c6100-da97-11eb-9681-a40ee2993351.png)



![image](https://user-images.githubusercontent.com/60011091/124125612-72732e00-da97-11eb-95ca-b3a678eef150.png)




![image](https://user-images.githubusercontent.com/60011091/124125673-874fc180-da97-11eb-87f0-5641a5dda44d.png)




![image](https://user-images.githubusercontent.com/60011091/124125772-9c2c5500-da97-11eb-84f6-965bdef75fcc.png)





![image](https://user-images.githubusercontent.com/60011091/124125863-b0705200-da97-11eb-88af-2619815c011d.png)



![image](https://user-images.githubusercontent.com/60011091/124125991-d3026b00-da97-11eb-9503-88f6d344b700.png)



 Viewing Floorplanning files
 
 
 
    $ cd picorv32a
    $ less config.tcl
    $ cd runs
    $ ls -ltr
    $ cd 30-06_17-25
    $ ls -ltr
    $ less config.tcl
    $ cd logs/floorplan/
    $ ls -ltr 
 


![image](https://user-images.githubusercontent.com/60011091/124126385-41dfc400-da98-11eb-839a-2f7a69f4179a.png)



![image](https://user-images.githubusercontent.com/60011091/124126556-6b98eb00-da98-11eb-91db-77acfbcb009c.png)




![image](https://user-images.githubusercontent.com/60011091/124126814-abf86900-da98-11eb-8fe0-4d34d6e3ce54.png)



![image](https://user-images.githubusercontent.com/60011091/124127144-0265a780-da99-11eb-8444-c37867a1c682.png)


Config file in the picorv32a runs folder


![image](https://user-images.githubusercontent.com/60011091/124127322-3771fa00-da99-11eb-8902-17aa127e13f0.png)


Picorv32a def file 


    $ cd 30-06_17-25
    $ ls -ltr
    $ less picorv32a.floorplan.def

![image](https://user-images.githubusercontent.com/60011091/124127655-a18a9f00-da99-11eb-9bb2-ff556e21e2f2.png)


Opening floorplan using Magic 


    $ magic -T /home/john/Desktop/work/tools.openlane_working_dir/openlane/pdks/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def & 
    



![image](https://user-images.githubusercontent.com/60011091/124128834-c7647380-da9a-11eb-8f68-5156d5c50338.png)






![image](https://user-images.githubusercontent.com/60011091/124128983-f1b63100-da9a-11eb-945e-9c9f87c2be67.png)




![image](https://user-images.githubusercontent.com/60011091/124130033-fa5b3700-da9b-11eb-9c25-d650683ad128.png)





![image](https://user-images.githubusercontent.com/60011091/124130672-a866e100-da9c-11eb-8cc9-d70be38d077d.png)






##### Placement and Routing 


Libraries are like shelves which can be divided into two sub libraries like one library will have shapes and sizes informations and the other might have delay related informations. 

Steps in Placement is as below 

-Binding netlist with physical cell 

The image below shows different flavors for same flipflop, gates and other netlists which can differ in sizes, shapes or delay relatedninformations.


![image](https://user-images.githubusercontent.com/60011091/124132170-2972a800-da9e-11eb-8df3-4fd26444a121.png)


-Placement 


![image](https://user-images.githubusercontent.com/60011091/124133881-e6b1cf80-da9f-11eb-8008-62749f4d4e14.png)



-Optimize Placement 

This is the stage where we estimate the wire length and capacitances so based on that we insert repeaters. As shown below:


![image](https://user-images.githubusercontent.com/60011091/124135078-1a412980-daa1-11eb-9dc9-3718d0ea47cc.png)





###### Need for libraries and characterizations


![Common_Workspace](https://user-images.githubusercontent.com/60011091/124135847-d39fff00-daa1-11eb-8469-c4fcff2f9425.jpg)


This image shows the common things across all the steps in OpenLane flow.


#### Lab For Placement


    % run_placement


![image](https://user-images.githubusercontent.com/60011091/124143057-6cd21400-daa8-11eb-8543-b587fa67be30.png)



![image](https://user-images.githubusercontent.com/60011091/124143198-8b380f80-daa8-11eb-8299-57dc7f9663cc.png)




![image](https://user-images.githubusercontent.com/60011091/124143309-a60a8400-daa8-11eb-90aa-f0a85a9b9072.png)




![image](https://user-images.githubusercontent.com/60011091/124143424-bb7fae00-daa8-11eb-8a60-a86e00b763e2.png)



![image](https://user-images.githubusercontent.com/60011091/124143523-d2260500-daa8-11eb-9478-ba293e33f0e5.png)



![image](https://user-images.githubusercontent.com/60011091/124143727-fda8ef80-daa8-11eb-933c-772d1de1bbed.png)




Viewing def file of placement in picorv32a design 


    $ cd results/placement
    $ ls
    


![image](https://user-images.githubusercontent.com/60011091/124144262-6ee8a280-daa9-11eb-8d85-2d9ea7e532f5.png)






Magic Layout after Placement of picorv32a



    $ magic -T /home/john/Desktop/work/tools.openlane_working_dir/openlane/pdks/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def & 

![image](https://user-images.githubusercontent.com/60011091/124144516-ae16f380-daa9-11eb-85aa-969a87911f1c.png)




![image](https://user-images.githubusercontent.com/60011091/124144972-0ea63080-daaa-11eb-85a9-fe3cead024f7.png)





![image](https://user-images.githubusercontent.com/60011091/124145421-680e5f80-daaa-11eb-8570-fe06d017cd33.png)







![image](https://user-images.githubusercontent.com/60011091/124145514-7e1c2000-daaa-11eb-8fcd-e23edbdaf4ea.png)





#### Cell Flow 



![Cell_design_Workspace](https://user-images.githubusercontent.com/60011091/124148859-b2dda680-daad-11eb-9e66-5423b5cd0ee8.jpg)

The above image shows what are the components in the Cell flow 


The below images talk about DRC and LVS rules in a brief way 




![image](https://user-images.githubusercontent.com/60011091/124149347-1f58a580-daae-11eb-9e6e-f2c99dc650f4.png)





![image](https://user-images.githubusercontent.com/60011091/124149468-3dbea100-daae-11eb-84ee-b1c39e760646.png)







The below image explains about SPICE models and shows the formulated equation for Threshold Voltage Equation and for linear and saturated regions of operation for the models.



![Untitled](https://user-images.githubusercontent.com/60011091/124150644-5c716780-daaf-11eb-97c5-85bb276ac718.png)


The below images show an example of SPICE Models From Tanner EDA Tool for 0.18nm technology 


![image](https://user-images.githubusercontent.com/60011091/124153976-a60f8180-dab2-11eb-8e3a-a1e888e503c0.png)


![image](https://user-images.githubusercontent.com/60011091/124154041-b6276100-dab2-11eb-9fa9-f6deed66bef9.png)


#### Design Steps

-Circuit Design 

In circuit design Step

We take user defined specifications like cell height, supply voltage, metal layers and pin locations in this design step for cell flow 

![image](https://user-images.githubusercontent.com/60011091/124155570-4023f980-dab4-11eb-982d-12a04f9ddede.png)


The above image is an example of circuit design step where we use Euler's path concept to construct paths for the layout design.

Thhe equation for the circuit is Fn= ((B+D) +(A+C) + E.F)'


![image](https://user-images.githubusercontent.com/60011091/124156347-28994080-dab5-11eb-9564-c83ea607ead5.png)


The above circuit show the equation for Wp/Lp / Wn/Ln ratio to set Vm which is the threshold voltage of the above circuit.


-Layout Design 

In layout design as we have mentioned in circuit design that we are using Euler's path concept to construct layout. 



So below image is the example of the paths.


![image](https://user-images.githubusercontent.com/60011091/124156740-9e9da780-dab5-11eb-84f2-598c3bc5a3f5.png)


The below image explains the euler's path clearly. 

![image](https://user-images.githubusercontent.com/60011091/124156964-df95bc00-dab5-11eb-90f5-545d22b1965a.png)



-Characterization Flow 


![image](https://user-images.githubusercontent.com/60011091/124157458-68acf300-dab6-11eb-9a76-14d730dee38f.png)


This schematic is for a buffer which has inverters connected back to back and this is drawn in GUNA Tool. 



The below two images shows the netlist for the main circuit and subcircuit for the buffer we have taken in previous image. The third and fourth images are a model parameter file for this SPICE model.

![image](https://user-images.githubusercontent.com/60011091/124157676-a6118080-dab6-11eb-8bbd-d843b819b603.png)


![image](https://user-images.githubusercontent.com/60011091/124157708-b164ac00-dab6-11eb-8567-fe08c0272f02.png)


![image](https://user-images.githubusercontent.com/60011091/124157748-bc1f4100-dab6-11eb-8940-23891c51a7a5.png)


![image](https://user-images.githubusercontent.com/60011091/124158114-2801a980-dab7-11eb-81a0-7c4953abb1b2.png)


This GUNA softwares Takes all the files shown in this sections as inputs and generates outputs as Timing, Noise and  Power .libs.


#### Timing Threshold Definitions

Low depicts the values which are close to 0 power supply.

Here in the below concepts we used red line to show inputs and blue for outputs in the graphs.


slew_low_rise_thr- defines the point over the lower side of your power supply which is 0V. Typical value of slew_low_rise_thr is about 20% or can be 30% of bottom power supply.



![image](https://user-images.githubusercontent.com/60011091/124162455-14a50d00-dabc-11eb-9337-acdb9c4ff9f0.png)

The above image depicts the slew_low_rise_thr definition.


slew_high_rise_thr- defines the point over the higher side of power supply. Typical value of slew_high_rise_thr is about 20% or can be 30% of top power supply.

![image](https://user-images.githubusercontent.com/60011091/124162634-49b15f80-dabc-11eb-963c-cddd01d186ad.png)

The above image depicts the slew_high_rise_thr definition.

slew_low_fall_thr

![image](https://user-images.githubusercontent.com/60011091/124165084-115f5080-dabf-11eb-8647-441c1a027448.png)

This images explains slew_low_fall_thr concept.


slew_high_fall _thr

![image](https://user-images.githubusercontent.com/60011091/124163078-d78d4a80-dabc-11eb-8940-63499375737b.png)

This images explains slew_high_fall _thr concept. 



in_rise_thr-

![image](https://user-images.githubusercontent.com/60011091/124163518-479bd080-dabd-11eb-8aeb-ed08073383fc.png)

This image explains in_rise_thr concept.
 


in_fall_thr

![image](https://user-images.githubusercontent.com/60011091/124163924-c133be80-dabd-11eb-8b17-5c6cd57259a2.png)

This image explains in_faLL_thr concept.



out_rise_thr


![image](https://user-images.githubusercontent.com/60011091/124163756-892c7b80-dabd-11eb-921c-18c5876a6df0.png)

This image explains out_rise_thr concept.


out_fall_thr

![image](https://user-images.githubusercontent.com/60011091/124164016-e45e6e00-dabd-11eb-8913-8b98abe9698d.png)

This image explains out_fall_thr concept.



![image](https://user-images.githubusercontent.com/60011091/124164482-51720380-dabe-11eb-8c1c-9cd1456de8af.png)


The above table summarizes the concepts learn in this section all the % is taken from the VDD. in the above Table we see slew_low_rise_thr is 20% of VDD so similarly other % are taken from VDD. 







## Day-3 Design and characterize one library cell using Magic Layout tool and ngspice




### Lab for CMOS inverter ngspice simulations


![image](https://user-images.githubusercontent.com/60011091/124224442-47362080-db23-11eb-87c8-e6b7689c07ea.png)


The above image shows the ngspice simulator which we are going to use in this lab.


#### IO Placer Revision

![image](https://user-images.githubusercontent.com/60011091/124339904-1dd2ce80-dbcf-11eb-8f79-7b3ab99def93.png)


The above image indicates the location from where we are trying to read picorv32a.floorplan.def to understand about IO placers in the design in floorplan step.

![image](https://user-images.githubusercontent.com/60011091/124340035-f3354580-dbcf-11eb-9f29-e188798b524e.png)


From the above image we see that by default pins are placed equidistantly from each other.

![image](https://user-images.githubusercontent.com/60011091/124340100-6f2f8d80-dbd0-11eb-9d73-ca2c5502339a.png)


This is the zoomed version of the previous image to show that the pin are placed equidistantly from each other.



![image](https://user-images.githubusercontent.com/60011091/124340363-4e683780-dbd2-11eb-87ad-2bad0a0e3484.png)


Here in the image we see FP_IO_MODE is set to 1, 0 for matching mode and 1 for random equidistant pins.



![image](https://user-images.githubusercontent.com/60011091/124340446-05fd4980-dbd3-11eb-823c-cd1bcdf1a465.png)


Here we are setting FP_IO_MODE to 2 in the above image. 


![image](https://user-images.githubusercontent.com/60011091/124340627-18c44e00-dbd4-11eb-91af-a501b4f8bbc2.png)


This is the layout we will be getting where pins are not equidistant from each other but pins are stacked upon one another.


#### SPICE Deck creation and simulation for CMOS Inverter

SPICE Deck is nothing but the connectivity information about the netlist.

This has the connectivity information, inputs to be provided to the simulator, tap points at which we will take the  outputs etc.


![image](https://user-images.githubusercontent.com/60011091/124341467-41e7dd00-dbda-11eb-91b1-8a5f5f566747.png)


We are going to create SPICE Deck for the circuit in the above image.

    







## Day-4 Pre-layout timing analysis and importance of good clock tree




## Day-5 Final steps for RTL2GDS
