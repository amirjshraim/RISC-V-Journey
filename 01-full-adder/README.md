# 01 - Full Adder

First project in my journey of building a RISC-V CPU from scratch.

## What is a Full Adder?

A logic circuit that adds 3 binary digits (0 or 1):
- **$in1** — First input
- **$in2** — Second input
- **$carry_in** — Carry from a previous addition

And produces two outputs:
- **$out** — Sum result
- **$carry_out** — Carry to the next addition

## Logic

```
$xor = $in1 XOR $in2
$out = $xor XOR $carry_in
$carry_out = ($xor AND $carry_in) OR ($in1 AND $in2)
```

## Truth Table

| $in1 | $in2 | $carry_in | $out | $carry_out |
|------|------|-----------|------|------------|
| 0    | 0    | 0         | 0    | 0          |
| 1    | 0    | 0         | 1    | 0          |
| 1    | 1    | 0         | 0    | 1          |
| 1    | 1    | 1         | 1    | 1          |

## Tools

- **TL-Verilog** — Hardware description language
- **Makerchip** — Online simulation IDE

## Project Journey

```
01-full-adder     ✅
02-alu
03-risc-v-cpu
...
```