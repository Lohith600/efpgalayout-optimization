# VTR Basics

## What VTR Does

Takes your circuit → Maps it to an FPGA → Tells you how fast it runs

```
Verilog/BLIF → [Synthesis] → [Packing] → [Placement] → [Routing] → Results
```

## The Only Commands You Need

### 1. Run VPR directly (fastest way)

```bash
cd ~/vtr-verilog-to-routing

./vpr/vpr ARCHITECTURE.xml CIRCUIT.blif --route_chan_width 100
```

Example:
```bash
./vpr/vpr vtr_flow/arch/timing/EArch.xml vtr_flow/benchmarks/blif/tseng.blif --route_chan_width 100
```

### 2. Run full flow (from Verilog)

```bash
source venv/bin/activate

./vtr_flow/scripts/run_vtr_flow.py CIRCUIT.v ARCHITECTURE.xml
```

Example:
```bash
./vtr_flow/scripts/run_vtr_flow.py vtr_flow/benchmarks/verilog/diffeq1.v vtr_flow/arch/timing/EArch.xml
```

### 3. Run full flow (from BLIF)

```bash
./vtr_flow/scripts/run_vtr_flow.py CIRCUIT.blif ARCHITECTURE.xml -start abc
```

## File Types

| Extension | What it is |
|-----------|------------|
| `.v` | Verilog - your circuit design |
| `.blif` | Already synthesized circuit (skip yosys) |
| `.xml` | FPGA architecture definition |

## Where Files Are

```
~/vtr-verilog-to-routing/
├── vpr/vpr                              # The main tool
├── vtr_flow/
│   ├── arch/timing/EArch.xml            # Default architecture
│   └── benchmarks/
│       ├── blif/                        # Pre-synthesized circuits
│       └── verilog/                     # Verilog circuits
```

## Output That Matters

After running, look for:
```
Final critical path delay: X.XX ns, Fmax: XXX MHz   ← How fast
VPR succeeded                                        ← It worked
```

## Common Options

```bash
--route_chan_width 100    # Routing width (higher = easier to route)
--seed 1                  # Random seed (for reproducibility)
```

## That's It

Run command → Get MHz → Done.
