
# 🖥️ VSDBabySoC: RISC-V SoC Design & Tapeout Journey

**Author:** Paidipilli Purushotham

**Program:** VSD RISC-V SoC Tapeout Program

**Technology:** SkyWater 130nm (Sky130)

**Current Status:** ✅ **Complete** (RTL to GDSII Flow Executed & Verified)

---

## 📋 Table of Contents

**Executive Summary**

  * [The Vision: VSDBabySoC Architecture](https://www.google.com/search?q=%23-the-vision-vsdbabysoc-architecture)

**Part 1: The Foundation (Skill Building)**

  * [Day 1: Simulation Flow & Tool Setup](https://www.google.com/search?q=%23-day-1-simulation-flow--tool-setup)
  * [Day 2: Timing Libraries & Hierarchical Synthesis](https://www.google.com/search?q=%23-day-2-timing-libraries--hierarchical-synthesis)
  * [Day 3: Optimization Techniques](https://www.google.com/search?q=%23-day-3-optimization-techniques)
  * [Day 4: GLS & Synthesis Mismatches](https://www.google.com/search?q=%23-day-4-gls--synthesis-mismatches)
  * [Day 5: Advanced Verilog Strategies](https://www.google.com/search?q=%23-day-5-advanced-verilog-strategies)

**Part 2: VSDBabySoC Implementation (The Project)**

  * [Step 1: Architecture & Workspace Setup](https://www.google.com/search?q=%23-step-1-architecture--workspace-setup)
  * [Step 2: TL-Verilog to Verilog Conversion](https://www.google.com/search?q=%23-step-2-tl-verilog-to-verilog-conversion)
  * [Step 3: Pre-Synthesis Simulation](https://www.google.com/search?q=%23-step-3-pre-synthesis-simulation)
  * [Step 4: SoC Synthesis with Analog IP](https://www.google.com/search?q=%23-step-4-soc-synthesis-with-analog-ip)
  * [Step 5: Post-Synthesis Verification](https://www.google.com/search?q=%23-step-5-post-synthesis-verification)

**Part 3: Post-Synthesis Verification & Timing Analysis**

  * [Step 1: Synthesis (RTL to Netlist)](https://www.google.com/search?q=%23-phase-1-synthesis-rtl-to-netlist)
  * [Step 2: Post-Synthesis Simulation (GLS)](https://www.google.com/search?q=%23-phase-2-post-synthesis-simulation-gls)
  * [Step 3: Static Timing Analysis (STA) with OpenSTA](https://www.google.com/search?q=%23-performing-sta-on-vsdbabysoc)
  * [Step 4: Visualizing Timing Results](https://www.google.com/search?q=%23-visualizing-timing-graphs)

**Part 4: Circuit Characterization & SPICE Simulations**

  * [Day 1: nMOSFET I-V Characteristics](https://www.google.com/search?q=%23-day-1-nmosfet-i-v-characteristics)
  * [Day 2: Velocity Saturation & Short-Channel Effects](https://www.google.com/search?q=%23-day-2-velocity-saturation--short-channel-effects)
  * [Day 3: CMOS Switching Threshold](https://www.google.com/search?q=%23-day-3-cmos-switching-threshold-vm)
  * [Day 4: Noise Margins & Robustness](https://www.google.com/search?q=%23-day-4-noise-margins--robustness)
  * [Day 5: Power Supply & Process Variation](https://www.google.com/search?q=%23-day-5-power-supply--process-variation)

**Part 5: Physical Design - OpenROAD Flow**

  * [Step 1: Installation & Setup](https://www.google.com/search?q=%23-step-1-installation--setup)
  * [Step 2: Running the Flow (RTL to Placement)](https://www.google.com/search?q=%23-step-2-running-the-flow-rtl-to-placement)
  * [Step 3: Visualizing the Layout (GUI & KLayout)](https://www.google.com/search?q=%23-step-3-visualizing-the-layout)

**Part 6: Advanced Physical Design & Timing Closure**

  * [Step 1: Floorplanning & Power Planning](https://www.google.com/search?q=%23-step-1-floorplanning--power-planning)
  * [Step 2: Placement & Custom Cell Integration](https://www.google.com/search?q=%23-step-2-placement--custom-cell-integration)
  * [Step 3: Timing Analysis & ECO (Pre-CTS)](https://www.google.com/search?q=%23-step-3-timing-analysis--eco-pre-cts)
  * [Step 4: Clock Tree Synthesis (CTS)](https://www.google.com/search?q=%23-step-4-clock-tree-synthesis-cts)

**Part 7: Final Physical Design & Tapeout Sign-off**

  * [Step 1: Environment Setup & Design Config](https://www.google.com/search?q=%23-step-1-environment-setup--design-configuration)
  * [Step 2: Synthesis & Floorplanning](https://www.google.com/search?q=%23-step-2-synthesis--floorplanning)
  * [Step 3: Placement & Congestion Management](https://www.google.com/search?q=%23-step-3-placement--congestion-management)
  * [Step 4: Clock Tree Synthesis (CTS)](https://www.google.com/search?q=%23-step-4-clock-tree-synthesis-cts)
  * [Step 5: Pre-Route Checks](https://www.google.com/search?q=%23-step-5-pre-route-checks-critical)
  * [Step 6: Final Routing & Extraction](https://www.google.com/search?q=%23-step-6-final-routing--extraction)
## 1️⃣ 🎯 Executive Summary

This repository documents the comprehensive journey of designing **VSDBabySoC**, a mixed-signal RISC-V System-on-Chip. The project leverages the **Open-Source ASIC Flow**, taking the design from Register Transfer Level (RTL) logic all the way to a layout ready for fabrication.

### 🏆 VSDBabySoC Architecture 

The SoC integrates three core components:

1.  **`rvmyth` (Digital):** A RISC-V CPU Core that executes instructions and outputs 10-bit data.
2.  **`avsdpll` (Analog):** A Phase-Locked Loop that generates a stable clock for the core.
3.  **`avsddac` (Analog):** A Digital-to-Analog Converter that takes the CPU output and converts it to an analog voltage.

-----

## 🎬 Part 1: The Foundation (Skill Building)

**Focus:** Mastering the open-source toolchain (iVerilog, GTKWave, Yosys) and understanding digital design nuances before tackling the full SoC.

### 🛠️ Day 1: Simulation Flow & Tool Setup
**Goal:** Establish the simulation environment.
We verified the flow using a **2:1 Multiplexer**.

1.  **Design & Testbench:** Created Verilog source.
2.  **Simulation:** Used `iverilog` to generate VCD.
3.  **Visualization:** Used `GTKWave` to inspect signals.

**Simulator, Design & Testbench Basics:**
<img width="1108" height="442" alt="Image" src="https://github.com/user-attachments/assets/0a70940a-d265-424b-9b8b-97159efea7a8" />
**Icarus Verilog Flow:**
<img width="918" height="389" alt="Image" src="https://github.com/user-attachments/assets/ccea1f7c-0fa0-41ad-bcac-204c3f103026" />

**Lab Output: 2:1 Multiplexer Waveform**
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/ce7431c5-267b-400e-8160-1d90a343019d" />

**Synthesis Result:**
We converted the RTL to a gate-level netlist using Yosys.
<img width="1366" height="768" alt="Image" src="https://github.com/user-attachments/assets/c8ce0867-bb33-4888-bcdc-847133d4de0e" />

-----

### ⚙️ Day 2: Timing Libraries & Synthesis 

**Goal:** Mapping abstract HDL to physical Sky130 cells.
We analyzed `sky130_fd_sc_hd__tt_025C_1v80.lib` to understand PVT corners (Process, Voltage, Temperature) and compared **Hierarchical vs. Flattened** synthesis strategies.

-----

### ⚡ Day 3: Optimization Techniques {https://www.google.com/search?q=%23-day-3-optimization-techniques}

**Goal:** Reducing Area and Power.
We applied **Constant Propagation** (removing logic for constant inputs) and **State Optimization** to simplify logic gates.

**Lab: Optimization Check (Ternary Operator Mux)**

  * **RTL Code:**
    <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/0f1fe6b8-c360-4e53-bcbc-968cc126192e" />
  * **Synthesis Output:**
    <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/40491a7d-ce08-430f-8bd8-2a470cb7cb9b" />
  * **GLS Verification:**
    <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/9e3d1b85-5be1-43e9-84aa-4d0ec60c7e27" />

-----

### 🔬 Day 4: GLS & Synthesis Mismatches 
**Goal:** Detecting "Simulation-Synthesis Mismatches."
We demonstrated that bad coding (e.g., missing sensitivity lists or improper blocking assignments) leads to functional errors that only appear in **Gate-Level Simulation (GLS)**.

**1. The "Bad MUX" Experiment:**

  * **Code (Missing Sensitivity List):**
   <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/f58d41aa-1629-415a-97cf-452ccba798af" />
  * **Synthesis (Latch Inferred):**
   <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/7635ab61-af00-42fc-a0a8-6e50dddd48f0" />
  * **GLS Mismatch Result:**
    <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/fcea6575-16f6-4d1b-bfed-518f9ab792c6" />

**2. Blocking Assignment Caveat:**

  * **Synthesis:**
   <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/d0d86787-776e-415c-80d2-723fe670f25f" />
  * **GLS Result:**
    <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/57751582-7155-45b1-ba01-3aafaeccb13a" />

-----

### 🏗️ Day 5: Advanced Verilog Strategies {https://www.google.com/search?q=%23-day-5-advanced-verilog-strategies}

**Goal:** Scalable Design and Avoiding Latches.

**1. Latch Prevention (If/Else & Case):**

  * **Incomplete If (Latch Inferred):**
    <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/91d6cf74-ed4c-4029-b1b3-89da4ab6282c" />
  * **Synthesis Result:**
    <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/aee262c8-3769-4e0f-bd55-a9b198f69134" />
  * **Bad Case Statement (Wildcard issues):**
    <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/7c6de6eb-ff95-4b70-9c5b-856f3836b9bf" />

**2. Scalable Design (Generate Blocks):**
We utilized `generate` blocks and `for` loops to create an **8-bit Ripple Carry Adder (RCA)** efficiently.

  * **Demux using For Loop:**
   <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/feede22b-14d6-4968-9fb0-e90467c59099" />
  * **8-bit RCA Code:**
    <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/e6d52123-b337-4aef-8f69-20a7f8b2c06f" />
  * **RCA Schematic:**
    <img width="1280" height="800" alt="Image" src="https://github.com/user-attachments/assets/866c3dc3-c870-483c-a683-e74172cf1a84" />

-----

## 🚀 Part 2: VSDBabySoC Implementation (The Project)

**Focus:** Applying the skills from Part 1 to build, simulate, and synthesize the complete mixed-signal SoC.

### 🧱 Step 1: Architecture & Workspace Setup {https://www.google.com/search?q=%23-step-1-architecture--workspace-setup}

The VSDBabySoC connects the digital world (RISC-V) with the analog world (DAC/PLL).

**Connections:**

  * `PLL` → provides `CLK` → `rvmyth` (CPU)
  * `rvmyth` → outputs `DATA` → `DAC`
  * `DAC` → outputs `Analog Voltage`

**File Structure:**

```bash
VSDBabySoC/
├── src/module/
│   ├── rvmyth.tlv       # RISC-V Core (TL-Verilog)
│   ├── avsdpll.v        # Analog PLL Model
│   ├── avsddac.v        # Analog DAC Model
│   └── vsdbabysoc.v     # Top-level integration
```

### ⚙️ Step 2: TL-Verilog to Verilog Conversion {https://www.google.com/search?q=%23-step-2-tl-verilog-to-verilog-conversion}

The CPU core (`rvmyth`) is designed in **TL-Verilog** for efficiency. We use **SandPiper-SaaS** to convert it to standard Verilog for synthesis.

```bash
# Activate SandPiper Environment
source sp_env/bin/activate

# Convert TLV to Verilog
sandpiper-saas -i ./src/module/*.tlv -o rvmyth.v --bestsv --noline -p verilog --outdir ./src/module/
```

✅ **Outcome:** `rvmyth.v` is generated and ready for synthesis.

### 🧪 Step 3: Pre-Synthesis Simulation {https://www.google.com/search?q=%23-step-3-pre-synthesis-simulation}

We verify the RTL functionality using `iverilog`. This simulation checks if the CPU is correctly driving the DAC inputs.

**Waveform Analysis:**
To see the DAC output correctly in GTKWave, we formatted the `OUT` signal as **Analog (Step)**.

<img width="1920" height="1080" alt="GTKwave presynthesis" src="https://github.com/user-attachments/assets/7258f4ae-5249-4995-9e6d-a20dc37d091c" />
**GTKWave Configuration:**
Changing the data format to view analog steps.
<img width="1920" height="1080" alt="GTk Wave Setting" src="https://github.com/user-attachments/assets/30100c1b-cf2a-45fe-839e-ca8e8b615f0b" />

**Key Signals:**

  * `CLK`/`Reset`: Inputs from PLL/External.
  * `D[9:0]`: Digital output from the RISC-V core.
  * `OUT`: The simulated analog voltage stepping up/down based on CPU data.

### 🧰 Step 4: SoC Synthesis with Analog IP {https://www.google.com/search?q=%23-step-4-soc-synthesis-with-analog-ip}

We synthesized the design using **Yosys**.

  * **Challenge:** The PLL and DAC are *analog* blocks, so they don't have standard logic gates.
  * **Solution:** We mapped them as "Black Boxes" using their Liberty (`.lib`) files (`avsddac.lib`, `avsdpll.lib`), while the digital core was mapped to `sky130_fd_sc_hd`.

**Synthesized Schematic:**
<img width="1920" height="1080" alt="VSDBabySoc Schematic" src="https://github.com/user-attachments/assets/cda5a231-a25b-4101-a126-18020078db86" />

**Yosys Output Log:**
<img width="1920" height="1080" alt="Yosys Output" src="https://github.com/user-attachments/assets/47305e0a-ba6a-4f9d-b1e0-80625006913c" />

### 🧪 Step 5: Post-Synthesis Verification {https://www.google.com/search?q=%23-step-5-post-synthesis-verification}

We ran a Gate-Level Simulation (GLS) on the synthesized netlist `vsdbabysoc.synth.v`.

**Why this matters:**
This simulation includes the actual standard cells (AND, OR, DFF) instead of behavioral logic. It validates that the synthesis tool correctly translated the logic and that the design functions with gate delays.

<img width="1920" height="1080" alt="Post Synth GTKWave" src="https://github.com/user-attachments/assets/42539cef-8042-425f-babd-99015880a564" />
**Observation:**
The waveform shows numerous internal `wire` signals (e.g., `wire 3674`), confirming we are simulating the physical gate structure. The logic matches the pre-synthesis run, confirming a successful synthesis.

-----

### 🏁 Phase 2 Summary

✅ **Integrated:** Digital RISC-V Core with Analog PLL & DAC.
✅ **Converted:** TL-Verilog to Standard Verilog using SandPiper.
✅ **Synthesized:** Full SoC using Analog Black-Box Libraries.
✅ **Verified:** Validated functionality via Pre-Synth and Post-Synth simulations.

**🚀 Next Up:** Phase 3 - Physical Design (Floorplanning & Placement)

## 🔎 Part 3: Post-Synthesis Verification & Timing Analysis

**Focus:** Transforming the RTL into a Gate-Level Netlist, verifying it via Gate-Level Simulation (GLS), and performing Static Timing Analysis (STA) to ensure the design meets timing constraints across all Process-Voltage-Temperature (PVT) corners.

### 🌊 Workflow Overview

The flow moves from abstract behavior to concrete silicon logic:

1.  **Synthesis (Yosys):** RTL $\rightarrow$ Logic Gates (Netlist).
2.  **GLS (Icarus):** Netlist Verification.
3.  **STA (OpenSTA):** Timing Verification.

<!-- end list -->

```mermaid
graph TD
    A[RTL Verilog] -->|Yosys| B(Gate-Level Netlist)
    B -->|Icarus Verilog| C[Gate-Level Simulation]
    B -->|OpenSTA| D[Static Timing Analysis]
    C --> E{Functional Correct?}
    D --> F{Timing Met?}
```

### 🔬 Step 1: Synthesis (RTL to Netlist) {\#-phase-1-synthesis-rtl-to-netlist}

We used **Yosys** to translate the VSDBabySoC RTL into a netlist using the Sky130 PDK.

**1. Loading Design & Libraries:**
We read the Verilog modules (`vsdbabysoc.v`, `rvmyth.v`, `clk_gate.v`) and the Liberty files. Note that we used separate `.lib` files for the Analog IPs (`avsddac`, `avsdpll`) to treat them as black boxes.

*Loading Design Files:*
<img width="1907" height="183" alt="1st command_yosys" src="https://github.com/user-attachments/assets/5e49a6ff-2adf-42ee-9319-ae0cc9ea08d9" />
<img width="1907" height="651" alt="2_3_commands_yosys" src="https://github.com/user-attachments/assets/bb775499-ea6d-48d1-aabd-6df970e83885" />
*Loading Liberty Files:*
<img width="1907" height="376" alt="Liberty_files_read" src="https://github.com/user-attachments/assets/053b496a-04d4-4df9-8fca-1c15d2f77b40" />
**2. Synthesis & Mapping:**
We ran `synth -top vsdbabysoc` to generate generic logic, followed by `dfflibmap` to map Flip-Flops to Sky130 cells.
<img width="1920" height="1080" alt="synth-top_1" src="https://github.com/user-attachments/assets/cf9f673a-29bb-4048-92f6-6544578966fa" />

*Mapping D-Flip-Flops:*
<img width="1920" height="1080" alt="Map-D-ff" src="https://github.com/user-attachments/assets/65da6fc7-190b-45e8-b6d1-1a6a64ccb2fa" />

**3. Optimization & Output:**
Using `opt` and `abc`, we optimized the design for the target library. Finally, we wrote the netlist `vsdbabysoc.synth.v`.

*Optimization & Tech Mapping:*
<img width="1920" height="1080" alt="Opt_tech_mapping" src="https://github.com/user-attachments/assets/3b5fa67c-758e-49fc-a36c-77b4a02992c0" />
*Cleaning & Renaming:*
<img width="1920" height="1080" alt="cleanup_rename" src="https://github.com/user-attachments/assets/e0a0d10f-1165-4470-8beb-58a0d84b8d1a" />

*Final Statistics & Write:*
<img width="1920" height="1080" alt="Check-stats1" src="https://github.com/user-attachments/assets/a42cf15d-5296-4579-9e3d-29df8c095707" />
<img width="1907" height="236" alt="Write-netlist" src="https://github.com/user-attachments/assets/738c715c-a8e3-4aa3-b15f-d8434b2021d4" />
-----

### ⚡ Step 2: Post-Synthesis Simulation (GLS) {\#-phase-2-post-synthesis-simulation-gls}

We compiled the **Synthesized Netlist** along with the **Sky130 Primitives** (`primitives.v`, `sky130_fd_sc_hd.v`) to verify that the gate-level translation functions correctly.

**Compilation Command:**
We used the `-DPOST_SYNTH_SIM` flag to switch the testbench to the netlist.
<img width="1907" height="301" alt="Iverilog-output" src="https://github.com/user-attachments/assets/479760fe-546f-4996-acb5-9f9d442b681d" />
**Verification Result:**
The GLS waveforms matched the Pre-Synthesis RTL simulation, confirming the synthesis was successful.
<img width="1920" height="1080" alt="gtkwave_1stout" src="https://github.com/user-attachments/assets/e69d3446-3d60-45fb-9de7-661eb5814eaa" />

-----

### 🛰️ Step 3: Static Timing Analysis (STA) with OpenSTA {\#-performing-sta-on-vsdbabysoc}

GLS verifies function, but STA verifies **Speed**. We used **OpenSTA** to analyze timing paths across multiple PVT corners.

**1. Setup & Installation:**
We built OpenSTA from source and set up the Sky130 Timing libraries.
<img width="1918" height="1045" alt="Screenshot from 2025-10-12 14-30-51" src="https://github.com/user-attachments/assets/b408d143-fd92-4dce-bbcf-a61708d588d5" />

**2. Multi-Corner Analysis Script:**
We wrote a TCL script (`run_sta.tcl`) to iterate through **13 different PVT libraries** (Typical, Fast, Slow corners at various temperatures).

**3. Execution:**
The STA run generated detailed reports for WNS (Worst Negative Slack) and TNS (Total Negative Slack).
<img width="1918" height="1045" alt="Screenshot from 2025-10-12 15-04-18" src="https://github.com/user-attachments/assets/27709f40-20c3-4a43-bad0-de01fd802cbd" />
<img width="1918" height="1050" alt="Screenshot from 2025-10-12 15-30-41" src="https://github.com/user-attachments/assets/4df2e70e-8a25-4b3f-b022-808a99cc9069" />

**4. Data Parsing:**
We used a shell script to consolidate the logs into a summary table.
<img width="1918" height="830" alt="Screenshot from 2025-10-12 15-25-17" src="https://github.com/user-attachments/assets/a9d9791c-59dc-4fc7-95b0-65b72322c844" />

-----

### 📊 Step 4: Visualizing Timing Results {\#-visualizing-timing-graphs}

Using Python (`matplotlib`), we plotted the timing metrics across all corners to visualize margins.

**Composite Timing Graph:**
This plot summarizes Setup, Hold, WNS, and TNS across all analyzed corners.
<img width="1918" height="1051" alt="All Graphs" src="https://github.com/user-attachments/assets/d097f299-5716-4e0b-a0ab-8ca940399953" />

**Detailed Metrics:**

  * **Worst Setup Slack:** (Positive slack = Timing Met)
    <img width="1918" height="1051" alt="Worst Setup Slack" src="https://github.com/user-attachments/assets/6a8155ce-6841-4cc8-8f23-41906a319817" />
  * **Worst Hold Slack:**
    <img width="1918" height="1051" alt="Worst Hold Slack" src="https://github.com/user-attachments/assets/44d74903-ab24-4b46-bd72-4f5bf86dfd66" />
  * **Worst Negative Slack (WNS):**
   <img width="1918" height="1051" alt="Wns Across PVT" src="https://github.com/user-attachments/assets/00558139-156a-4fd9-91ba-315631a2c21c" />

-----

### 🏁 Part 3 Summary

✅ **Synthesized:** RTL converted to Sky130 Netlist.
✅ **Verified:** GLS matches Functional Simulation.
✅ **Analyzed:** Timing checked across 13 PVT corners.
✅ **Visualized:** Timing margins plotted successfully.

**🚀 Next Up:** Phase 3 - Physical Design (Floorplanning & Placement)

## 🔬 Part 4: Circuit Characterization & SPICE Simulations (Week 4)

**Focus:** Moving from digital abstraction to analog reality. We characterized the Sky130 MOSFETs using SPICE simulations to understand the physics governing timing, power, and robustness.

### 📜 Day 1: nMOSFET I-V Characteristics

**Goal:** Characterize the fundamental Current-Voltage behavior of the Sky130 nMOS device.

We simulated the device to observe the **Linear** (Resistive) and **Saturation** regions. Understanding these regions is critical because the saturation current ($I_{dsat}$) determines the "Drive Strength" of the cell—directly impacting circuit speed.

**Simulation Setup:**
We swept the Drain Voltage ($V_{ds}$) while stepping the Gate Voltage ($V_{gs}$).
<img width="1920" height="1080" alt="Spice Setup" src="https://github.com/user-attachments/assets/697e343f-3497-453a-95ce-bad2939866b4" />
**Result: Family of Curves**
The plot clearly shows the transition from the linear region to saturation (flattening of the curve).
<img width="1920" height="1080" alt="Graph" src="https://github.com/user-attachments/assets/6439e173-0258-43f5-a8c4-e6b5cbabb2bb" />

**Derivation of Current Equation:**
We validated the square-law equations against the simulation.
<img width="1920" height="1080" alt="Id derivation" src="https://github.com/user-attachments/assets/fd3ad54c-7b60-4489-a44b-9c4a3755af8d" />

-----

### ⚡ Day 2: Velocity Saturation & Short-Channel Effects

**Goal:** Compare "Long Channel" vs. "Short Channel" behavior.

In modern nodes like 130nm, the classic square-law ($I_d \propto V_{gs}^2$) breaks down due to **Velocity Saturation**. High electric fields cause carrier velocity to cap out, making the current linear with respect to $V_{gs}$.

**Simulation Results:**
We observed that for short-channel devices, the current increases linearly rather than quadratically at high $V_{gs}$.
<img width="1920" height="1080" alt="Graph id vs vgs" src="https://github.com/user-attachments/assets/1b64c8e0-327d-499a-ad8b-5495e742fd88" />
**CMOS Inverter Theory:**
We began analyzing the Voltage Transfer Characteristic (VTC) by overlaying the NMOS and PMOS load curves.

<img width="1920" height="1080" alt="Screenshot 2025-10-18 123820" src="https://github.com/user-attachments/assets/fc6a1d0a-4131-4fc1-825a-79c08073f9c7" />

-----

### ⚙️ Day 3: CMOS Switching Threshold ($V_m$)

**Goal:** Analyze the Switching Threshold—the point where $V_{in} = V_{out}$.

The switching threshold $V_m$ is determined by the ratio of the PMOS to NMOS drive strengths. An ideal inverter has $V_m = V_{dd}/2$.

**Sizing Impact:**
We found that a $W_p / W_n$ ratio of roughly **2:1 to 2.5:1** is required to center the VTC, as the PMOS hole mobility is lower than NMOS electron mobility.

**Static Analysis (VTC):**
<img width="1920" height="1080" alt="cmos vt curve" src="https://github.com/user-attachments/assets/a8965c13-dc14-4830-b26d-235a46c76dde" />

**Dynamic Analysis (Transient Response):**
We simulated a pulse input to measure Rise and Fall delays.
<img width="1920" height="1080" alt="cmos tran" src="https://github.com/user-attachments/assets/b5bc4a50-577a-424e-b64e-a51d8bb091b2" />

-----

### 🔊 Day 4: Noise Margins & Robustness

**Goal:** Quantify the inverter's tolerance to noise.

We extracted the critical voltage points ($V_{IL}, V_{IH}, V_{OL}, V_{OH}$) from the VTC to calculate:

  * **$NM_L$ (Low Noise Margin):** $V_{IL} - V_{OL}$
  * **$NM_H$ (High Noise Margin):** $V_{OH} - V_{IH}$

**VTC for Extraction:**
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6eeeb5a5-276d-4c77-b420-2cc24e5a4d2e" />

-----

### 🔋 Day 5: Power Supply & Process Variation

**Goal:** Ensure the circuit works under non-ideal conditions.

**1. Power Supply Variation:**
We swept $V_{dd}$ from 1.8V down to lower voltages.

  * **Observation:** Lower Vdd saves energy but degrades noise margins and increases delay.

<img width="1920" height="1080" alt="Screenshot from 2025-10-19 15-48-56" src="https://github.com/user-attachments/assets/e263adda-343c-4858-ad76-1f3bac70576e" />

**2. Device Variation:**
We simulated "Strong PMOS / Weak NMOS" corners. The CMOS inverter proved remarkably robust—the switching threshold shifted, but the logic gate did not fail.

-----

### 🏁 Part 4 Summary

✅ **Characterized:** Sky130 NMOS I-V curves.
✅ **Analyzed:** Velocity Saturation effects in short-channel devices.
✅ **Optimized:** CMOS Inverter sizing for symmetric Switching Threshold ($V_m$).
✅ **Calculated:** Noise Margins ($NM_H, NM_L$).
✅ **Verified:** Robustness against Supply and Process variations.

## 🚀 Part 5: Physical Design - OpenROAD Flow (Week 5)

**Focus:** Setting up the complete **RTL-to-GDSII flow** using OpenROAD. We moved from specific circuit characterization to the macroscopic physical design process, taking a design from Verilog RTL to the Placement stage.

### 🌊 The Physical Design Journey

We utilized the **OpenROAD Flow Scripts** to automate the backend flow. This transforms the abstract RTL into physical geometry.

```mermaid
graph TD
    A[RTL Verilog] -->|Synthesis| B(Gate-Level Netlist)
    B -->|OpenROAD| C(Floorplanning)
    C -->|OpenROAD| D(Placement)
    D -->|OpenROAD| E(CTS & Routing)
```

### ⚙️ Step 1: Installation & Setup

Setting up the environment involves compiling OpenROAD and its dependencies.

**1. Clone & Install:**
We cloned `OpenROAD-flow-scripts` and utilized the robust dependency installer to handle system-level packages.

```bash
sudo ./etc/DependencyInstaller.sh -all
./build_openroad.sh --local
```

**2. Troubleshooting:**
We encountered issues with missing libraries (`GTest`, `spdlog`).

  * **Solution:** The `-all` flag in the dependency installer was critical to ensure all local libraries (Eigen, Boost, etc.) were built correctly in the local environment.

**Successful Build:**
<img width="1920" height="1080" alt="OpenRoad - help" src="https://github.com/user-attachments/assets/5989ff38-1b47-43cb-bed0-4a358fc746b2" />

-----

### 🏃‍♂️ Step 2: Running the Flow (RTL to Placement)

We verified the toolchain using the `gcd` (Greatest Common Divisor) test design. We executed the flow up to the **Placement** stage.

**Command:**

```bash
make DESIGN_CONFIG=./designs/sky130hd/gcd/config.mk place
```

**Execution Logs:**
The flow automatically performed Synthesis (Yosys), Floorplanning (ioPlacer/pdngen), and Global/Detailed Placement.
<img width="1920" height="1080" alt="Screenshot from 2025-10-23 12-23-25" src="https://github.com/user-attachments/assets/d3c6e1b4-20ed-40e5-824c-07cfd26f91b2" />
<img width="1920" height="1080" alt="Screenshot from 2025-10-23 11-14-04" src="https://github.com/user-attachments/assets/d396602f-d212-46ac-b541-133d16838bb6" />

-----

### 🖼️ Step 3: Visualizing the Layout

We used two methods to inspect the generated layouts: the native **OpenROAD GUI** and **KLayout**.

#### Method 1: OpenROAD GUI (Native)

We loaded the `.odb` (Open Database) files directly into the GUI.

**1. Floorplan View:**
This stage defines the Die Area, I/O Pin placement, and the Power Distribution Network (PDN).
*Loading the database:*
<img width="651" height="467" alt="Screenshot from 2025-10-23 11-28-40" src="https://github.com/user-attachments/assets/6f88ce86-98ac-4ebc-9235-099a1592f889" />

*Visualizing Die & Power Grid:*
<img width="1920" height="1080" alt="floor_plan" src="https://github.com/user-attachments/assets/f5259366-31fe-45ba-8ea3-2db8c59a2f0c" />
**2. Placement View:**
This stage places the standard cells (logic gates) into the rows defined by the floorplan.
<img width="1920" height="1080" alt="Placement" src="https://github.com/user-attachments/assets/7f1ccb52-558c-4f81-b68b-9ffbf056b230" />

-----

#### Method 2: KLayout (Def Viewer)

To use KLayout, we converted the OpenROAD database (`.odb`) into Data Exchange Format (`.def`) using Tcl commands.

**Conversion Process:**

```tcl
read_db results/sky130hd/gcd/base/3_place.odb
write_def results/sky130hd/gcd/base/3_place.def
```

<img width="1920" height="306" alt="Convert for klayout" src="https://github.com/user-attachments/assets/a7e911b6-d168-458d-a1b9-44afad628c32" />

**KLayout Visualization:**
We loaded the generated `.def` along with the Sky130 LEF files to view the physical geometry.
<img width="1920" height="1080" alt="Screenshot from 2025-10-23 12-01-53" src="https://github.com/user-attachments/assets/b2de2408-54e3-463b-8794-2f89b578f917" />

---

### 🏁 Part 5 Summary

✅ **Environment:** Successfully built OpenROAD Flow Scripts.
✅ **Flow Execution:** Ran `gcd` design from RTL through Synthesis to Placement.
✅ **Floorplanning:** Verified die area and power grid creation.
✅ **Placement:** Verified standard cell placement.
✅ **Visualization:** Mastered both OpenROAD GUI and KLayout for inspection.


## 🏗️ Part 6: Advanced Physical Design & Timing Closure (Week 6)

**Focus:** Moving from a "soft" synthesized design to a "hard" manufacturable layout. This week involved creating a robust Floorplan, designing a custom Standard Cell (Inverter) from scratch, fixing timing violations via ECOs, and building the Clock Tree.

### 📍 Step 1: Floorplanning & Power Planning

**Goal:** Define the chip's dimensions and build the Power Distribution Network (PDN).

  * **Core definition:** Set **Utilization Factor** (ratio of logic to total area) and **Aspect Ratio** (height/width).
  * **Power Planning:** Created the power mesh (VDD/VSS) using upper metal layers to minimize IR drop.
  * **Decoupling Capacitors:** Inserted "Decaps" to stabilize power during switching.

**Magic Visualization (Floorplan):**
The layout shows the core area (inner box) and I/O pin placement.
<img width="1920" height="1080" alt="magic layout" src="https://github.com/user-attachments/assets/dd482b0e-74f7-4359-bf89-4c23bcb1a291" />

----

### 📦 Step 2: Placement & Custom Cell Integration

**Goal:** Place standard cells onto the floorplan rows and integrate a custom-designed cell.

#### A. Custom Inverter Design

We didn't just use the library; we built a custom CMOS Inverter from scratch to understand the cell design flow.

1.  **Layout:** Drew the PMOS/NMOS layers (Poly, Diffusion, Metal1) in Magic.
2.  **Extraction:** Extracted parasitics to SPICE.
3.  **Characterization:** Simulated in `ngspice` to find Rise/Fall delays.
4.  **LEF Generation:** Exported the "Abstract View" (LEF) for the Place & Route tool.

**Custom Inverter Layout:**

<img width="1920" height="1080" alt="Layout" src="https://github.com/user-attachments/assets/d380e3dd-7905-4cd5-93d1-730c5bd80cd4" />
**SPICE Characterization:**

<img width="1920" height="1080" alt="spice Output" src="https://github.com/user-attachments/assets/9cf60f46-399f-45e0-90d6-ea6c377ea04b" />

#### B. Full Design Placement

We integrated this custom LEF into the OpenLANE flow and ran global placement.
<img width="1920" height="1080" alt="Placement" src="https://github.com/user-attachments/assets/01a57243-18e7-420d-92ee-b385d71568af" />

-----

### ⏱️ Step 3: Timing Analysis & ECO (Pre-CTS)

**Goal:** Fix Setup Time violations before inserting the clock tree.

**Analysis Strategy:**
We used **OpenSTA** with ideal clocks.

  * **Initial Result:** WNS (Worst Negative Slack) was **-23.89 ns**. The design was failing timing significantly.

<img width="1920" height="1080" alt="27 Slack Violated" src="https://github.com/user-attachments/assets/b42fbd51-914e-42bd-8076-a893d127a6b2" />

**The Fix (ECO - Engineering Change Order):**
We identified high-fanout nets driving weak cells (e.g., `OR2_2`). We performed **Cell Sizing** (upsizing to `OR2_4`) to increase drive strength and reduce delay.

**Final Result:**
After multiple ECO iterations, we successfully reduced the negative slack.

<img width="1920" height="1080" alt="32 slack met at last" src="https://github.com/user-attachments/assets/f4f69cf8-f59f-41dc-a054-9e51c95402d4" />

-----

### 🕒 Step 4: Clock Tree Synthesis (CTS)

**Goal:** Distribute the clock to all sequential elements with minimum **Skew** and **Latency**.

We used **TritonCTS** to build the H-Tree structure.

  * **Buffers:** Inserted clock buffers (`clkbuf`) to manage signal integrity.
  * **Post-CTS Analysis:** We switched from "Ideal Clocks" to "Propagated Clocks" in OpenSTA to analyze real Setup/Hold timing including Clock Skew (`Delta1 - Delta2`) and Jitter.

**CTS Success:**

<img width="1920" height="1080" alt="38 cts success" src="https://github.com/user-attachments/assets/7df7f57a-73af-4969-940e-3db121e180ed" />

-----

### 🏁 Part 6 Summary

✅ **Floorplan:** Created core area and robust Power Distribution Network.
✅ **Custom Cell:** Designed, characterized, and integrated a custom Inverter.
✅ **Placement:** Legalized standard cell placement with no overlaps.
✅ **Timing ECO:** Fixed critical setup violations by upsizing drive cells.
✅ **CTS:** Built a balanced clock tree to minimize skew.

## 🚀 Part 7: Final Physical Design & Tapeout Sign-off (Week 7)

**Focus:** Executing the complete **RTL-to-GDSII flow** using the OpenROAD Flow Scripts (ORFS) for the final VSDBabySoC. This week focused on integrating the analog macros (`avsddac`, `avsdpll`), solving congestion/PDN issues, and generating the final Layout (GDS) and Parasitics (SPEF) for sign-off.

### 📘 Overview: The Real ASIC Flow

We transitioned from unit-level experiments to a full-chip physical implementation.

  * **Input:** RTL (`vsdbabysoc.v`), Analog GDS/LEF/LIB (`avsddac`, `avsdpll`), Constraints (`.sdc`).
  * **Output:** DRC-clean GDSII layout and SPEF parasitics for final timing analysis.

-----

### 🛠️ Step 1: Environment Setup & Design Configuration

We utilized **OpenROAD-flow-scripts** (ORFS) to automate the flow.

**1. Directory Structure:**
We organized the design files to align with the ORFS standard structure:

```text
designs/sky130hd/vsdbabysoc/
├── gds/ (Analog Macros)
├── lef/ (Physical Abstracts)
├── lib/ (Timing Models)
├── config.mk (Flow Configuration)
└── constraint.sdc
```

**2. Configuration (`config.mk`):**
We defined critical flow parameters, including:

  * **Die/Core Area:** `3000 x 3000` units.
  * **Macro Placement:** Defined in `macro.cfg` to place PLL and DAC.
  * **PDN & Tapcells:** Configured specifically for Sky130 requirements.

> <img width="1920" height="1080" alt="1 config mk" src="https://github.com/user-attachments/assets/0bee8ae9-afd0-49f4-96fa-c763fe174435" />
-----

### 📉 Step 2: Synthesis & Floorplanning

**Synthesis:**
Mapped the digital logic to Sky130 cells while preserving the analog black boxes.

  * *Output:* Netlist with \~3000 standard cells.

> <img width="1920" height="1080" alt="4 netlist file" src="https://github.com/user-attachments/assets/3757fe8c-72a4-4c15-bc56-8c710876a2f8" />

**Floorplanning:**

  * Placed the Macros (DAC & PLL) according to `macro.cfg`.
  * Generated the Power Distribution Network (PDN).
  * **Crucial Fix:** We had to adjust **Tapcell spacing** in `tapcell.tcl` to avoid congestion and reduce blockages.

> <img width="1920" height="1080" alt="6 flooorplan output" src="https://github.com/user-attachments/assets/121368ab-1922-44cf-956a-9a430b334bd4" />
-----

### 🧩 Step 3: Placement & Congestion Management

**Global & Detailed Placement:**
The tool placed standard cells in the core area. We used **Heatmaps** to verify that cell density did not exceed limits (target density 0.10).

> <img width="1920" height="1080" alt="7 placement heatmaps" src="https://github.com/user-attachments/assets/cdc4ded6-68dd-43a1-973c-098b372be0d3" />

-----

### 🕒 Step 4: Clock Tree Synthesis (CTS)

We built the clock tree to distribute the `CLK` signal from the PLL to the rest of the chip.

  * **Verification:** Checked that buffers were inserted correctly and that the tree was balanced.

> <img width="1920" height="1080" alt="8 cts output" src="https://github.com/user-attachments/assets/d0ddf270-a0a3-42eb-a6c2-d1e9ed53806d" />

-----

### ⚠️ Step 5: Pre-Route Checks (Critical)

Before routing, we performed rigorous checks to ensure the router wouldn't fail:

1.  **Blockages:** Removed old placement/CTS data to prevent ghost blockages (`clean_place`, `clean_cts`).
2.  **Congestion Report:** Verified congestion was \< 5% using `congestion.rpt`.
3.  **Tapcells:** Verified correct insertion density using `grep` on logs.

> <img width="1920" height="1080" alt="9 pdn tcl comment out" src="https://github.com/user-attachments/assets/e81c8c01-69e0-42e3-bf60-220de783425f" />

-----

### 🛣️ Step 6: Final Routing & Extraction

**Routing:**
Executed Global and Detailed routing. The router successfully connected all nets without DRC violations.

> <img width="1920" height="1080" alt="Screenshot from 2025-11-16 19-56-45" src="https://github.com/user-attachments/assets/2e554178-d2c8-4edd-ac06-cc8837ad553d" />
**SPEF Extraction:**
Extracted the **Standard Parasitic Exchange Format (SPEF)** file. This file contains the exact Resistance and Capacitance of the routed wires, which is used for the final, most accurate Static Timing Analysis.

-----

### 📚 Theory: The Future of VLSI

We also explored the roadmap of semiconductor scaling:

  * **Scaling:** From Planar FETs → FinFETs → Gate-All-Around (GAA).
  * **Interconnects:** Evolution from Copper to Ruthenium (Ru) and Air-gaps to reduce resistance/capacitance.
  * **Power Delivery:** Moving to **Backside Power Delivery Networks (BS-PDN)** to reduce IR drop and save area.

> <img width="1126" height="654" alt="image" src="https://github.com/user-attachments/assets/5ff79748-af0a-4ad8-ab94-a3197dfdb409" />

-----

### 🏁 Part 7 Summary

✅ **Flow Config:** Successfully set up ORFS for a mixed-signal SoC.
✅ **Macro Integration:** Placed Analog IP (DAC/PLL) and routed power correctly.
✅ **Congestion:** Solved routing blockages by optimizing tapcell distribution.
✅ **Routing:** Achieved a DRC-clean routed layout.
✅ **Sign-off:** Generated GDSII and SPEF for fabrication and final timing check.

-----

# 🎉 **Final Conclusion**

The **VSDBabySoC** project is now complete. We have successfully taken a RISC-V based design from **RTL** (Verilog/TL-Verilog) through **Synthesis**, **Physical Design**, and **Sign-off**, integrating custom analog IP along the way. This repository serves as a complete reference for the Open-Source ASIC Implementation Flow.
