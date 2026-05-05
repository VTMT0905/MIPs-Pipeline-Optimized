# MIPs-Pipeline-Optimized
## Update — Data Forwarding

Added data forwarding to the Execute stage to reduce the number of NOPs
needed between dependent instructions.

### Results

| Version | NOPs Needed | Cycles to Finish |
|---------|-------------|-----------------|
| Without forwarding | 15 NOPs | ~20 cycles |
| With forwarding | 2 NOPs | ~14 cycles |

### Files Changed
- `execute.v` — forwarding unit added
- `idExLatch.v` — added rs field pass-through
- `decode.v` — added rs output port
- `mips_pipeline.v` — wired forwarding signals

### Output
```
FINAL REGISTERS: r1=12 r2=2 r3=3
PASS: r1 is 12 as expected.
```
