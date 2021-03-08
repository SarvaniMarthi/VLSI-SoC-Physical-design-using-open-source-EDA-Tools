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
## Lab Excercises
### Software
List of tools used for RTL to GDS flow
- Yosys – for Synthesis
- Graywolf – for Placement
- Qrouter – for Routing
- Netgen – for LVS
- Magic – for Layout and Floorplanning
- Qflow – RTL2GDS integration
- OpenSTA & Opentimer – Pre-layout and Post-layout Static timing analysis
## Day-1
### Terminal

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Terminal.png)

### Raven spi using qflow

'''
cd vsdflow
./vsdflow spi_slave_design_details.csv
'''

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Raven_spi.png)

### Raven spi Layout

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Raven_spi_Layout.png)

### Raven spi Layout Area

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Raven_spi_Area.png)

### Preparation of Picorv32

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Preparation_Picorv32.png)

### Synthesis of Picorv32

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Synthesis_Picorv32.png)

### Picorv32 Statistics

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Synthesis_log_Picorv32.png)

## Day-2
### Placement of Picorv32

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

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Picorv32_Layout.png)

### Layout Area

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Picorv32_Area.png)

### Terminal

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Terminal.png)

## Day-3
### Inverter with PMOS Width 0.5μm
### Spice Deck

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Spicedeck_0.5%CE%BCm.png)

### Transfer Characteristics

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Transfer_Characteristics_0.5%CE%BCm.png)

### Inverter with PMOS Width 0.75μm
### Spice Deck

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Spicedeck_0.75%CE%BCm.png)

### Transfer Characteristics

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Transfer_Characteristics_0.75%CE%BCm.png)

### Transient Analysis

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Transient_Analysis_0.75%CE%BCm.png)

### Prelayout 
### Spice Deck

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Prelayout_Spicedeck.png)

### Transient Analysis

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Prelayout_Transient_Analysis.png)

### Layout 
### Using Tcl Script

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Layout_Tcl.png)

### Layout

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Layout.png)

### Layout Area

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Layout_Area.png)

### Postlayout 
### Spice Deck

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Postlayout_Spicedeck.png)

### Transient Analysis

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Postlayout_Transient_Analysis.png)

## Day-4
### OSU018 std library

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/OSU018_std.png)

### Synopsys Design Constraints File (.sdc)

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/SDC_File.png)

### Configuration before running STA

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/Configuration_STA.png)

### OpenSTA

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/STA-1.png)

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/STA-2.png)

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/STA-3.png)

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/STA-4.png)

### Slack Condition Met

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/Slack_Met.png)

## Day-5
### Routing In-Progress

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%205/Routing_In-Progress.png)

### Routing Complete

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%205/Routing_Complete.png)

### Prelayout STA Frequency

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%205/Prelayout_Frequency.png)

### Postlayout STA Frequency

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%205/Postlayout_Frequency.png)

### Acknowledgement
Kunal Ghosh, Co-founder (VSD Corp. Pvt. Ltd)
