🖥️ RTL + UVM IP Library

A complete SystemVerilog RTL + UVM verification library containing fundamental building blocks, protocols, and SoC-level projects.
This repo is structured tier-wise to cover combinational, sequential, memory, buses, protocols, and SoC integrations, each with:

✅ Synthesizable RTL (SystemVerilog)

✅ UVM Testbench (transaction → driver → monitor → scoreboard → coverage)

✅ Assertions (SVA) for protocol checks

✅ Documentation (schematics, block diagrams, PDFs)

✅ Simulation results (waveforms, coverage reports)

📂 Repository Structure
uvm-projects
│── docs/                  # Notes, schematics, reports
│── common/                # Packages, interfaces, utilities
│
│── combinational/         # Adders, muxes, encoders, decoders
│   ├── full_adder/
│   ├── carry_select_adder/
│   ├── booth_multiplier/
│   └── ...
│
│── sequential/            # Counters, FSMs, flip-flops
│   ├── bcd_counter/
│   ├── moore_fsm/
│   ├── traffic_light_controller/
│   └── ...
│
│── memory/                # Caches, SRAM, DRAM controllers
│   ├── direct_mapped_cache/
│   ├── dual_port_sram/
│   ├── generic_dram_controller/
│   └── ...
│
│── bus_protocols/         # AXI, APB, TileLink, PCIe
│   ├── axi_protocol_monitor/
│   ├── apb_controller/
│   ├── tilelink/
│   └── ...
│
│── interfaces/            # Serial & parallel interfaces
│   ├── uart_tx_rx/
│   ├── spi_master_slave/
│   ├── i2c_master_slave/
│   ├── ethernet_mac/
│   └── usb/
│
│── soc_projects/          # Integration-level projects
│   ├── simple_soc/
│   ├── riscV_soc/
│   └── ...
│
│── results/               # Waveforms, coverage, reports
│   ├── waveform/
│   ├── uvm_results/
│   └── coverage_reports/
│
│── README.md              # Overview of repo

🚀 Getting Started
Prerequisites

Simulator: Mentor Questa / Synopsys VCS / Cadence Xcelium / Aldec Riviera / EDA Playground

Synthesis: Xilinx Vivado / Synopsys Design Compiler (optional)

Languages: SystemVerilog, UVM 1.2 / IEEE UVM 1800.2

Run Simulation
# Example (QuestaSim)
vlog -sv combinational/full_adder/*.sv tb/full_adder_tb.sv +incdir+common
vsim -c work.full_adder_tb -do "run -all; quit"

Run UVM Test
vlog -sv +incdir+common +incdir+uvm_src *.sv
vsim -uvmdebug -do "run -all"

📊 Coverage & Verification Goals
Category	Blocks Implemented	Coverage Goal
Combinational	Adders, Multipliers, Shifters	95%+
Sequential	Counters, FSMs, Shift Regs	95%+
Memory	SRAM, DRAM, Cache	90%+
Bus Protocols	AXI, APB, TileLink, PCIe	90%+
Interfaces	UART, SPI, I2C, USB, Ethernet	90%+
SoC Projects	4 mini SoCs	Full regression
📑 Documentation

Each block includes:

📘 RTL Design Spec

📝 FSM diagrams / Block Diagrams

🧪 UVM Test Plan

📈 Waveforms & Coverage Reports
