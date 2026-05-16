# 02 - ALU (Arithmetic Logic Unit)

Second project in my RISC-V journey — building a simple ALU that performs basic arithmetic operations.

---

## What is an ALU?

The ALU is the brain of the CPU. It performs all arithmetic and logic operations.

---

## Operations

| $op | Binary | Operation | Description |
|-----|--------|-----------|-------------|
| 0   | 2'b00  | +         | Addition    |
| 1   | 2'b01  | -         | Subtraction |
| 2   | 2'b10  | *         | Multiply    |
| 3   | 2'b11  | /         | Division    |

---

## How It Works

```
$val1 and $val2 → go into all 4 operations simultaneously
$op             → selects which result comes out
$out            → the final result
```

Think of it like a radio — all stations broadcast at once, but you pick one with the remote (`$op`).

---

## Code

```tlv
$sum[31:0]  = $val1[31:0] + $val2[31:0];
$diff[31:0] = $val1[31:0] - $val2[31:0];
$prod[31:0] = $val1[31:0] * $val2[31:0];
$quot[31:0] = $val1[31:0] / $val2[31:0];

$out[31:0] = $op[1:0] == 2'b00 ? $sum  :
             $op[1:0] == 2'b01 ? $diff :
             $op[1:0] == 2'b10 ? $prod :
                                 $quot;
```

---

## Tools

- **TL-Verilog** — Hardware description language
- **Makerchip** — Online simulation IDE

---

## Project Journey

```
01-full-adder     ✅
02-alu            ✅
03-risc-v-cpu
...
```
