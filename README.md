# Ghidra-GDB-Game-Debugging

This repository contains a reverse engineering project focused on debugging and patching a legacy Snake game written in C. 

The original game frequently crashed with a `SIGSEGV` (Segmentation fault) when the player picked up a specific item (flask). 

**Tools Used:** GDB, Ghidra

**The Bug & Fix:**
- Analyzed the binary and traced the crash to a null-pointer dereference in the `takeHpMedcine` function.
- The crash occurred because `p->nxt` was being accessed without checking if it was null inside a loop.
- Patched the binary logic by modifying the assembly instructions to validate `p->nxt` before execution, which permanently fixed the crash.

**Repository Structure:**
- `game_patched`: The fixed Linux executable.
- `Patch_Proof_Demo.mkv`: A short demo video showing the fixed gameplay without crashes.
- `Reverse_Engineering_Report.pdf`: Full step-by-step technical analysis and patching process (in Persian).
