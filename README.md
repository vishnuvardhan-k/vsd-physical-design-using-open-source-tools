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

git clone is a Git command line utility which is used to target an existing repository and create a clone, or copy of the target repository.

What is last line as you see in the terminal?

![D1SK4-MCQ5](https://user-images.githubusercontent.com/80052961/110207999-94bfbb00-7eac-11eb-841f-14d60a70ad69.JPG)

**D1SK4 – MCQ6:**

Type below commands on terminal

cd vsdflow					                         

./vsdflow spi_slave_design_details.csv	

ls -ltr outdir_spi_slave/			                 

ls -ltr outdir_spi_slave | wc

 cd vsdflow command is usedchange the directory to vsdflow folder. ls -ltr shows list files/folders.

This will give you 3 numbers in one row, where 1st number represents number of files

What are the number of files you see?

![D1SK4-MCQ6](https://user-images.githubusercontent.com/80052961/110208038-d3557580-7eac-11eb-8349-8ddb453254bd.JPG)

**D1SK4 – MCQ7:**

cd outdir_spi_slave

qflow display spi_slave	

on tkcon window, type “box” 

What is the output area in microns ?

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

 After entering the commands shown above, it opens a qflow manager and we set technology = osu018, Verilog source = picorv32 and verilog module = picorv32. Click on start button opposite the preparation. If it is okay, then proceed to synthesis. Click on okay opposite to synthesis, it opens a synthesis log file. Synthesis file shows the number of cells, number of flops and etc.
 
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

git clone is a Git command line utility which is used to target an existing repository and create a clone, or copy of the target repository and ngspice is a tool which is used for circuit simulation.

![D3SK1-MCQ5](https://user-images.githubusercontent.com/80052961/110209735-0ea77280-7eb4-11eb-8147-aad0fa93b299.JPG)

**D3SK1 - MCQ8**

Type below commands

cd

cd ngspice_labs

ngspice inv.spice

There will be terminal like below

ngspice 1 ->

On the above ngspice terminal, type below commands

run

setplot dc1

plot out in

This will open a plot with CMOS VTC and Blue 45 degree line

Click on the intersection of Blue line and CMOS VTC.

Go to terminal

What does "x0" value lies between?

![D3SK1-MCQ8](https://user-images.githubusercontent.com/80052961/110209940-3fd47280-7eb5-11eb-995c-166a3a6eb778.JPG)

The below diagram shows the VTC characteristics of an inverter. The blueline(tan 45) intersecting the VTC curve that is called as switching threshold voltage(vm). swicthing threshold is the point where vin = vout and at which both p & n mos turned on and they are in saturation region.
![D3SK1-MCQ8_1](https://user-images.githubusercontent.com/80052961/110209947-44009000-7eb5-11eb-8062-d0de8b542873.JPG)

**D3SK1 - MCQ10**

Type below command

leafpad inv.spice

Edit the width of PMOS to 0.75u and save the file and exit the file

Repeat experiment given in D3SK1 - MCQ8

Where does the switching threshold lies between?

The below figure shows that cmos model description and the w/l ratios of both pmos and nmos
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

The below images shows the all the commands, which are used to open the simulation
![D3SK1-MCQ11_0](https://user-images.githubusercontent.com/80052961/110210758-3baa5400-7eb9-11eb-9add-06fdb1c135db.JPG)
The below figure shows the values of input fall time at 50% of power supply (1st x0) and output rise time at 50% of power supply(2nd x0)
![D3SK1-MCQ11](https://user-images.githubusercontent.com/80052961/110210768-4369f880-7eb9-11eb-9426-29ea95730bbb.JPG)
The below image shows the trainsient charecters of an inverter if input = 0v then output =2.5v(in this case) . it depends on the technolgy.
![D3SK1-MCQ11_1](https://user-images.githubusercontent.com/80052961/110210782-49f87000-7eb9-11eb-8596-eef1981181a3.JPG)


