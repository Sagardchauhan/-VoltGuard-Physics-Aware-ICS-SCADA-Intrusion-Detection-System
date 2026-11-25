# VoltGuard
### Physics-Aware ICS/SCADA Intrusion Detection System

VoltGuard is a simulation-based industrial cybersecurity project designed to demonstrate physics-aware command validation for Industrial Control Systems (ICS) and Supervisory Control and Data Acquisition (SCADA) environments.

Unlike traditional network monitoring systems that primarily analyze packet-level information, VoltGuard aims to evaluate industrial control commands against security policies and simulated physical safety constraints.

The project integrates network traffic processing, command analysis, physics simulation, decision logic, and security event logging into a unified application.

> **Project Status:** Simulation Prototype  
> **Environment:** Simulated industrial network and equipment  
> **Purpose:** Educational and cybersecurity research

---

## Project Overview

VoltGuard demonstrates how cybersecurity and physical process validation can be combined to identify and reject potentially unsafe industrial control commands.

For example, a simulated command requesting an excessive pump speed can be evaluated against the configured physical safety limits before being accepted by the decision engine.

## Key Features

- Simulated industrial network traffic generation
- Modbus/TCP command processing
- C++ packet parsing
- Rust-based decision engine
- Physics-aware command validation
- Simulated industrial process monitoring
- Security event logging
- SQLite-based event storage
- Hash-chain integrity verification
- Qt-based desktop dashboard
- System health and component monitoring
- Automated testing and preflight checks

## System Architecture

The VoltGuard pipeline is designed around the following components:

1. **Traffic Generator**  
   Generates simulated industrial network traffic.

2. **C++ Packet Parser**  
   Parses and extracts protocol information and control commands.

3. **Rust Decision Engine**  
   Evaluates commands using configured security and decision logic.

4. **Physics Simulation Engine**  
   Checks commands against simulated physical constraints.

5. **Event Logging System**  
   Records security events and command decisions in SQLite.

6. **Qt Dashboard**  
   Displays traffic statistics, system status, security alerts, and simulation results.

## Dashboard Modules

### System Overview
Displays component status, system statistics, traffic information, and the integrated processing pipeline.

### Live Traffic Monitoring
Visualizes simulated industrial traffic and protocol activity.

### Decision Engine
Displays incoming commands, physics validation results, risk information, and command decisions.

### Physics Simulation
Monitors simulated process parameters such as pump speed, pressure, and flow.

### Security Events
Displays rejected commands, anomalies, and security-related incidents.

### Event Logs
Provides access to recorded events and integrity verification information.

## Technology Stack

| Technology | Purpose |
|---|---|
| Python | Application logic and orchestration |
| C++ | Packet parser |
| Rust | Decision engine |
| Qt 6 | Desktop dashboard |
| Scapy | Network packet processing |
| SQLite | Event storage |
| CMake | C++ build system |
| pytest | Python testing |

## Project Structure

```text
VoltGuard/
├── voltguard/
├── physics_engine/
├── packet_interceptor/
├── decision_engine/
├── dashboard/
├── traffic_generator/
├── event_logging/
├── config/
├── tests/
├── scripts/
├── requirements.txt
├── CMakeLists.txt
└── README.md
```

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/VoltGuard.git
cd VoltGuard
```

### 2. Create a Python virtual environment

```bash
python -m venv venv
```

Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

### 3. Install Python dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Build the project

Install the required C++ compiler, CMake, Rust toolchain, and Qt 6 development components.

Build the C++ components:

```bash
cmake -S . -B build
cmake --build build --config Release
```

Build the Rust decision engine:

```bash
cargo build --release --manifest-path decision_engine/Cargo.toml
```

## Running VoltGuard

Run the Python startup module:

```bash
python -m voltguard.main
```

Run the preflight check:

```bash
python scripts/preflight.py
```

Launch the simulation demo:

```powershell
.\scripts\demo.ps1
```

The demo script is intended to perform the preflight check and launch the configured dashboard.

## Testing

Run Python tests:

```bash
python -m pytest -v
```

Run C++ tests:

```bash
ctest --test-dir build -C Release --output-on-failure
```

Run Rust tests:

```bash
cargo test --manifest-path decision_engine/Cargo.toml
```

## Safety Notice

VoltGuard is a simulation-based educational prototype.

It is not intended to control, modify, or protect live industrial equipment. All demonstrations should use simulated traffic and simulated process values.

Do not connect the prototype to production ICS/SCADA networks or live industrial machinery.

## Project Goals

- Explore physics-aware industrial command validation
- Demonstrate multi-language cybersecurity application architecture
- Simulate industrial protocol processing
- Study security decision-making and event integrity
- Develop a modular industrial cybersecurity dashboard

## Author

**Sagar Chauhan**

Cybersecurity | Industrial Network Security | Software Development

---

VoltGuard — Bringing physical safety awareness into industrial cybersecurity.
