# ⏰ VHDL Digital Clock – 7-Segment Display

This VHDL project implements a simple digital clock using a 4-digit 7-segment display and push buttons on an FPGA board.

---

## 🔧 Features

- 4-digit time display (00–99 for two separate values)
- Button control:
  - `btnL`: switch modes (display, set digit1, set digit2)
  - `btnR`: increment selected digit
  - `btnC`, `btnU`, `btnD`: optional actions (e.g., reset, confirm)
- Blinking for active digit while editing
- Debounce logic to clean button inputs

---

## 📦 Components

- `driver7seg`: Controls the 7-segment display
- `debounce`: Filters button bounce
- `ceas.vhdl`: Main logic with FSM for state transitions and digit handling

---

## 💡 FSM States

1. `afis_scor`: Show current value
2. `set_digit1`: Edit first pair of digits
3. `set_digit2`: Edit second pair
4. `set_scor`: Save and return to display

---

## 🛠️ Inputs/Outputs

| Signal     | Direction | Description                    |
|------------|-----------|--------------------------------|
| `CLK100MHZ`| in        | 100 MHz system clock           |
| `btnL–btnC`| in        | Control buttons                |
| `seg`      | out       | Segment control (a–g)          |
| `an`       | out       | Display enable (4 digits)      |
| `dp`       | out       | Decimal point (unused)         |

---

## ▶️ Usage

Designed for FPGA boards with 4-digit 7-segment displays (e.g., Basys 3). Simulate in ModelSim or deploy to hardware using Vivado.

