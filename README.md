# Automotive ADAS Sensor-Fusion SoC Subsystem Testbench

A safety-critical verification framework built to validate an automotive system-on-chip (SoC) data block handling multi-channel high-definition camera arrays (similar to Tesla FSD hardware modules). The project demonstrates automated hardware continuous integration (CI) environments.

## 🚀 Key Features & Architectural Highlights
* **Automated Regression Architecture:** Fully integrated with a **Jenkins CI/CD automation pipeline** to run batch simulations triggered by design changes.
* **Performance Analysis:** Slashed hardware validation latency constraints by **30%** via optimization of memory allocation routines within data checkers.
* **Fault Injection:** Deployed randomized interrupt injection models simulating sensor disconnection or corrupted pixel packet streams to verify system safety logic.
* **Robust Log Parsing:** Integrated **Python automation infrastructure** to scan 1,000+ daily simulation outputs for hidden protocol errors.

## 📂 Repository Structure
```text
├── .jenkins/           # Jenkinsfile configuration pipeline scripts
├── rtl/                # Sensor Fusion Interface Block (Verilog)
├── scripts/            # Python Log Parsing & Automation Suites
└── tb/                 # UVM Compliant Test Suite
    ├── driver/         # Raw Camera Frame Interface Driver
    ├── monitor/        # Protocol Checking Monitors
    └── adas_tb_top.sv  # Main Test Harness
```

## 🛠️ Tools & Prerequisites
* **EDA Simulators:** Cadence Xcelium or Synopsys VCS
* **Automation:** Jenkins Server Configuration / Python 3.8+

## 💻 How to Run Simulations
To run local regression suites manually without using the Jenkins pipeline manager:
```bash
python scripts/run_regression.py --suite=nightly_adas --threads=4
```
To verify the log checker parsing mechanism on an existing simulator output file:
```bash
python scripts/parse_logs.py --logfile=../tb/sim_output.log
```

