# VLSI SoC/Physical design using open-source EDA Tools
## Topics Covered
**Day-1**
- IC Design Components Terminologies
- RISC-V based SOC Design
- Open-source EDA Tools

**Day-2**
- Floorplanning
- Placement
- Cell Design Flow
- Timing Characterization Parameters

**Day-3**
- CMOS Inverter Spice Simulation
- Euler's Path and Stick Diagram
- Post Layout Simulation
- CMOS Fabrication Process

**Day-4**
- Timing modelling using delay tables
- Timing Analysis with Ideal Clocks
- Clock Tree Synthesis and Signal Integrity
- Timing Analysis with Real Clocks

**Day-5**
- Routing
- DRC
- Parasitic Extraction

## RTL to GDSII Flow
- **Synthesis**
- **Floorplanning**
- **Powerplanning**
- **Placement**
- **Clock Tree Synthesis**
- **Static Timing Analysis**
- **Routing**
- **Layout**

## Software
List of tools used for RTL to GDS flow
- Yosys – for Synthesis
- Graywolf – for Placement
- Qrouter – for Routing
- Netgen – for LVS
- Magic – for Layout and Floorplanning
- Qflow – RTL2GDS integration
- OpenSTA & Opentimer – Pre-layout and Post-layout Static timing analysis

## Day-1
### Theory
### IC Design Components Terminologies
- Introduction to QFN-48 package, chip, pads, core, die and IP's

### RISC-V based SOC Design
- Introduction to RISC-V
- Introduction to picorv32 and picoSoC review
- Raven SoC and Raven full chip review

### Open-source EDA Tools
- Introduction to IC design components and open-source EDA tools
- Synthesizing picorv32, report ratio
- Test open-source EDA tools using sample design

### Lab
### Terminal

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Terminal.png)

### Raven spi using qflow
```
cd
git clone https://github.com/kunalg123/vsdflow.git
cd vsdflow
./vsdflow spi_slave_design_details.csv
```
Navigate to the root directory, clone an existing folder in repository 'vsdflow' and change the directory to 'vsdflow'.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Raven_spi.png)

### Raven spi Layout
```
cd outdir_spi_slave
qflow display spi_slave
```
Change directory to 'outdir_spi_slave' and display Qflow manager to open layout and tkcon window. Select the layout in layout window.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Raven_spi_Layout.png)

### Raven spi Layout Area

```
box
```
Type above command in the tkcon window to know the area of the selected layout.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Raven_spi_Area.png)

### Preparation of Picorv32
```
mkdir my_picorv32
cd my_picorv32
mkdir source synthesis layout
cp ~/vsdflow/verilog/picorv32.v source/.
qflow gui &
```
Create a new folder named 'my_picorv32', change the folder to 'my_picorv32', create new folders named source, synthesis and layout, copy the verilog file 'picorv32.v' from the source to 'vsdflow' folder, open the Qflow manager to perform the preparation and synthesis steps.

```
Technology = osu018
Verilog source file: picorv32.v
Verilog module: picorv32
```
Change the above parameters in the Qflow manager.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Preparation_Picorv32.png)

### Synthesis of Picorv32

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Synthesis_Picorv32.png)

### Picorv32 Statistics

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Synthesis_log_Picorv32.png)

## Day-2
### Theory
### Floorplanning
- Utilization factor and aspect ratio
- Concept of pre-placed cells and De-coupling capacitors
- Power planning
- Pin Placement and logical cell placement blockage
- Pin arrangement UI and automatic grouping of vectors

### Placement
- Netist binding and initial place design
- Optimize placement
- Final placement optimization
- Need for libraries and characterization

### Cell Design Flow
- Inputs for cell design flow
- Circuit design 
- Layout design
- Characterization flow

### Timing Characterization Parameters
- Timing threshold
- Propagation delay and transition time

### Lab
### Placement of Picorv32
```
mkdir my_picorv32
cd my_picorv32
mkdir source synthesis layout
cp ~/vsdflow/verilog/picorv32.v source/.
qflow gui &
```
Create a new folder named 'my_picorv32', change the folder to 'my_picorv32', create new folders named source, synthesis and layout, copy the verilog file 'picorv32.v' from the source to 'vsdflow' folder, open the Qflow manager to perform the placement step.

```
Technology = osu018
Verilog source file: picorv32.v
Verilog module: picorv32
```
Change the above parameters in the Qflow manager.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Placement_In-Progress-1.png)

### Ungroup Pins

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Ungrouped_Pins.png)

### Auto Group

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Auto_Grouped_Pins.png)

### Create Pin Group

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Create_Pin_Groups.png)

### Custom Group

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/After_Custom_Group.png)

### Placement In-Progress

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Placement_In-Progress-2.png)

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Placement%20In-Progress-3.png)

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Placement_In-Progress-4.png)

### Placement Complete 

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Placement_Complete-1.png)

### Layout
```

qflow display picorv32 &
```
Display Qflow manager to open layout and tkcon window. Select the layout in layout window.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Picorv32_Layout.png)

### Layout Area
```
box
```
Type above command in the tkcon window to know the area of the selected layout.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Picorv32_Area.png)

### Terminal

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Terminal.png)

## Day-3
### Theory
### CMOS Inverter Spice Simulation
- SPICE deck creation for CMOS inverter
- SPICE simulation for CMOS inverter
- Switching Threshold
- Static and dynamic simulation of CMOS inverter

###  Euler's Path and Stick Diagram
- Pre-layout simulation 
- Layout using stick diagram
- Euler's path
- Improved stick diagram
- Abstarct layout from stick diagram

###  Post Layout Simulation
- Script to create layout in Magic
- Final layout 
- Post-layout simulation

###  CMOS Fabrication Process
- Create active regions
- Formation of N-well and P-well
- Formation of gate terminal, lightly doped drain and source-drain
- Local interconnect and higher level metal formation

### Lab
### Inverter with PMOS Width 0.5μm
### Spice Deck
```
cd
git clone https://github.com/kunalg123/ngspice_labs.git
cd ngspice_labs
cat inv.spice
```
Navigate to the root directory, clone an existing folder in repository 'ngspice_labs', change the folder to 'ngspice_labs' and view the contents of the 'inv.spice' file.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Spicedeck_0.5%CE%BCm.png)

### Voltage Transfer Characteristics
```
ngspice inv.spice
ngspice 1 -> run
ngspice 1 -> setplot dc1
ngspice 1 -> plot out in
```
Open ngspice simulation tool for 'inv.spice', run the 'inv.spice', set the plot to dc mode and plot the output and input of 'inv.spice'.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Transfer_Characteristics_0.5%CE%BCm.png)

### Inverter with PMOS Width 0.75μm
### Spice Deck
```

leafpad inv.spice
cat inv.spice
```
Open leadpad to edit the 'inv.spice' file and change the width of the 'PMOS to 0.75μm' and view the contents of the updated 'inv.spice' file.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Spicedeck_0.75%CE%BCm.png)

### Voltage Transfer Characteristics
```
ngspice inv.spice
ngspice 1 -> run
ngspice 1 -> setplot dc1
ngspice 1 -> plot out in
```
Open ngspice simulation tool for 'inv.spice', run the 'inv.spice', set the plot to dc mode and plot the output and input of 'inv.spice'.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Transfer_Characteristics_0.75%CE%BCm.png)

### Transient Analysis
```
ngspice inv_tran.spice
ngspice 1 -> run
ngspice 1 -> setplot tran1
ngspice 1 -> plot out in
```
Open ngspice simulation tool for 'inv_tran.spice', run the 'inv_tran.spice', set the plot to transient mode and plot the output and input of 'inv_tran.spice'.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Transient_Analysis_0.75%CE%BCm.png)

### Prelayout 
### Spice Deck
```
cat fn_prelayout.spice
````
View the contents of the 'fn_prelayout.spice' file.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Prelayout_Spicedeck.png)

### Transient Analysis
```
ngspice fn_prelayout.spice
ngspice 1 -> run
ngspice 1 -> setplot tran1
ngspice 1 -> plot out 1.25
```
Open ngspice simulation tool for 'fn_prelayout.spice', run the 'fn_prelayout.spice', set the plot to transient mode and plot the output of 'fn_prelayout.spice' and 1.25V constant voltage.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Prelayout_Transient_Analysis.png)

### Layout 
### Using Tcl Script
```
magic -T min2.tech
```
Open the magic layout window and tkcon window. 

```
source draw_fn.tcl
```
Run the draw_fn.tcl file.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Layout_Tcl.png)

### Layout
```

magic -T min2.tech fn_postlayout.mag &
```
Open the magic layout for fn_postlayout and tkcon window. Select the layout.

```
% extract all
% ext2spice
```
Extract all the parasitics.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Layout.png)

### Layout Area
```
box
```
Type above command in the tkcon window to know the area of the selected layout.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Layout_Area.png)

### Postlayout 
### Spice Deck
```
leafpad fn_postlayout.spice
cat fn_postlayout.spice
````
Open leadpad to edit the 'fn_postlayout.spice' file and change the width of the 'PMOS to 0.75μm' View the contents of the 'fn_prelayout.spice' file.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Postlayout_Spicedeck.png)

### Transient Analysis
```
ngspice fn_postlayout.spice
ngspice 1 -> run
ngspice 1 -> setplot tran1
ngspice 1 -> plot out 1.25
```
Open ngspice simulation tool for 'fn_postlayout.spice', run the 'fn_postlayout.spice', set the plot to transient mode and plot the output of 'fn_postlayout.spice' and 1.25V constant voltage.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Postlayout_Transient_Analysis.png)

## Day-4
### Theory
### Timing modelling using delay tables
- Introducation to delay tables
- Delay table usage

###  Timing Analysis with Ideal Clocks
- Setup timing analysis
- Introduction to clock jitter and uncertainty

###  Clock Tree Synthesis and Signal Integrity
- Clock tree routing and buffering using H-Tree algorithm
- Crosstalk and clock net shielding

###  Timing Analysis with Real Clocks
- Setup timing analysis
- Hold timing analysis

### Lab
### OSU018 std library
```
leafpad /usr/local/share/qflow/tech/osu018/osu018_stdcells.lib
```
Open the 'OSU018 std library' file using leafpad.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/OSU018_std.png)

### Synopsys Design Constraints File (.sdc)
```
cd
cd vsdflow/my_picorv32
leafpad picorv32.sdc
```
Navigate to the root directory, change the folder to 'my_picorv32' and open 'picorv32.sdc' file in leafpad.

```
create_clock -name clk -period 2.5 -waveform {0 1.25} [get_ports clk]
```
Type the above line in the 'picorv32.sdc' opened in leafpad.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/SDC_File.png)

### Configuration before running STA
```
leafpad prelayout_sta.conf
```
Open 'prelayout_sta.conf' file in leafpad.

```
read_liberty /usr/local/share/qflow/tech/osu018/osu018_stdcells.lib
read_verilog synthesis/picorv32.rtlnopwr.v
link_design picorv32
read_sdc picorv32.sdc
report_checks
```
Type the above lines in the 'prelayout_sta.conf' opened in leafpad.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/Configuration_STA.png)

### OpenSTA
```
sta prelayout_sta.conf
```
Run STA of prelayout.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/STA-1.png)
```
% report_checks -digits 4
```
![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/STA-2.png)
```
% set_propagated_clock [all_clocks]
% report_checks
```
![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/STA-3.png)

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/STA-4.png)

### Slack Condition Met
```
report_checks -path_delay min -digits 4
```
![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/Slack_Met.png)

## Day-5
### Theory
### Routing
- Introduction to Maze routing
- Lee's algorithm

### DRC
- Design rule check
- Introduction to IEEE 1481- 1999 SPEF format
- SPEF representation of a NET
- SPEF header description

### Parasitic Extraction
- Placement and pre-layout STA
- Routing and post-layout STA

### Lab
### Routing In-Progress
```
cd
cd vsdflow/my_picorv32
qflow route picorv32
```
Navigate to the root directory, change the folder to 'my_picorv32' and initialize Qflow to route 'picorv32'.

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%205/Routing_In-Progress.png)

### Routing Complete

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%205/Routing_Complete.png)

### Prelayout STA Frequency
```
qflow sta picorv32
qflow backanno picorv32
leafpad log/sta.log
```
![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%205/Prelayout_Frequency.png)

### Postlayout STA Frequency
```
leafpad log/post_sta.log
```
![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%205/Postlayout_Frequency.png)

### Acknowledgement
Kunal Ghosh, Co-founder (VSD Corp. Pvt. Ltd)
