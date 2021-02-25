# Reverse Engineering

[INE Practical Reverse Engineering course](https://my.ine.com/CyberSecurity/courses/eac457f2/practical-reverse-engineering)

Notes from the course

----
# Prerequisites
[Olly Debugger](http://www.ollydbg.de/)

[HxD Hex Editor](http://www.mh-nexus.de/en/hxd/)

----

# String references and basic patching

When you load the exe in OllyDbg, you will be at the `EP` (Entry Point)

A 'naked' function directs the compiler to not create a prologue/epilogue, and is handled manually.

## OllyDbg 

### Searching for a string

CPU window > right click, Search For > All referenced text strings

Double click on string address, to go to the code where it is referenced.

### Find code in EXE file (not memory)

Highlight selected bytes > right click, Copy to executable > Selection

This will give you the VA of the instruction in the EXE file

## Patching a JMP
- Use `NOP`s (`0x90`)
- Change JMP logic `JZ` (`0x74`) <-> `JNZ` (`0x75`)
- Change JMP offset

## HxD 
- Open the EXE
- Find the memory (Ctrl + G)
- Patch and save

----
