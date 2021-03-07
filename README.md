# VSD PHYSICAL DESIGN USING OPEN SOURCE TOOLS

**DAY1 LAB:**

**D1SK4 – MCQ3:**

1.Click on VSD IAT, Go to "Lab Instances". Then under "Links", click on the "link" 	icon. Click bottom left, System tools > LXTerminal.
2.Now type the command "yosys". What do you see next?

yosys is synthesis tool which is used to convert the rtl code into gate level netlist. To open the yosys tool, we use the command yosys. 

![d1sk4](https://github.com/vishnuvardhan-k/vsd-physical-design-using-open-source-tools/blob/main/Day%201/D1SK4-MCQ3.JPG)

**D1SK4 - MCQ4:**

1.Click on VSD IAT, Go to "Lab Instances". Then under "Links", click on the "link" icon. Click bottom left, System tools > LXTerminal.
Type "which sta" and what path do you see the sta tool to be linked to?

“which” is command used to shows the loction/directory path of tool/folder

![D1SK4-MCQ4](https://user-images.githubusercontent.com/80052961/110207735-8329e380-7eab-11eb-9d79-2085d53d23c3.JPG)

**D1SK4 – MCQ5:**

Type below command on terminal from current working directory

		git clone https://github.com/kunalg123/vsdflow.git

==> git clone is a Git command line utility which is used to target an existing repository and create a clone, or copy of the target repository.

What is last line as you see in the terminal?

![D1SK4-MCQ5](https://user-images.githubusercontent.com/80052961/110207999-94bfbb00-7eac-11eb-841f-14d60a70ad69.JPG)

**D1SK4 – MCQ6:**

Type below commands on terminal

					cd vsdflow					                         

					./vsdflow spi_slave_design_details.csv	

					ls -ltr outdir_spi_slave/			                 

					ls -ltr outdir_spi_slave | wc

==> The cd command, also known as chdir (change directory), is a command-line shell command used to change the current working directory in various operating systems. It can be used in shell scripts and batch files.cd vsdflow command is usedchange the directory to vsdflow folder. ls -ltr shows list files/folders.

This will give you 3 numbers in one row, where 1st number represents number of files. you will see total 17 number of lines beacuse 1st line will give total number and the rest 16 are the number of flies.

What are the number of files you see?

![D1SK4-MCQ6](https://user-images.githubusercontent.com/80052961/110208038-d3557580-7eac-11eb-8349-8ddb453254bd.JPG)

**D1SK4 – MCQ7:**

					cd outdir_spi_slave

					qflow display spi_slave	

					on tkcon window, type “box” 

What is the output area in microns ?

1st command change the directory to outdir_spi_slave and the next command open and display the qflow manager where you do preference,synthesis,placement and so on.Qflow(complete tool chain) is a complete tool chain for synthesizing digital circuits starting from verilog source and ending in physical layout for a specific target fabrication process

These commands open two windows 1.layout window
                                2. Tkcon window

![D1SK4-MCQ7_1](https://user-images.githubusercontent.com/80052961/110208575-04827580-7eae-11eb-84a3-37c0a0e6e84c.JPG)

1st select the chip area and then type the command box in tkcon window.it shows the selected area in microns.

![D1SK4-MCQ7_2](https://user-images.githubusercontent.com/80052961/110208587-1b28cc80-7eae-11eb-9d28-f3410f268a2f.JPG)

![D1SK4-MCQ7](https://user-images.githubusercontent.com/80052961/110208597-23810780-7eae-11eb-9dca-3ee02319f153.JPG)

**D1SK4 – MCQ8:**  

Type below commands

					cd

					cd vsdflow			

					mkdir my_picorv32	

					cd my_picorv32				

					mkdir source synthesis layout		

					cp ~/vsdflow/Verilog/picorv32.v/source/.	

					qflow gui &	

cd vsdflow is a command change the directory to vsdflow, mkdir is a command create the folder, cd my_picorv32	- change the directory to my_picorv32, mkdir source synthesis layout - create folders source, synthesis and layout, cp ~/vsdflow/Verilog/picorv32.v/source/. - copy the Verilog file i.e picorv32 from source to vsdflow, qflow gui &	- it open qflow manager in a graphical user interface.

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
 
 **DAY2 LAB**
 
**D2SK4 - MCQ5**

Type below command

					cd

					cd vsdflow/my_picorv32

					qflow display picorv32 &
					

This will open layout and tkcon window In the layout window and then select all chip and then type the command in tkcon window "box".

What is the area of you chip in microns?

![qflow](https://user-images.githubusercontent.com/80052961/110209245-6b555e00-7eb1-11eb-80f5-0d04dfbab6c4.JPG)

After entering the commands shown above, it opens a qflow manager and we set technology = osu018, Verilog source = picorv32 and verilog module = picorv32. Click on start button opposite the preparation. If it is okay, then proceed to synthesis. Click on okay opposite to synthesis, it opens a synthesis log file. Synthesis file shows the number of cells, number of flops and etc.

![placement2](https://user-images.githubusercontent.com/80052961/110209263-7c9e6a80-7eb1-11eb-98fa-f708573c7cfe.JPG)

1st select the chip area and then type the command box in tkcon window.it shows the selected area in microns.

![layoutofpicorv32](https://user-images.githubusercontent.com/80052961/110209279-89bb5980-7eb1-11eb-87e6-66ee41f5fe24.JPG)

The below images shows the pins(clk,rstn) in bottom of chip.first we group them and then select the pin arrange to bottom.

![bottom_group](https://user-images.githubusercontent.com/80052961/110209283-8cb64a00-7eb1-11eb-88e8-b436d1196388.JPG)

The below image shows the chip area which is selected in the layoutsection.

![chipsize](https://user-images.githubusercontent.com/80052961/110209286-917afe00-7eb1-11eb-8ee8-1e10961bd351.JPG)

**DAY3 LAB**

**D3SK1 - MCQ5,6,7**

Type below commands in terminal

					cd

					git clone https://github.com/kunalg123/ngspice_labs.git

					cd ngspice_labs

					cat inv.spice

What is the width of PMOS,NM0S transistor and wp/wn?

git clone is a Git command line utility which is used to target an existing repository and create a clone, or copy of the target repository and ngspice is a tool which is used for circuit simulation.The cat command allows us to create single or multiple files, view contain of file, concatenate files and redirect output in terminal or files.

![D3SK1-MCQ5](https://user-images.githubusercontent.com/80052961/110209735-0ea77280-7eb4-11eb-8147-aad0fa93b299.JPG)

**D3SK1 - MCQ8**

Type below commands

					cd

					cd ngspice_labs

					ngspice inv.spice

					There will be terminal like below

					ngspice 1 ->

					On the above ngspice terminal, type below commands

					ngspice 1 -> run

					ngspice 1 -> setplot dc1

					ngspice 1 -> plot out in

					Click on the intersection of Blue line and CMOS VTC.

					Go to terminal

What does "x0" value lies between?

The cd command, also known as chdir (change directory), is a command-line shell command used to change the current working directory in various operating systems. It can be used in shell scripts and batch files. ngspice is a circuit simulation tool used to simulate the dc and transient characteristics of different gates/cells. ngspice 1 -> run is used to run the fn_prelayout.spice. setplot tran1 is used to set the plot in dc mode. plot is a command, which is used to plot simulated waveforms with respect some input in this case input (50% of the power supply) i.e 1.25.This will open a plot with CMOS VTC and Blue 45 degree line

![D3SK1-MCQ8](https://user-images.githubusercontent.com/80052961/110209940-3fd47280-7eb5-11eb-995c-166a3a6eb778.JPG)

The below diagram shows the VTC characteristics of an inverter. The blueline(tan 45) intersecting the VTC curve that is called as switching threshold voltage(vm). swicthing threshold is the point where vin = vout and at which both p & n mos turned on and they are in saturation region.

![D3SK1-MCQ8_1](https://user-images.githubusercontent.com/80052961/110209947-44009000-7eb5-11eb-8062-d0de8b542873.JPG)

**D3SK1 - MCQ10**

Type below command

					leafpad inv.spice

Edit the width of PMOS to 0.75u and save the file and exit the file

Repeat experiment given in D3SK1 - MCQ8

Where does the switching threshold lies between?

The below figure shows that cmos model description and the w/l ratios of both pmos and nmos.After changing the width of pmos,the transfer characteristic curve shifts to right side.

![D3SK1-MCQ10_2](https://user-images.githubusercontent.com/80052961/110210206-93938b80-7eb6-11eb-8708-69b194d49e38.JPG)

The below images shows the all the commands and switching threshold value(vm) i.e x0

![D3SK1-MCQ10_1](https://user-images.githubusercontent.com/80052961/110210212-98f0d600-7eb6-11eb-9c8a-8528b43c0153.JPG)

![D3SK1-MCQ10](https://user-images.githubusercontent.com/80052961/110210219-9d1cf380-7eb6-11eb-9a4d-7b73d4d95dae.JPG)

**D3SK1 - MCQ11**

Open file called "inv_tran.spice" using below command

					leafpad inv_tran.spice

Change PMOS width to 0.75u, Save and Close

Type below commands for transient simulations

					ngspice inv_tran.spice

					ngspice 1 -> run

					ngspice 1 -> setplot tran1

					ngspice 1 -> plot out in

What is the rise delay? 

The leafpad is a application which is used to open the files. ngspice is a circuit simulation tool used to simulate the dc and transient characteristics of different gates/cells. ngspice 1 -> run is used to run the fn_prelayout.spice. setplot tran1 is used to set the plot in dc mode. plot is a command, which is used to plot simulated waveforms with respect some input in this case input (50% of the power supply) i.e 1.25.This will open a plot with CMOS VTC and Blue 45 degree line

The below images shows the all the commands, which are used to open the simulation
![D3SK1-MCQ11_0](https://user-images.githubusercontent.com/80052961/110210758-3baa5400-7eb9-11eb-9add-06fdb1c135db.JPG)

The below figure shows the values of input fall time at 50% of power supply (1st x0) and output rise time at 50% of power supply(2nd x0)

![D3SK1-MCQ11](https://user-images.githubusercontent.com/80052961/110210768-4369f880-7eb9-11eb-9426-29ea95730bbb.JPG)

The below image shows the trainsient charecters of an inverter if input = 0v then output =2.5v(in this case) . it depends on the technolgy.

![D3SK1-MCQ11_1](https://user-images.githubusercontent.com/80052961/110210782-49f87000-7eb9-11eb-8596-eef1981181a3.JPG)

**D3SK2 - MCQ1**

					cd

					cd ngspice_labs

					ngspice fn_prelayout.spice

					ngspice 1 -> run

					ngspice 1 -> setplot tran1

					ngspice 1 -> plot out 1.25

What is the value of X0 at the intersection of horizontal blue line and middle rising waveform?

The cd command, also known as chdir (change directory), is a command-line shell command used to change the current working directory in various operating systems. It can be used in shell scripts and batch files. ngspice is a circuit simulation tool used to simulate the dc and transient characteristics of different gates/cells. ngspice 1 -> run is used to run the fn_prelayout.spice. setplot tran1 is used to set the plot in transient mode. plot is a command, which is used to plot simulated waveforms with respect some input in this case input (50% of the power supply) i.e 1.25.

The below figure shows the respective commands shown above:

![D3SK2-MCQ1_0](https://user-images.githubusercontent.com/80052961/110228713-4dc3db00-7f29-11eb-9d89-a1b94f4b17d8.JPG)

The below figure shows the value of x0 at the intersection of horizontal blue line(50% of the power supply) and middle rising waveform (50% of power supply):

![D3SK2-MCQ1](https://user-images.githubusercontent.com/80052961/110228717-53212580-7f29-11eb-88fb-e4a7858e611b.JPG)

The below image shows transient waveform:
![D3SK2-MCQ1_1](https://user-images.githubusercontent.com/80052961/110228725-5caa8d80-7f29-11eb-83f8-d1ca78217539.JPG)

![D3SK2-MCQ1_2](https://user-images.githubusercontent.com/80052961/110228732-646a3200-7f29-11eb-9587-bade369c41e1.JPG)

**D3SK2 - MCQ2**

Repeat all steps in D3SK2 - MCQ1

What is the value of X0 at intersection of horizontal blue line and middle falling waveform ?

The below figure shows the value of x0 at the intersection of horizontal blue line(50% of the power supply) and middle rising waveform (50% of power supply):

![D3SK2-MCQ2](https://user-images.githubusercontent.com/80052961/110229445-823a9580-7f2f-11eb-906d-3e78c820ff75.JPG)
![D3SK2-MCQ2_1](https://user-images.githubusercontent.com/80052961/110229447-85ce1c80-7f2f-11eb-8346-61efc60c450c.JPG)

**D3SK2 - MCQ3**

Pulsewidth is defined by the X0 value obtained in "D3SK2 - MCQ2" - "D3SK2 - MCQ1" 

What is the pulsewidth ?

The rise/fall time values of 10% and 90% are calculated based on an algorithm, which looks at the mean power above and below the 50% points of the rise/fall times. The pulse width is based on the 50% points in linear power (W) mode.

![D3SK2-MCQ3](https://user-images.githubusercontent.com/80052961/110229523-17d62500-7f30-11eb-9ddb-0a111f40a84c.JPG)

**D3SK3 - MCQ3**

Type below commands

					cd
					
					cd ngspice_labs
					
					magic -T min2.tech
This will open magic layout window and tkcon window

Go to tkcon window and type below command

					source draw_fn.tcl
					
In layout window, how many nsubstratecontact and how many polysilicon strips you observe?

magic is a tool which is used to construct the layout.Integrated circuit layout, also known IC layout, IC mask layout, or mask design, is the representation of an integrated circuit in terms of planar geometric shapes which correspond to the patterns of metal, oxide, or semiconductor layers that make up the components of the integrated circuit.
source draw_fn.tcl is run the drwa_fn tcl file.

The below figure shows the command which are used to open magic tool with a technology file. The technology file consist of all the design rules that must be satisfy to draw a layout.

![D3SK3-MCQ3_1](https://user-images.githubusercontent.com/80052961/110229655-1a854a00-7f31-11eb-8817-fb6d065130f4.JPG)

![D3SK3-MCQ3_0](https://user-images.githubusercontent.com/80052961/110229663-24a74880-7f31-11eb-9934-ca3912959f0f.JPG)

The blow image shows the layout diagram of a function. In the layout, the pink color strips are polysilicon strips and bottom of the layout shows the gnd terminal and it has contacts which are used to connect the ground terminal.

![D3SK3-MCQ3](https://user-images.githubusercontent.com/80052961/110229666-28d36600-7f31-11eb-9300-a52158cd22c4.JPG)

**D3SK3 - MCQ4**

Type below command

					cd
					
					cd ngspice_labs
					
					magic -T min2.tech fn_postlayout.mag &
					
What is the area of this design?

The below figure shows the above commands which are used to open magic tool:
![D3SK3-MCQ4_0](https://user-images.githubusercontent.com/80052961/110229830-405f1e80-7f32-11eb-912d-5879f368f31e.JPG)

The below figure shows the layout of a function and select the whole to find the area of the design.
![D3SK3-MCQ4_1](https://user-images.githubusercontent.com/80052961/110229836-48b75980-7f32-11eb-9bf1-9deaf952d281.JPG)

In tkcon window type **box**,after selecting the whole chip then only it shows the area of the design in microns.
![D3SK3-MCQ4](https://user-images.githubusercontent.com/80052961/110229842-4e14a400-7f32-11eb-8ef9-67d9b7872db8.JPG)

**D3SK3 - MCQ5**

Type below command

					cd
					
					cd ngspice_labs
					
					magic -T min2.tech fn_postlayout.mag &
					
it will layout window and tkcon window. In tkcon window , type these commands

					% extract all
					%ext2spice

We don't have Gnd, but we have 0. Please modify postlayout spice netlist accordingly

What is the value of X0 at intersection rising & falling waveform and intersection of horizontal blue line?

![D3SK3-MCQ5_0](https://user-images.githubusercontent.com/80052961/110229964-473a6100-7f33-11eb-8e24-c71eaea99f24.JPG)

Extract all command is used to extract all parasitics and it creates a file name fn_postlayout.ext

![D3SK3-MCQ5_3](https://user-images.githubusercontent.com/80052961/110230046-f5460b00-7f33-11eb-8f2a-4831d5c765f5.JPG)

The below figure shows the transient response:
![D3SK3-MCQ5_1](https://user-images.githubusercontent.com/80052961/110229976-676a2000-7f33-11eb-8c24-97b9c36ce3d1.JPG)

1st x0 shows the rise time and 2nd x0 is the fall time of the above transient analysis:

![D3SK3-MCQ5](https://user-images.githubusercontent.com/80052961/110229966-50c3c900-7f33-11eb-867c-eb2f1101480f.JPG)









