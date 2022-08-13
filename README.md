# VSD PHYSICAL DESIGN USING OPEN SOURCE TOOLS

The repository shows the 5 - day workshop for beginners using open source tools like yosys,magic,opentimer,qrouter and the purpose of this repository is to provide a complete idea about the 5 - days workshop on VLSI SoC/Physical design using open source EDA tools.


## *Contents of 5 - Days Workshop:*
	
- **Day 1 - Study and Review Various Components of RISC-V based PicoSoC**

- **Day 2 - Chip Planning Strategies and Introduction to Foundry Library Cells**

- **Day 3 - Design and Characterize one Library Cell using magic Layout Tool and ngspice**

- **Day 4 - Pre-Layout Timing Analysis and Importance of Good Clock Tree**

- **Day 5 - Final Steps for RTL2GDS**


## *Day 1 - Study and Review Various Components of RISC-V based PicoSoC*

**IC TERMINOLOGIES :**

**Package** QFN - 48 is manufactured by germany labs. The full form of QFN is Quad Flat No leads and the number 48 represents the number of ports of the chip.The package dimensions are 7mm * 7mm.

![1](https://user-images.githubusercontent.com/80052961/110233528-90e27600-7f4a-11eb-856b-b47fa4b7a615.JPG)

			QFN - 48

**Pads** are one of the important components of the chip, which is used to send the signals to inside the chip and receive the signals from inside to outside and viceversa. **core** is a section of chip where we place the all digital components. A **Die**  is a small block of semiconducting material on which a given functional circuit is fabricated.

![2](https://user-images.githubusercontent.com/80052961/110233813-9b9e0a80-7f4c-11eb-9b04-2e55ac148cb0.JPG)

**RISC - V OVERVIEW:**

1.RISC - V available in various flavours i.e genealogy

2.RV32 has 32 - bit instructions

3. Suffixes specify available extensions  -I : basic integer instruction set; -M : hardware mulptiplier/divider; -C : compressed instruction set (16 - bit)

**PICORV32 OVERVIEW:**

key features: 1. small size 2.high clock speed 3.native memory interface 4.optional IRQ support

**IC DESIGN COMPONENTS:**

					Logic synthesis - yosys open synthesis suite

					Floorplanning, Placement and CTS - graywolf

						Routing - qrouter

					Static Timing Analysis - opentimer

					pre-layout/post-layout simulation - ngspice

						schematic editor - esim
						

ngspice - General purpose circuit simulation programs for both non linear and linear analysis.

magic - Vlsi layout editor, extraction and DRC tool

opentimer - Open sourece high performance timing analysis tool

esim - Complext circuit design, SPICE simulation and analysis and PCB design

qflow - Tool chain for complete RTL2GDS flow
					  

**DAY1 LAB SKILLS:**

yosys is synthesis tool which is used to convert the rtl code into gate level netlist. To open the yosys tool, we use the command yosys. 

![d1sk4](https://github.com/vishnuvardhan-k/vsd-physical-design-using-open-source-tools/blob/main/Day%201/D1SK4-MCQ3.JPG)


“which” is command used to shows the loction/directory path of tool/folder.Linux which command is used to identify the location of a given executable that is executed when you type the executable name (command) in the terminal prompt. The command searches for the executable specified as an argument in the directories listed in the PATH environment variable.

![D1SK4-MCQ4](https://user-images.githubusercontent.com/80052961/110207735-8329e380-7eab-11eb-9d79-2085d53d23c3.JPG)


==> git clone is a Git command line utility which is used to target an existing repository and create a clone, or copy of the target repository.


![D1SK4-MCQ5](https://user-images.githubusercontent.com/80052961/110207999-94bfbb00-7eac-11eb-841f-14d60a70ad69.JPG)

==> The cd command, also known as chdir (change directory), is a command-line shell command used to change the current working directory in various operating systems. It can be used in shell scripts and batch files.**cd vsdflow** command is usedchange the directory to vsdflow folder.**./vsdflow spi_slave_design_details.csv** is to initialize the design.The **ls** command lists the contents of a specified directory, excluding dotfiles. If no directory is specified then, by default, the contents of the current directory are listed. Listed files are sorted alphabetically.**ls -ltr outdir_spi_slave | wc** will show you the total 17 number of lines beacuse 1st line will give total number and the rest 16 are the number of flies.

![D1SK4-MCQ6](https://user-images.githubusercontent.com/80052961/110208038-d3557580-7eac-11eb-8349-8ddb453254bd.JPG)


**cd outdir_spi_slave** command change the directory to outdir_spi_slave and the **qflow display spi_slave** command open and display the qflow manager where you do preference,synthesis,placement and so on.Qflow(complete tool chain) is a complete tool chain for synthesizing digital circuits starting from verilog source and ending in physical layout for a specific target fabrication process

These commands open two windows 1.layout window
                                2. Tkcon window

![D1SK4-MCQ7_1](https://user-images.githubusercontent.com/80052961/110208575-04827580-7eae-11eb-84a3-37c0a0e6e84c.JPG)

1st select the chip area and then type the command box in tkcon window.it shows the selected area in microns.

![D1SK4-MCQ7_2](https://user-images.githubusercontent.com/80052961/110208587-1b28cc80-7eae-11eb-9d28-f3410f268a2f.JPG)

![D1SK4-MCQ7](https://user-images.githubusercontent.com/80052961/110208597-23810780-7eae-11eb-9dca-3ee02319f153.JPG)

**cd vsdflow** is a command change the directory to vsdflow, **mkdir** is a command create the folder, **cd my_picorv32** is a command to change the directory to my_picorv32, **mkdir source synthesis layout** is a command to create folders source, synthesis and layout, **cp ~/vsdflow/Verilog/picorv32.v/source/.** - copy the Verilog file i.e picorv32 from source to vsdflow, **qflow gui &**- it open qflow manager in a graphical user interface.

These commands open qflow manager window

					set technology = osu018
    
					Verilog source = picorv32.v
    
					Verilog module = picorv32
    
What is the % ratio of flipflop/total logic ?

![D1SK4-MCQ8_1](https://user-images.githubusercontent.com/80052961/110208826-60013300-7eaf-11eb-97f7-02e4e14f9ccb.JPG)

 After entering the commands shown above, it opens a qflow manager and we set the preferences,technology = osu018, Verilog source = picorv32 and verilog module = picorv32. Click on start button opposite the preparation. If it is okay, then proceed to synthesis. Click on okay opposite to synthesis, it opens a synthesis log file. Synthesis file shows the number of cells, number of flops and etc.
 
 ![D1SK4-MCQ8_2](https://user-images.githubusercontent.com/80052961/110208848-74453000-7eaf-11eb-80c8-3a1133b64282.JPG)

			Ratio of flops to logic cells = Total number of flops / Total number of cells

![D1SK4-MCQ8](https://user-images.githubusercontent.com/80052961/110208861-86bf6980-7eaf-11eb-9386-dc81e7934f18.JPG)

         				Number of cells = 13197

        			  	Number of flops = 1613
         
 			Ratio of flops to total logic  = 1317/1613 = 12.22%
 
 
 ## *Day 2 - Chip Planning Strategies and Introduction to Foundry Library Cells*
 
 **core** is the section of the chip where the fundamental logic of the design is placed. A**die** ,which consists of core ,is a small semiconductor material specimen on whcih the fundamental circuit is fabricated. A ** netlist** describes the connectivity of a electronic design.
 
 ![5](https://user-images.githubusercontent.com/80052961/110236559-71ecdf80-7f5c-11eb-87a0-3f77dd0f6ac2.JPG)

If the logic cells occupies the complete area of the core,then this is called as **100% utilization**. The **Utilization Factor** is defined as the ratio of area occupied by netlist to total area of the core. **100% utilization means utilization factor is 1.0**.In practical scenario, we can only use 60 - 70 % utilization.

					utilization factor = area occupied by netlist/Total area of the core
						
**aspect ratio** is defined as ratio of height to width of the core. If the aspect ratio is **1** then the chip is in square shape and if it is **0.5** then the chip is in rectangle shape.

						Aspect ratio = height of the core / width of the core
						
**Define locations of preplaced cells:**
						
===> The arrangement of these IP's/blocks in a chip is reffered as **floorplanning**

===> **Pre placed cells** - These blocks have user defined locations and hence are placed in chip before automated placement and routing and are called as **pre-placed cells**.Examples of preplaced cells are memories,mux,multiplier etc. once there placed,it can't be touched by placement and routing tools. Automated placement and routing tool places the remaining logical cells in the design onto chip.

===> The prepalced cells has been placed in the core, depending upon the design scenario. Foe example,preplaced cells have more input connections then they are placed near to input side.

![6](https://user-images.githubusercontent.com/80052961/110237069-c5146180-7f5f-11eb-864a-c7123cb2595e.jpg)

**surround preplaced cells with decoupling capacitors:**

===> During switching operatons, the ckt demands swichting current i.e peak current (I peak). 

![7](https://user-images.githubusercontent.com/80052961/110237339-8ed7e180-7f61-11eb-827c-9b6747506df5.jpg)

===> Due to the presence of resistance and capacitance, ther will be a voltage drop acroos them and the voltage at node **A** would be **vdd'(0.7 v instead of 1v)** . If the voltage goes below the noise margin,the logic **1** at the output of the circuit wont be detected.

**noise margin summary:**

For any signal to be considered as logic 0 and logic 1 , it should be in the NML and NMH respectively.If there is a huge difference between the vdd and vdd' then it comes into undefined region in noise margin levels.

![8](https://user-images.githubusercontent.com/80052961/110237380-c050ad00-7f61-11eb-9dd8-3afd32f302db.jpg)

For this problem, we have a solution i.e adding decoupling capacitors parallel to the circuit.Every time the circuit switches, it draws currents from the decoupling cap, wheras RL network is used to refill the charge into decoulping capacitor.If there are any power hungry circuits in the design, we place the decoupling caps close to them physically.

**POWER PLANNING:** Decoupling caps take care of local communication but for global communication, we use power planning.![9](https://user-images.githubusercontent.com/80052961/110237696-59cc8e80-7f63-11eb-8062-d21c96d55678.JPG)

All the caps, which were charged to v volts will have to discharge to 0 through single ground point. This will cause a bump in groung tap point and it is called as **ground bounce**.All the caps, which were at 0 volts will have to charged to v through single power point. This will cause a bump in power tap point and it is called as **votlage droop**.

instead of single power supply, we will use multiple supplies so that we can avoid voltage droop and ground bounce.power planning can be done in mash shape.

![10](https://user-images.githubusercontent.com/80052961/110237908-98167d80-7f64-11eb-9bae-3518b4bf42d4.jpg)

**PIN PLACEMENT and LOGIC CELL PLACEMENT BLOCKAGE:** The connectivity info between gates is coded using VHDL/Verilog lang. and it is called as **netlist**. Pin placement is used the space between die and core. Frontend team defines the netlist connectivity and backend team defines the pin placement. Clock ports are bigger in size compared to data pins, the reason is clock is continuouslly driven the all flops in the design so we need least resistance as we know that resistance is inversely propotional to area.

**LOGICAL CELL PLACEMENT BLOCKAGE:** It blocks the particular area in between the die and core so that automated placement and routing tools can't be placed the logical cells into the area.The floorplan is ready for placement and routing.

![11](https://user-images.githubusercontent.com/80052961/110238938-4f61c300-7f6a-11eb-95c4-56c469adb415.jpg)

**PLACEMENT & ROUTING:**

**bind netlist with physical cells:** Library has different flavours of gates/cells with different sizes, different threshold voltges and different timing information. once we are given proper size/shape to the gate/cell then we go for placement.

**Placement:** Placement is the process of determining the locations of circuit devices on a die surface.

**Optimize placement based on estimated wire length and capacitance:** This is the stage where we estimate wire length and capacitance ,based on that we place repeaters. To maintain signal integrity between the input ports to flops so we use repeaters in between them. Slew depend upon the vaule of the capacitance.The higher the value of cap, the amount of charge required to charge the cap will high because of that slew will be bad.

**need for library and characterizaton:** From RTL2GDSII, one thing is common for all stages i.e is library.All the standard cells being placed in a section is called library.It consists of different sizes/shapes of the gates,different functionality of the gates and differnet Vth (LVT,HVT,SVT) cells. Vth = 0.4v inverter takes more time to switch compare to vth = 0.3v inverter.

**CELL DESIGN FLOW:** It divided into 3 parts : 1. inputs    2. Design steps    3.outputs

**1.Inputs:** Process Design kit's,DRC & LVS,SPICE models,library and user definend specs.

**DRC & LVS**: Technology file provides the lambda rules. For example, polywidth should be 2λ or more than that.

						λ = L/2 where L = min. feature size

**llibrary and user defined specs:**

**cell height** : The separaton between power rails and ground rails decides the cell height.

**cell width** : Cell width depends upon the timing info.if cell drive strength is lower, it's difficult for that cell to drive the huge wire length

**power supply :** A typical inverter has to operate at certain voltage which is provided by the top level designer.

**2. circuit design stpes:**

**i. circuit design:** 1.implement the function 2.model the design in order to meet the library requirements.

**ii. layout design: art of layout is a combination of eluer,s path and stick diagram**

1.function implemented into set of Pmos and nmos
2.get the pmos netwrok graph and nmos netwrok graph 
3.get the euler's path and then draw stick diagram
4.draw layout
5.extraxt spice model which consist the info of parasitics (R,C)

![12](https://user-images.githubusercontent.com/80052961/110240238-f8abb780-7f70-11eb-8ece-1f37546cf65d.jpg)
![13](https://user-images.githubusercontent.com/80052961/110240242-fc3f3e80-7f70-11eb-895a-5d51e1bf4eb4.jpg)

**3.Characterization:** It is the step that will help to get the info of timing,noise and power.**GUNA tool** is used for timing,noise and power characterization.
 
**TIMINIG CHARACTERIZATION:** Timing and delay information is important to the ASIC design process because it allows a level of realism to be incorporated into the circuit model.

**propagation delay:** Propagation delay typically refers to the rise time or fall time in logic gates. This is the time it takes for a logic gate to change its output state based on a change in the input state. It occurs due to inherent capacitance in the logic gate.

							tp = time(out_*_thr) - time (in_*_thr)
							
![14](https://user-images.githubusercontent.com/80052961/110240962-5f7ea000-7f74-11eb-9480-b4bbabd6b182.jpg)

choosing threshold points is very important. If we haven't take care this, propagation delay will be -ve.There are 2 situations for tp = -ve, 1. if the threshold points are moved to above then tp is -ve and 2. if the circuit is designed not properly, it has hage wire delays then it leads to -ve propagation delay.

![15](https://user-images.githubusercontent.com/80052961/110241139-45918d00-7f75-11eb-8784-90af7a6da375.jpg)

**Transition delay:** Transition delay or slew is defined as the time taken by signal to rise from 10 %( 20%) to the 90 %( 80%) of its maximum value.

![16](https://user-images.githubusercontent.com/80052961/110241188-7ec9fd00-7f75-11eb-88b0-772a7bf21d6c.JPG)

 
**DAY2 LAB SKILLS:**

First we have to change the directory to vsdflow using the command **cd vsdflow**,and then make a directory name *my_picorv32* using the command **mkdir my_picorv32** then change the directory to **my_picorv32** and **mkdir source synthesis layout** is a command to create folders source, synthesis and layout, **cp ../Verilog/picorv32.v source/** - copy the Verilog file i.e picorv32.v, **qflow gui &**- it open qflow manager in a graphical user interface.

![qflow](https://user-images.githubusercontent.com/80052961/110209245-6b555e00-7eb1-11eb-80f5-0d04dfbab6c4.JPG)

After entering the commands shown above, it opens a qflow manager and we set technology = osu018, Verilog source = picorv32 and verilog module = picorv32. Click on start button opposite the preparation. If it is okay, then proceed to synthesis. Click on okay opposite to synthesis, it opens a synthesis log file. Synthesis file shows the number of cells, number of flops and etc.

![placement2](https://user-images.githubusercontent.com/80052961/110209263-7c9e6a80-7eb1-11eb-98fa-f708573c7cfe.JPG)

1st select the chip area and then type the command box in tkcon window.it shows the selected area in microns.

![layoutofpicorv32](https://user-images.githubusercontent.com/80052961/110209279-89bb5980-7eb1-11eb-87e6-66ee41f5fe24.JPG)

The below images shows the pins(clk,rstn) in bottom of chip.first we group them and then select the pin arrange to bottom.

![bottom_group](https://user-images.githubusercontent.com/80052961/110209283-8cb64a00-7eb1-11eb-88e8-b436d1196388.JPG)

The below image shows the chip area which is selected in the layoutsection.

![chipsize](https://user-images.githubusercontent.com/80052961/110209286-917afe00-7eb1-11eb-8ee8-1e10961bd351.JPG)


## *Day 3 - Design and Characterize one Library Cell using magic Layout Tool and ngspice*

**1.SPICE deck Creation for CMOS Inverter:**

**SPICE Deck:** it is the information of component connectivity,intput and output. substrate/body of pmos is connected to vdd and nmos substrate/body is conncted to vss.

component values :

				M1:PMOS : W/L = 0.375u/0.25u
				
				M2:NMOS : W/L = 0.375u/0.25u
				
				cap : Cload = 10fF
				
				vin = 2.5v and vdd = 2.5v

![18](https://user-images.githubusercontent.com/80052961/110241794-cc943480-7f78-11eb-90dd-23d1eb3e743a.JPG)
 
![17](https://user-images.githubusercontent.com/80052961/110241712-39f39580-7f78-11eb-8902-da172f2ccab8.JPG)

ideally,pmos should be twice/trice bigger than nmos.

**SPICE  Waveform:** It is the transfer characteristics of the inverter.

![19](https://user-images.githubusercontent.com/80052961/110241862-2268dc80-7f79-11eb-8354-6171a384eb8c.JPG)

**SWITCHING THRESHOLD(Vm):** Integrity and robustness,expressed by the static (or steady-state) behavior. CMOS Inverter robustness, defines certain parameters and one of thing is **switching threshold**. switching threshold (Vm) means the point at which the device switches.draw a tan 45 line in DC characteristic i.e vout vs vin.

![19](https://user-images.githubusercontent.com/80052961/110241862-2268dc80-7f79-11eb-8354-6171a384eb8c.JPG)

Vm has a critical area because of 1. Vin = Vout 2.Both pmos and nmos arein the sat. region 3.if both nmos and pmos are turn on, there is a leakage current flow from power to gnd.The effect of changing the Wp/Wn ratio is to shift the transient region of the VTC. Increasing the width of the PMOS or the NMOS moves VM towards VDD or GND respectively.

**Layout:** Art of layout is a combination of euler's path and stick diagram.

using pull up network, we can build pull down network using duality theorem and demorgan's theorem.pull down network is complementary function of pull up network and thats where duality and demorgan's theorems comes into picture.

![22](https://user-images.githubusercontent.com/80052961/110242603-d4ee6e80-7f7c-11eb-8da3-964dbd20b2e7.JPG)
![23](https://user-images.githubusercontent.com/80052961/110242613-d91a8c00-7f7c-11eb-86cc-9fb5c37fa6d2.JPG)

The function of the circuit 			f = ((A+C).(B+D) + (E.F))'

**Layout using only stick diagram:** These are the problems comes into picture, if we are only using stick diagram to draw a layout.

											1. Congestion problem
											2. DRC rule issues
											3. Manufacturing issues
	
![26](https://user-images.githubusercontent.com/80052961/110243144-27c92580-7f7f-11eb-9494-64477cc3e173.JPG)

**Layout diagram using Euler's path and stick diagram:** stick diagram is a interface between circuit and final layout. Euler's path is defined as it is the path that covers each vertices atleast once. Optimize euler's path gives optimize layout. 

![27](https://user-images.githubusercontent.com/80052961/110243294-b5a51080-7f7f-11eb-860a-e189d91dcdb2.JPG)  Optimize euler's path A - C - E - F - D - B

![28](https://user-images.githubusercontent.com/80052961/110243384-2a784a80-7f80-11eb-8ac9-12fe3f9528e8.JPG)

**Design Rules Check (DRC):** Afte completion of the layout, you need to check the design rule. It is very important step for the post layout simulation and fabrication of a chip.

					polywidth				2λ
					
					metal width				3λ
					
					poly to active spaceing			1λ


**DAY3 LAB SKILLS**

**git clone** is a Git command line utility which is used to target an existing repository and create a clone, or copy of the target repository and change the directory to **ngspice** using the command **cd ngspice** . **ngspice** is a tool which is used for circuit simulation.The **cat** command allows us to create single or multiple files, view contain of file, concatenate files and redirect output in terminal or files. The *cat inv.spice* is open the file of inverter which shows the netlist description of the inverter and also it shows the pmos and nmos width(Wp,Wn),length(Lp,Ln) and load capacitance value i.e used in the design.

![D3SK1-MCQ5](https://user-images.githubusercontent.com/80052961/110209735-0ea77280-7eb4-11eb-8147-aad0fa93b299.JPG)


The **cd** command, also known as chdir (change directory), is a command-line shell command used to change the current working directory in various operating systems. It can be used in shell scripts and batch files.**cd ngspice_labs** command changes the directory into ngspice_labs. **ngspice** is a circuit simulation tool used to simulate the dc and transient characteristics of different gates/cells.**ngspice inv.spice** command open the simulataion tool and the design is inverter.**ngspice 1 -> run** is used to run the fn_prelayout.spice. **setplot tran1** is used to set the plot in dc mode. **plot** is a command, which is used to plot simulated waveforms with respect some input in this case input (50% of the power supply) i.e 1.25.This will open a plot with CMOS VTC and Blue 45 degree line

![D3SK1-MCQ8](https://user-images.githubusercontent.com/80052961/110209940-3fd47280-7eb5-11eb-995c-166a3a6eb778.JPG)

The below diagram shows the VTC characteristics of an inverter. The blueline(tan 45) intersecting the VTC curve that is called as switching threshold voltage(vm). swicthing threshold is the point where vin = vout and at which both p & n mos turned on and they are in saturation region.

![D3SK1-MCQ8_1](https://user-images.githubusercontent.com/80052961/110209947-44009000-7eb5-11eb-8062-d0de8b542873.JPG)

By using **leafpad inv.spice** command opens the inv.spice file and then edit the pmos width into 0.75u and then perform the dc simulation in ngspice simulation tool.The below figure shows that cmos model description and the w/l ratios of both pmos and nmos.After changing the width of pmos,the transfer characteristic curve shifts to right side.

![D3SK1-MCQ10_2](https://user-images.githubusercontent.com/80052961/110210206-93938b80-7eb6-11eb-8708-69b194d49e38.JPG)

The below images shows the all the commands and switching threshold value(vm) i.e x0

![D3SK1-MCQ10_1](https://user-images.githubusercontent.com/80052961/110210212-98f0d600-7eb6-11eb-9c8a-8528b43c0153.JPG)

![D3SK1-MCQ10](https://user-images.githubusercontent.com/80052961/110210219-9d1cf380-7eb6-11eb-9a4d-7b73d4d95dae.JPG)


The leafpad is a application which is used to open the files. ngspice is a circuit simulation tool used to simulate the dc and transient characteristics of different gates/cells.By using **leafpad inv.spice** command opens the inv.spice file and then edit the pmos width into 0.75u and then perform the dc simulation in ngspice simulation tool.The below figure shows that cmos model description and the w/l ratios of both pmos and nmos.After changing the width of pmos, **ngspice 1 -> run** is used to run the fn_prelayout.spice. **setplot tran1** is used to set the plot in dc mode. plot is a command, which is used to plot simulated waveforms with respect some input in this case input (50% of the power supply) i.e 1.25.This will open a plot with CMOS VTC and Blue 45 degree line

The below images shows the all the commands, which are used to open the simulation
![D3SK1-MCQ11_0](https://user-images.githubusercontent.com/80052961/110210758-3baa5400-7eb9-11eb-9add-06fdb1c135db.JPG)

The below figure shows the values of input fall time at 50% of power supply (1st x0) and output rise time at 50% of power supply(2nd x0)

![D3SK1-MCQ11](https://user-images.githubusercontent.com/80052961/110210768-4369f880-7eb9-11eb-9426-29ea95730bbb.JPG)

The below image shows the trainsient charecters of an inverter if input = 0v then output =2.5v(in this case) . it depends on the technolgy.

![D3SK1-MCQ11_1](https://user-images.githubusercontent.com/80052961/110210782-49f87000-7eb9-11eb-8596-eef1981181a3.JPG)


The cd command, also known as chdir (change directory), is a command-line shell command used to change the current working directory in various operating systems. It can be used in shell scripts and batch files. **ngspice** is a circuit simulation tool used to simulate the dc and transient characteristics of different gates/cells.Change the directory to ngspice_labs and then open simulation tool with the command - **ngspice fn_prelayout.spice** . **ngspice 1** -> run is used to run the fn_prelayout.spice. **setplot tran1** is used to set the plot in transient mode. **plot** is a command, which is used to plot simulated waveforms with respect some input in this case input (50% of the power supply) i.e 1.25.

The below figure shows the respective commands shown above:

![D3SK2-MCQ1_0](https://user-images.githubusercontent.com/80052961/110228713-4dc3db00-7f29-11eb-9d89-a1b94f4b17d8.JPG)

The below figure shows the value of x0 at the intersection of horizontal blue line(50% of the power supply) and middle rising waveform (50% of power supply):

![D3SK2-MCQ1](https://user-images.githubusercontent.com/80052961/110228717-53212580-7f29-11eb-88fb-e4a7858e611b.JPG)

The below image shows transient waveform:

![D3SK2-MCQ1_1](https://user-images.githubusercontent.com/80052961/110228725-5caa8d80-7f29-11eb-83f8-d1ca78217539.JPG)

![D3SK2-MCQ1_2](https://user-images.githubusercontent.com/80052961/110228732-646a3200-7f29-11eb-9587-bade369c41e1.JPG)


The below figure shows the value of x0 at the intersection of horizontal blue line(50% of the power supply) and middle rising waveform (50% of power supply):

![D3SK2-MCQ2](https://user-images.githubusercontent.com/80052961/110229445-823a9580-7f2f-11eb-906d-3e78c820ff75.JPG)
![D3SK2-MCQ2_1](https://user-images.githubusercontent.com/80052961/110229447-85ce1c80-7f2f-11eb-8346-61efc60c450c.JPG)


The rise/fall time values of 10% and 90% are calculated based on an algorithm, which looks at the mean power above and below the 50% points of the rise/fall times. The pulse width is based on the 50% points in linear power (W) mode.

![D3SK2-MCQ3](https://user-images.githubusercontent.com/80052961/110229523-17d62500-7f30-11eb-9ddb-0a111f40a84c.JPG)


**cd ngspice_labs** is used the change the directory to ngspice_labs. **magic** is a tool which is used to construct the layout.Integrated circuit layout, also known IC layout, IC mask layout, or mask design, is the representation of an integrated circuit in terms of planar geometric shapes which correspond to the patterns of metal, oxide, or semiconductor layers that make up the components of the integrated circuit. **source draw_fn.tcl** is run the drwa_fn tcl file and it draw a layout for the function. The layout consist of polysilicon straps, n- well, metal contacts with width 3lambda and etc. 

The below figure shows the command which are used to open magic tool with a technology file. The technology file consist of all the design rules that must be satisfy to draw a layout.

![D3SK3-MCQ3_1](https://user-images.githubusercontent.com/80052961/110229655-1a854a00-7f31-11eb-8817-fb6d065130f4.JPG)

![D3SK3-MCQ3_0](https://user-images.githubusercontent.com/80052961/110229663-24a74880-7f31-11eb-9934-ca3912959f0f.JPG)

The below image shows the layout diagram of a function. In the layout, the pink color strips are polysilicon strips and bottom of the layout shows the gnd terminal and it has contacts which are used to connect the ground terminal.

![D3SK3-MCQ3](https://user-images.githubusercontent.com/80052961/110229666-28d36600-7f31-11eb-9300-a52158cd22c4.JPG)

**cd ngspice_labs** is used the change the directory to ngspice_labs. **magic** is a tool which is used to construct the layout.Integrated circuit layout, also known IC layout, IC mask layout, or mask design, is the representation of an integrated circuit in terms of planar geometric shapes which correspond to the patterns of metal, oxide, or semiconductor layers that make up the components of the integrated circuit.The layout consist of polysilicon straps, n- well, metal contacts with width 3lambda and etc. The below figure shows the command which are used to open magic tool with a technology file. The technology file consist of all the design rules that must be satisfy to draw a layout.

The below figure shows the above commands which are used to open magic tool:
![D3SK3-MCQ4_0](https://user-images.githubusercontent.com/80052961/110229830-405f1e80-7f32-11eb-912d-5879f368f31e.JPG)

The below figure shows the layout of a function and select the whole to find the area of the design.
![D3SK3-MCQ4_1](https://user-images.githubusercontent.com/80052961/110229836-48b75980-7f32-11eb-9bf1-9deaf952d281.JPG)

In tkcon window type **box**,after selecting the whole chip then only it shows the area of the design in microns.
![D3SK3-MCQ4](https://user-images.githubusercontent.com/80052961/110229842-4e14a400-7f32-11eb-8ef9-67d9b7872db8.JPG)


After sourcing the draw_fn.tcl. we will extract all files and also spice files by using the commands extract all and eext2spice. From ther we fn.postlayout.spice, then this file is edited as it doesn't consists of vdd and gnd info. For the stimulus to obtain those were copied from the fn_layout and added to the fn_postlayout and then the simulation is done.

![D3SK3-MCQ5_0](https://user-images.githubusercontent.com/80052961/110229964-473a6100-7f33-11eb-8e24-c71eaea99f24.JPG)

Extract all command is used to extract all parasitics and it creates a file name fn_postlayout.ext

![D3SK3-MCQ5_3](https://user-images.githubusercontent.com/80052961/110230046-f5460b00-7f33-11eb-8f2a-4831d5c765f5.JPG)

The below figure shows the transient response:
![D3SK3-MCQ5_1](https://user-images.githubusercontent.com/80052961/110229976-676a2000-7f33-11eb-8c24-97b9c36ce3d1.JPG)

1st x0 shows the rise time and 2nd x0 is the fall time of the above transient analysis:

![D3SK3-MCQ5](https://user-images.githubusercontent.com/80052961/110229966-50c3c900-7f33-11eb-867c-eb2f1101480f.JPG)

## *Day 4 - Pre-Layout Timing Analysis and Importance of Good Clock Tree*

**Delay Table:** At every level, Each buffer varies output load capacitance and input transitions/slew. in simple way, we have varying input transition at input buffer and varying output load at output load at the output buffer.so that we have different delays for one buffer/cell and solution for that is delay table. **Delay Table** is the representation of delays of a particular cell while varying the input slew and output load.

**Timing Analysis:**

**setup timing analysis:**  The setup time is the interval before the clock where the data must be held stable.

![29](https://user-images.githubusercontent.com/80052961/110247846-47b71400-7f94-11eb-8ab5-0fee76ee8795.JPG)

**hold timing analysis:** The hold time is the interval after the clock where the data must be held stable. Hold time can be negative, which means the data can change slightly before the clock edge and still be properly captured.

![30](https://user-images.githubusercontent.com/80052961/110248001-fa877200-7f94-11eb-883a-c284b751a639.JPG)

**Clock Tree Routing:** It is very important setp for the performance. H - tree is used to build the clock tree. The main objective of clock tree routing is minimazation of the skew. In clock routing, we clock buffers. there is a differnce in clock buffer and normal buffer that clock buffer have equal rise and fall time but in case of normal buffer it's not.

**cross talk:** Crosstalk is a phenomenon, by which a logic transmitted in vlsi circuit or a net/wire creates undesired effect on the neighbouring circuit or nets/wires, due to capacitive coupling. If there is a crosstalk between two nets then all the parameters(input transition/slew ) are deteriorates.

![31](https://user-images.githubusercontent.com/80052961/110248434-1e4bb780-7f97-11eb-8cad-b511a0fa1ecf.JPG)

**Shielding:** shielding is placing ground or power lines at the sides of a. victim signal line to reduce noise and delay uncertainty. clock nets are considered as critical nets, by shielding the clock net we will protect the clock net from the outside world.


**DAY4 LAB SKILLS:**

git clone is a Git command line utility which is used to target an existing repository and create a clone, or copy of the target repository and **ngspice** is a tool which is used for circuit simulation and change the directory to ngspice_labs.The **cat** command allows us to create single or multiple files, view contain of file, concatenate files and redirect output in terminal or files and **cat inv_tran.spice**- it open the inv_tran.spice file. The file contains the info of the pmos and nmos that is width,length and the input pulse signal shows the rise slew and fall slew values.

The below figure shows the netlist description of a inverter. in that image, vin is a pulse with time period = 2ns,pulse width = 1ns,rise and fall slew = 10ps.

![D4SK1-MCQ6](https://user-images.githubusercontent.com/80052961/110230321-3808e280-7f36-11eb-8988-8236347e8b81.jpg)


The below figure shows the netlist description of a inverter. in that image, cload represents the load capacitance of 10fF.

![D4SK1-MCQ7_2](https://user-images.githubusercontent.com/80052961/110230453-165c2b00-7f37-11eb-9a9c-78af1713841a.jpg)

The below figure shows the transient response of a inverter. from that, we calculate rise time delay. It is difference between rise time of output(1st x0) to fall time input(2nd x0).

![D4SK1-MCQ7_1](https://user-images.githubusercontent.com/80052961/110230463-207e2980-7f37-11eb-8901-d5a840113e79.jpg)

![D4SK1-MCQ7](https://user-images.githubusercontent.com/80052961/110230466-2542dd80-7f37-11eb-96fd-a0ce691339d5.jpg)


git clone is a Git command line utility which is used to target an existing repository and create a clone, or copy of the target repository and **ngspice** is a tool which is used for circuit simulation and change the directory to ngspice_labs.The **cat** command allows us to create single or multiple files, view contain of file, concatenate files and redirect output in terminal or files and **cat inv_tran.spice**- it open the inv_tran.spice file. The file contains the info of the pmos and nmos that is width,length and the input pulse signal shows the rise slew and fall slew values. **Leafpad** used to open the file and then we change the load value to 20fF.


![D4SK1-MCQ8](https://user-images.githubusercontent.com/80052961/110230595-1a3c7d00-7f38-11eb-95ee-8281914419d7.jpg)

The image is after editing the output load capacitance.

![D4SK1-MCQ8_1](https://user-images.githubusercontent.com/80052961/110230600-20325e00-7f38-11eb-8d66-c47030ba0d44.jpg)

It is the transient response of the inverter:

![D4SK1-MCQ8_2](https://user-images.githubusercontent.com/80052961/110230611-2cb6b680-7f38-11eb-95c1-ce373b657561.jpg)

rise delay is difference between rise time of output(2nd x0) to fall time input(1st x0).

![D4SK1-MCQ8_0](https://user-images.githubusercontent.com/80052961/110230616-350ef180-7f38-11eb-9c7a-6378915be1c8.jpg)


**leafpad /usr/local/share/qflow/tech/osu018/osu018_stdcells.lib** opens the standard cell library with the technolgy of 180nm. The file will shows all info like slew_upper_thershold_pct_fall,output_threshold_pct_rise, various sizes of cells and their timing info.

![D4SK2-MCQ6_1](https://user-images.githubusercontent.com/80052961/110230767-2ffe7200-7f39-11eb-8e97-8c11287f3d12.jpg)

The below figure shows the library file of 180nm technolgy. It contains all standard cells like and,or,inv,mux and etc.

![D4SK2-MCQ6](https://user-images.githubusercontent.com/80052961/110230772-38ef4380-7f39-11eb-8e26-dbc51b1e2f09.jpg)
					
What are the 2 variables of "delay_template_5x5"?

![D4SK2-MCQ8](https://user-images.githubusercontent.com/80052961/110230913-42c57680-7f3a-11eb-8542-bd7a51ede398.jpg)
					
Which cell delay table in line number 2943?

![D4SK2-MCQ9](https://user-images.githubusercontent.com/80052961/110230945-920ba700-7f3a-11eb-942f-47667c18acb6.jpg)
					
Which delay template is used for INVX1?

![D4SK2-MCQ10](https://user-images.githubusercontent.com/80052961/110230973-c4b59f80-7f3a-11eb-851c-e40637e4786d.jpg)


The **cd** command, also known as chdir (change directory), is a command-line shell command used to change the current working directory and change the directory to vsdflow/my_picorv32. **sta command** is used to run the prelayout.conf file.

![D4SK2-MCQ11_1](https://user-images.githubusercontent.com/80052961/110231093-a56b4200-7f3b-11eb-994a-5467e595a059.jpg)

The **leafpad picorv32.sdc** is used to open picorv32.sdc . In sdc, we create a clock with period of 2.5ns with pulse width 1.25ns and the clock name is clk.

![11](https://user-images.githubusercontent.com/80052961/110231106-b1570400-7f3b-11eb-84b9-81571773f03f.jpg)

**leafpad** is used to open and then modify the contents with the below commands in prelayout_sta.conf. **read_liberty /usr/local/share/qflow/tech/osu018/osu018_stdcells.lib** is command used to read the library file in the given path. **read_verilog synthesis/picorv32.rtlnopwr.v** is a command read the verilog file in the given path. **read_sdc picorv32.sdc** it reads the synopsys design constraints. **report_checks** it reports the timing info like slack,data arrival time and required time.

![12](https://user-images.githubusercontent.com/80052961/110231111-b61bb800-7f3b-11eb-8f9f-e6c560279a00.JPG)

The below image shows the setup timing analysis. it shows the data rquired time, data arrival time and slack. slack is the difference to data requirerd time to data arrival time.

![D4SK2-MCQ11_2](https://user-images.githubusercontent.com/80052961/110231133-c895f180-7f3b-11eb-90de-ff84e8b08d84.jpg)


**% report_checks -digits 4** is a command used to check the timing info with 4 digits.

What is the data arrival time and required time?

![D4SK2-MCQ12_1](https://user-images.githubusercontent.com/80052961/110231405-9dac9d00-7f3d-11eb-9d0c-17f2d5e1f28e.jpg)

![D4SK2-MCQ12](https://user-images.githubusercontent.com/80052961/110231431-b452f400-7f3d-11eb-9fdb-9bfe51469263.jpg)


The **cd** command, also known as chdir (change directory), is a command-line shell command used to change the current working directory and change the directory to vsdflow/my_picorv32. **sta command** is used to run the prelayout.conf file.The **leafpad picorv32.sdc** is used to open picorv32.sdc . In sdc, we create a clock with period of 2.5ns with pulse width 1.25ns and the clock name is clk.**leafpad** is used to open and then modify the contents with the below commands in prelayout_sta.conf. **read_liberty /usr/local/share/qflow/tech/osu018/osu018_stdcells.lib** is command used to read the library file in the given path. **read_verilog synthesis/picorv32.rtlnopwr.v** is a command read the verilog file in the given path. **read_sdc picorv32.sdc** it reads the synopsys design constraints. **set_propagated_clock [all_clocks]** is a command which set the clock propagates through all clocks. **report_checks** it reports the timing info like slack,data arrival time and required time.

What is the SLACK value after clock propagation ?

These are the commands which are used to open sta. Static timing analysis (STA) is a method of validating the timing performance of a design by checking all possible paths for timing violations.

![D4SK4-MCQ2_1](https://user-images.githubusercontent.com/80052961/110231569-7dc9a900-7f3e-11eb-89c0-d2d99d75555f.jpg)

![D4SK4-MCQ2_2](https://user-images.githubusercontent.com/80052961/110231580-8fab4c00-7f3e-11eb-9373-9ae5a45b3204.jpg)

The below figure shows the slack after the propagation of the clock i.e post static timing analysis.

![D4SK4-MCQ2 ](https://user-images.githubusercontent.com/80052961/110231587-9fc32b80-7f3e-11eb-98db-b7798c7a22c0.jpg)


What is launch clock network delay or clock network delay propagated ?

![13](https://user-images.githubusercontent.com/80052961/110231817-262c3d00-7f40-11eb-93ee-44980d912635.JPG)

What is the capture clock network delay?

![14](https://user-images.githubusercontent.com/80052961/110231830-36dcb300-7f40-11eb-99e4-0e690881ead2.jpg)

The **cd** command, also known as chdir (change directory), is a command-line shell command used to change the current working directory and change the directory to vsdflow/my_picorv32. **sta command** is used to run the prelayout.conf file.The **leafpad picorv32.sdc** is used to open picorv32.sdc . In sdc, we create a clock with period of 2.5ns with pulse width 1.25ns and the clock name is clk.**leafpad** is used to open and then modify the contents with the below commands in prelayout_sta.conf. **read_liberty /usr/local/share/qflow/tech/osu018/osu018_stdcells.lib** is command used to read the library file in the given path. **read_verilog synthesis/picorv32.rtlnopwr.v** is a command read the verilog file in the given path. **read_sdc picorv32.sdc** it reads the synopsys design constraints. **set_propagated_clock [all_clocks]** is a command which set the clock propagates through all clocks. **report_checks -path_delay min -digits 4** it reports the timing info like slack,data arrival time and required time of hold analysis.
				
What is library hold time and hold slack? 

Setup and hold slack is defined as the difference between data required time and data arrival time. setup slack= Data Required Time - Data Arrival Time. hold slack= Data Arrival Time - Data Required Time.

![D4SK4-MCQ5](https://user-images.githubusercontent.com/80052961/110231887-6b506f00-7f40-11eb-9ade-40f1461ca9a6.jpg)


## *Day 5 - Final Steps for RTL2GDS*

**Routing:** In the vlsi design cycle, routing follows cell placement. To interconnect all the pins according to the specification of nets its konwn as **routing**. once routing is completed, precise paths are defined on the layout surface on which conductors carrying electrical signals are run. The main objective of routing is to minimize the area required for routing.

There are 3 types of routing:

   1. Grid/area routing

   2. Global routing
				
   3. Detailed routing
				
**Design Rule Check:** These design rules in the technology file. for every technology, the design rules changes.

There 3 typical design rules for the pairs of wires, which are running parallel.

   - Wire Width : The wire has min. width or more than that is okay

   - wire pitch: The centre to centre distance between 2 wires called as wire pitch.

   - wire spacing: wire to wire maintain min.spacing or more than that

If signal short occur, we route one of the signal into another metal layer.

**Parasitic Extraction**: 

Each and evry wire has got finite resistanc and capacitance and we have to extract it and then provides to analysis tool. Parasitic extraction represent in a special format known as **SPEF Format**. SPEF full form is Standard Parasitic Exchange Format

** SPEF : standard parasitic exchange format** 
IEEE 1481 - 1999

The above two lines are SPEF Header

![32](https://user-images.githubusercontent.com/80052961/110249097-63bdb400-7f9a-11eb-9eda-53edc7d97d78.JPG)


**DAY5 LAB SKILLS**

The cd command, also known as chdir (change directory), is a command-line shell command used to change the current working directory and the current directory is /vsdflow/my_picorv32 and then start the routing for picorv32 using the command **qflow route picorv32**. After completing the 3 stages of routing,open sta for picorv32. BACKANNO -- Annotate the Subcircuit Pin Names to the Port Currents. ... raw file that can be used to refer to port currents by the pin name. This allows you to cross probe pin currents by clicking on the symbol's pin and then open the log file of sta for the design and it shows the pre-layout frequency

![D5SK2 - MCQ1_1](https://user-images.githubusercontent.com/80052961/110232410-82449080-7f43-11eb-9191-dcf378a1a3a2.jpg)

					
![D5SK2 - MCQ1_2](https://user-images.githubusercontent.com/80052961/110232422-8c668f00-7f43-11eb-86ab-490fdf8f1d99.jpg)

It is the max. frequency in prelayout and which is 313.676MHz

![D5SK2 - MCQ1](https://user-images.githubusercontent.com/80052961/110232437-a7390380-7f43-11eb-841d-d086092856c4.jpg)


The cd command, also known as chdir (change directory), is a command-line shell command used to change the current working directory and the current directory is /vsdflow/my_picorv32 and then start the routing for picorv32 using the command **qflow route picorv32**. After completing the 3 stages of routing,open sta for picorv32. BACKANNO -- Annotate the Subcircuit Pin Names to the Port Currents. ... raw file that can be used to refer to port currents by the pin name. This allows you to cross probe pin currents by clicking on the symbol's pin and then open the log file of sta for the design.without completion of routing the post layout frequency is not shown in the file.**log/post_sta.log** shows the maximum frequency of the postlayout.

![D5SK2 - MCQ2_2 - Copy](https://user-images.githubusercontent.com/80052961/110232464-cafc4980-7f43-11eb-9a89-601d3c3b5a77.jpg)

![D5SK2 - MCQ2_1](https://user-images.githubusercontent.com/80052961/110232469-d2bbee00-7f43-11eb-8907-e72f981b2d69.jpg)

It is the max. frequency in postlayout and which is 293.556MHz

![D5SK2 - MCQ2](https://user-images.githubusercontent.com/80052961/110232471-d64f7500-7f43-11eb-938c-0ce84aa0c876.jpg)


**ACKNOWLEDGEMENT:**

- [Kunal Ghosh](https://github.com/kunalg123) Co-founder of VLSI System Design (VSD) Corp. Pvt. Ltd.
