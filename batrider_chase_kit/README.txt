Batrider: Chase! -- the kit for the N64 and the PS Vita
========================================================

This kit makes the Batrider: Chase! packages for the Nintendo 64 and the PlayStation Vita
from your own copy of the arcade game's ROM set. The packages in the kit are sealed: they are
opened with a key taken from the ROM set itself, so the kit is of no use without it, and it
contains no part of the game you do not already own.


1. What you need

   Armed Police Batrider, Japan, B version (Fri Feb 13 1998) -- MAME's "batriderj" -- as any of:

     - batriderj.zip together with its parent batrider.zip   (a MAME split set)
     - a merged batrider.zip that holds the batriderj clone
     - a non-merged batriderj.zip
     - the loose ROM files (prg0b.u22, prg1b.u23, prg2.u21, prg3.u24, snd.u77,
       rom-1.bin ... rom-6.bin)

   The other versions (Europe, USA, China, Korea, Taiwan, and the Japanese A version from 1997)
   have a different program and will not open the kit. Your files are only read, never changed,
   and nothing is sent anywhere.


2. Making the packages

   Windows:  put the ROM zips in the roms folder and double-click batrider-kit.exe.

   Or, from a command prompt or a terminal (any system):

     batrider-kit.exe                        both platforms, ROMs from the roms folder
     batrider-kit.exe n64                    the N64 alone
     batrider-kit.exe vita --roms D:\mame\roms
     batrider-kit.exe --out D:\batrider      somewhere else than the output folder

   On Linux run ./batrider-kit-linux, on a Mac ./batrider-kit-macos-arm64 (Apple silicon) or
   ./batrider-kit-macos-intel, with the same options. (macOS may ask you to allow it first:
   System Settings > Privacy & Security, or: xattr -d com.apple.quarantine batrider-kit-macos-*)

   The program finds the ROM files, checks each one, and writes:

     output/n64/batrider_n64_chase.z64
     output/vita/batrider_vita.vpk
     output/manual/   the instruction manuals, in English and Japanese


3. Playing

   N64   Copy batrider_n64_chase.z64 to a flashcart (SummerCart64, EverDrive 64, ...).
         It needs the Expansion Pak. Save type: EEPROM 16K.

   Vita  Copy batrider_vita.vpk to the Vita and install it with VitaShell.

   Both boot to the CHASE! title: START plays the mode chosen in the host menu, CHASE! or
   ORIGINAL (the original game), and each mode keeps its own high scores. The manuals have the
   rest.


The kit folder holds the sealed packages (kit.json lists them). Keep it beside the program.
