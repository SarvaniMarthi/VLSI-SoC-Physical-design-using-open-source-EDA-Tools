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
- Timing analysis with ideal clocks
- Clock tree synthesis and signal integrity
- Timing analysis with real clocks

**Day-5**
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
### Day-1
**Initialising a sample design - raven spi using qflow**
![]
**Raven spi Layout**
![]
**Raven spi Layout Area**
![]
**Preparation of Picorv32**
![]
**Synthesis of Picorv32**
![]
**Picorv32 Statistics**
![]
### Day-2
**Placement of Picorv32**
![]
**Qflow Ungroup Pins**
![]
**Qflow after Auto Group**
![]
**Qflow Create Pin Group**
![]
**Qflow after Custom Group**
![]
**Placement In-Progress**
![]
**Placement Complete - Layout**
![]
**Layout Area**
![]
### Day-3
#### Inverter with PMOS Width 0.5μm
**Spice Deck**
![]
**Transfer Characteristics*
![]
#### Inverter with PMOS Width 0.5μm
**Spice Deck*
![]
**Transfer Characteristics**
![]
**Transient Analysis**
![]
#### Prelayout 
**Spice Deck**
![]
**Transient Analysis**
![]
#### Layout 
**Using Tcl Script
![]
**Drawing Inputs
![]
**Layout Area
![]
#### Postlayout 
**Spice Deck**
![]
**Transient Analysis**
![]
### Day-4
**OSU018 std library**
![]
**Synopsys Design Constraints File (.sdc)**
![]
**Configuration before running STA**
![]
**OpenSTA**
![]
**Slack Condition Met**
![]
### Day-5
**Routing In-Progress**
![]
**Routing Complete**
![]
**Prelayout STA Maximum Frequency of Operation**
![]
**Postlayout STA Maximum Frequency of Operation**
![]
### Acknowledgement
Kunal Ghosh, Co-founder (VSD Corp. Pvt. Ltd)
