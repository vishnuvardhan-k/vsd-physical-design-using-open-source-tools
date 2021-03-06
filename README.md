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



