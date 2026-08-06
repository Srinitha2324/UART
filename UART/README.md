# UART Transmitter using Verilog HDL

## Overview

A Universal Asynchronous Receiver Transmitter (UART) is a hardware communication protocol used for serial communication between digital devices. It transmits data one bit at a time over a single communication line.

This project implements an **8-bit UART Transmitter (TX)** using Verilog HDL.

---

## Features

- 8-bit data transmission
- Start bit generation
- Stop bit generation
- Configurable baud rate divider
- Busy status signal
- Synchronous design using a system clock

---

## UART Frame Format

```
| Start | D0 | D1 | D2 | D3 | D4 | D5 | D6 | D7 | Stop |
|   0   |              8 Data Bits             |   1  |
```

- **Start Bit:** Logic 0
- **Data Bits:** Least Significant Bit (LSB) first
- **Stop Bit:** Logic 1

---

## Inputs

| Signal | Description |
|---------|-------------|
| clk | System clock |
| rst | Active-high reset |
| tx_start | Start transmission |
| tx_data[7:0] | 8-bit data input |

---

## Outputs

| Signal | Description |
|---------|-------------|
| tx | UART serial output |
| busy | High while transmitting |

---

## Project Structure

```
UART-Transmitter/
├── src/
│   └── uart_tx.v
├── testbench/
│   └── uart_tx_tb.v
├── simulation/
│   ├── uart_tx.vcd
│   ├── waveform.png
│   └── output.txt
└── images/
    ├── uart_block_diagram.png
    └── uart_timing_diagram.png
```

---

## Expected Transmission

Example data:

```
tx_data = 8'b10100101
```

UART output sequence:

```
Start Bit : 0

Data Bits (LSB First):
1
0
1
0
0
1
0
1

Stop Bit : 1
```

---

## Tools Used

- Verilog HDL
- Icarus Verilog
- GTKWave
- ModelSim (Optional)

---

## Applications

- Microcontrollers
- FPGA Communication
- Embedded Systems
- GPS Modules
- Bluetooth Modules
- Serial Communication Interfaces

---

## How to Run

Compile:

```bash
iverilog -o uart_sim src/uart_tx.v testbench/uart_tx_tb.v
```

Run:

```bash
vvp uart_sim
```

View waveform:

```bash
gtkwave simulation/uart_tx.vcd
```

---

## Author

Your Name