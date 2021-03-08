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

```
cd vsdflow
./vsdflow spi_slave_design_details.csv
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Raven_spi.png)

### Raven spi Layout
```
cd outdir_spi_slave
qflow display spi_slave
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Raven_spi_Layout.png)

### Raven spi Layout Area
```
box
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Raven_spi_Area.png)

### Preparation of Picorv32
```
cd
cd vsdflow
mkdir my_picorv32
cd my_picorv32
mkdir source synthesis layout
cp ~/vsdflow/verilog/picorv32.v source/.
qflow gui &
```
```
Technology = osu018
Verilog source file: picorv32.v
Verilog module: picorv32
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Preparation_Picorv32.png)

### Synthesis of Picorv32

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Synthesis_Picorv32.png)

### Picorv32 Statistics

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%201/Synthesis_log_Picorv32.png)

## Day-2
### Placement of Picorv32
```
cd
cd vsdflow
mkdir my_picorv32
cd my_picorv32
mkdir source synthesis layout
cp ~/vsdflow/verilog/picorv32.v source/.
qflow gui &
```
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
cd
cd vsdflow/my_picorv32
qflow display picorv32 &
```


![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Picorv32_Layout.png)

### Layout Area
```
box
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Picorv32_Area.png)

### Terminal

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%202/Terminal.png)

## Day-3
### Inverter with PMOS Width 0.5μm
### Spice Deck
```
cd
cd ngspice_labs
cat inv.spice
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Spicedeck_0.5%CE%BCm.png)

### Voltage Transfer Characteristics
```
ngspice inv.spice
ngspice 1 -> run
ngspice 1 -> setplot dc1
ngspice 1 -> plot out in
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Transfer_Characteristics_0.5%CE%BCm.png)

### Inverter with PMOS Width 0.75μm
### Spice Deck
```
cd
cd ngspice_labs
leafpad inv.spice
cat inv.spice
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Spicedeck_0.75%CE%BCm.png)

### Voltage Transfer Characteristics
```
ngspice inv.spice
ngspice 1 -> run
ngspice 1 -> setplot dc1
ngspice 1 -> plot out in
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Transfer_Characteristics_0.75%CE%BCm.png)

### Transient Analysis
```
ngspice inv_tran.spice
ngspice 1 -> run
ngspice 1 -> setplot tran1
ngspice 1 -> plot out in
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Transient_Analysis_0.75%CE%BCm.png)

### Prelayout 
### Spice Deck
```
cd
cd ngspice_labs
cat fn_prelayout.spice
````

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Prelayout_Spicedeck.png)

### Transient Analysis
```
ngspice fn_prelayout.spice
ngspice 1 -> run
ngspice 1 -> setplot tran1
ngspice 1 -> plot out 1.25
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Prelayout_Transient_Analysis.png)

### Layout 
### Using Tcl Script
```
cd
cd ngspice_labs
magic -T min2.tech
```
```
source draw_fn.tcl
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Layout_Tcl.png)

### Layout
```
cd
cd ngspice_labs
magic -T min2.tech fn_postlayout.mag &
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Layout.png)

### Layout Area
```
box
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Layout_Area.png)

### Postlayout 
### Spice Deck
```
cd
cd ngspice_labs
leafpad fn_postlayout.spice
cat fn_postlayout.spice
````

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Postlayout_Spicedeck.png)

### Transient Analysis
```
ngspice fn_postlayout.spice
ngspice 1 -> run
ngspice 1 -> setplot tran1
ngspice 1 -> plot out 1.25
```

![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%203/Postlayout_Transient_Analysis.png)

## Day-4
### OSU018 std library
```
leafpad /usr/local/share/qflow/tech/osu018/osu018_stdcells.lib
```
![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/OSU018_std.png)

### Synopsys Design Constraints File (.sdc)
```
cd
cd vsdflow/my_picorv32
leafpad picorv32.sdc
```
```
create_clock -name clk -period 2.5 -waveform {0 1.25} [get_ports clk]
```
![](https://github.com/SarvaniMarthi/VLSI-SoC-Physical-design-using-open-source-EDA-Tools/blob/main/Images/Day%204/SDC_File.png)

### Configuration before running STA
```
leafpad prelayout_sta.conf
```
```
read_liberty /usr/local/share/qflow/tech/osu018/osu018_stdcells.lib
read_verilog synthesis/picorv32.rtlnopwr.v
link_design picorv32
read_sdc picorv32.sdc
report_checks
```
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
