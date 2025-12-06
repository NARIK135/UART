# UART Verilog Module (Transmitter + Receiver)

This repository contains a basic UART (Universal Asynchronous Receiver/Transmitter) implementation in Verilog HDL.  
It includes separate modules for UART Transmission and Reception, along with a top-level UART wrapper.

---

## 🚀 Features

- 8-bit data transmission
- 1 parity bit support
- 1 start + 1 stop bit
- Parameterized clock and baud rate
- Clean state machine design in both TX and RX
- Loopback-capable UART

---

## 🔧 Default Configuration

| Parameter  | Value |
|-----------|-------|
| System Clock (`clk_freq`) | 5 MHz |
| Baud Rate | 2.5 Mbps |
| Clocks per Bit | 2 |
| Data Bits | 8 |
| Parity Bit | 1 (auto generated) |
| Stop Bit | 1 |

---

## 🧩 Module List

| Module | Description |
|--------|-------------|
| `UART` | Top-level wrapper: TX + RX connected together |
| `UART_tx` | Transmitter – sends 8 data bits + parity |
| `UART_rx` | Receiver – receives and outputs 8 data bits + parity |

---

## 📜 Top-Level Interface

```verilog
module UART(
    input        clk,
    input        reset,
    input  [7:0] data_tx,
    input        sent,
    output       recevied,
    output [8:0] data_rx
);
