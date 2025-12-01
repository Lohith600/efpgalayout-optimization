# Experiment Log

Just write what you did each day. Nothing fancy.

---

## Dec 1 - Karthikeya

**What I tried:**
- Set up GitHub repo with proper structure
- Installed VTR on Fedora 43

**What worked:**
- VTR compiles and runs!
- Ran `tseng` benchmark successfully
- Result: 152 MHz, 11x11 FPGA grid, routed in 12 iterations

**What broke:**
- Fedora's Clang 21 is too new for yosys code
- Had to patch `yosys/libs/json11/json11.cpp` with `#include <cstdint>`  
- Missing headers: `tcl.h`, `readline.h`, `ffi.h` - installed dev packages

**Random notes:**
- Build took ~20 mins with `-j16` on Ryzen 7
- Python scripts need `prettytable` package
- Created venv at `~/vtr-verilog-to-routing/venv/`
- Wrote easy Ubuntu guide for Lohith

**VTR Test Output (for reference):**
```
Circuit: tseng (1605 blocks, 1483 nets)
FPGA: 11x11 grid, 54 CLBs, 174 IOs
Routing: Succeeded in 12 iterations
Critical path: 6.57 ns (152 MHz)
Total time: 1.18 seconds
```

---

## Dec 1 - Lohith

**What I tried:**


**What worked:**


**What broke:**


**Random notes:**

---

## Dec X (copy this for new entries)

**What I tried:**


**What worked:**


**What broke:**


**Random notes:**
