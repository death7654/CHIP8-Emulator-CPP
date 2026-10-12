# CHIP8-Emulator

![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![SDL2](https://img.shields.io/badge/SDL2-1B6AC9?style=flat-square)
![Status](https://img.shields.io/badge/Audio-not_implemented-lightgrey?style=flat-square)

A CHIP-8 interpreter written in C++, built by following Austin Morlan's guide, [Writing a CHIP-8 Emulator](https://austinmorlan.com/posts/chip8_emulator/).

CHIP-8 is a small virtual machine from the 1970s, originally used to run simple games on hobbyist computers. It has 4 KB of memory, sixteen 8-bit registers, a 64x32 monochrome display and a 16-key hexadecimal keypad, which makes it a common first emulator project.

## Status

| Component | State |
|---|---|
| CPU (fetch, decode, execute) | Implemented |
| Display | Implemented |
| Keypad input | Implemented |
| Timers | Implemented |
| Audio | **Not implemented** (TODO) |

## Build

Requires a C++17 compiler and SDL2.

```bash
git clone https://github.com/death7654/CHIP8-Emulator-CPP.git
cd CHIP8-Emulator-CPP
# Adjust to match your build setup
g++ -std=c++17 *.cpp -o chip8 -lSDL2
```

## Usage

```bash
./chip8 <Scale> <Delay> <ROM>
```

| Argument | Meaning |
|---|---|
| `Scale` | Integer multiplier for the 64x32 display (for example, `10` gives a 640x320 window) |
| `Delay` | Milliseconds between CPU cycles. Lower is faster, and the right value varies by ROM |
| `ROM` | Path to a CHIP-8 ROM file |

Example:

```bash
./chip8 10 1 roms/test_opcode.ch8
```

### Keypad mapping

The original 4x4 hex keypad maps onto the left side of a QWERTY keyboard:

```
CHIP-8 keypad        Keyboard
+---+---+---+---+    +---+---+---+---+
| 1 | 2 | 3 | C |    | 1 | 2 | 3 | 4 |
| 4 | 5 | 6 | D |    | Q | W | E | R |
| 7 | 8 | 9 | E |    | A | S | D | F |
| A | 0 | B | F |    | Z | X | C | V |
+---+---+---+---+    +---+---+---+---+
```

## Roadmap

- [ ] Audio (the CHIP-8 sound timer should trigger a tone while it is above zero)

## Credits

This project follows [Austin Morlan's CHIP-8 emulator guide](https://austinmorlan.com/posts/chip8_emulator/), and the structure of the emulator comes from that tutorial. If you want to build your own, I recommend reading it.

## Related

My other CHIP-8 work goes further than this implementation:
- [Chip8-JIT-Rust](https://github.com/death7654/Chip8-JIT-Rust): a CHIP-8 emulator with an x86-64 JIT compiler
- [XO-Chip-Emulator-Zig](https://github.com/death7654/XO-Chip-Emulator-Zig): XO-CHIP support in Zig
- [Chip8-Emulator-Rust](https://github.com/death7654/Chip8-Emulator-Rust): a Rust implementation
