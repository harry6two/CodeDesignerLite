# CodeDesignerLite
v1.06 Changes
- Corrected bug where the "print" command was not compiling to the correct address when using a custom address format with pnach enabled.

Modern version of Code Designer 2.3(originally created by Gtlcpimp)

[About]
- Code Designer Lite is based on Code Designer 2.3 by Gtlcpimp.
- It compiles mips assembly instructions into a raw code format for Playstation 2 cheat devices or PCSX2 pnach files.
- FORMAT can overwrite the first character in an address. FORMAT is ignored when using the "-" character.
- Compile errors are listed in the output window using this format: Line# FileName ErrorMessage

![cds5](https://github.com/user-attachments/assets/c08b6671-ed45-405a-bbee-8ddfd6a41114)


[Custom instructions]
```
// set memory location
address $000A0000
// jump or branch to label
jal :label
nop
beq v0, zero, :label:
nop
// print text
print "bla bla bla"
// import files
import "imports/test.cds"
// raw data
hexcode $64
hexcode :label
// set register to value or label
setreg t0, $3F800000
setreg t0, :label
// set label
label:
// float commands convert decimal values to float values
float $-1
float $1.00
float $10.5
// easy branch, b is treated as a standard branch like: beq zero, zero, :label
b :label
nop
// labels starting with "FNC" are bold indicating the start of a function
FNC_Label:
fncLabel:
// multiple formats are supported
addiu $s0, $v0, 0x10
addiu s0, v0, 0x10
addiu s0, v0, $10
// float registers are highlighted unless using $ format
mtc1 f0, t0
mtc1 $f0, t0
```
