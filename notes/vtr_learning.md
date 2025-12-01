# VTR Notes

## WTF is VTR?

VTR = Verilog to Routing

It takes Verilog code → does magic → places it on an FPGA

```
Verilog (.v file)
    ↓
ODIN II (converts to simpler format)
    ↓
ABC (optimizes the logic)
    ↓
VPR (places & routes on FPGA)
    ↓
Output (timing, area, etc.)
```

## Installation

Using **v9.0.0** (stable release)

```bash
# Get dependencies (Ubuntu/Debian)
sudo apt install build-essential cmake python3 libcairo2-dev

# Download and extract VTR v9.0.0
wget https://github.com/verilog-to-routing/vtr-verilog-to-routing/releases/download/v9.0.0/vtr-verilog-to-routing-9.0.0.tar.gz
tar -xzf vtr-verilog-to-routing-9.0.0.tar.gz
cd vtr-verilog-to-routing-9.0.0
make -j4

# Test
./vtr_flow/scripts/run_vtr_flow.py -h
```

### If it breaks:
- Missing cairo? → `sudo apt install libcairo2-dev`
- Out of memory? → Use `make -j2` instead
- Other stuff? → Google the error, check VTR GitHub issues

## Running VTR

```bash
# Basic run
./vtr_flow/scripts/run_vtr_flow.py <circuit.v> <architecture.xml>
```

## Things I learned

### Architecture files (.xml)
[Add notes as you figure it out]

### Benchmarks
[What benchmarks did you run?]

## Commands I keep forgetting

```bash
# TODO: add useful commands here
```

## Tutorials completed
- [ ] Tutorial 1: Basic VTR flow
- [ ] Tutorial 2: ??? 

## Stuff that confused me
-
