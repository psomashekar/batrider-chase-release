BATRIDER: CHASE! -- N64 / PS VITA PACKAGE MAKER
===============================================                    (commit d20fac4, 2026-10-22)

Batrider: Chase! is an arrangement of Raizing's Armed Police Batrider by Coin-Op Game Studio. This
kit makes it for the Nintendo 64 (batrider_n64_chase.z64) and the PS Vita (batrider_vita.vpk) from
your own copy of the arcade ROM images. Both include both games: CHASE! and the original Armed
Police Batrider (1998), on one title screen.

The kit contains no readable game data. Its files in kit/ are encrypted with a key computed from the
contents of the arcade ROM images: they open only with correct dumps, so the kit is of no use without
your own ROMs. Nothing is installed or downloaded, and your files are only read, never changed.


WHAT YOU NEED
-------------
MAME's Armed Police Batrider, Japan, B version (Fri Feb 13 1998): "batriderj". Its parent's split
set (batriderj.zip together with batrider.zip) works, and so do a merged batrider.zip that holds the
batriderj clone, a non-merged batriderj.zip, and loose files in a folder. The eleven files:

  prg0b.u22  prg1b.u23  prg2.u21  prg3.u24     program
  snd.u77                                      sound program
  rom-1.bin  rom-2.bin  rom-3.bin  rom-4.bin   graphics
  rom-5.bin  rom-6.bin                         sound samples

Each file is checked by its size, CRC32 and SHA-1. The other versions (Europe, USA, China, Korea,
Taiwan, and the Japanese A version from 1997) have a different program and will not open the kit.


MAKING THE PACKAGES
-------------------
Windows: put your ROM zips in the roms folder and double-click batrider-kit.exe.

From a command prompt or terminal in this folder (Linux: batrider-kit-linux; macOS:
batrider-kit-macos-arm64 on Apple silicon, batrider-kit-macos-intel on Intel Macs):

  batrider-kit                                    both systems, ROMs from the roms folder
  batrider-kit n64                                the N64 only
  batrider-kit vita                               the Vita only
  batrider-kit --roms D:\mame\roms                ROMs from another folder
  batrider-kit --out D:\out                       another output folder

(macOS may refuse to start a program from the internet: right-click it, Open, then Open again.)

The packages go to the output folder: n64/, vita/ and the manuals in manual/. Each package is
checked before it is written. Keep the kit folder beside the program, as it came.


INSTALLING
----------
Nintendo 64: copy n64/batrider_n64_chase.z64 to a flash cart (SummerCart64, EverDrive 64).
It needs the 8 MB Expansion Pak; saves go to the cartridge's EEPROM (16K, set by the image's header).

PS Vita: install vita/batrider_vita.vpk with VitaShell on a Vita running HENkaku / Enso.

Both boot to the CHASE! title: START plays the mode chosen in the host menu, CHASE! or ORIGINAL,
and each mode keeps its own high scores. The instruction booklets for each system (English and
Japanese) are in manual/.


IF SOMETHING GOES WRONG
-----------------------
Not found (or not the right version) -- those files were not in what you gave the kit, or a file of
           that name is not the right dump (another version's, a patched or damaged file). Get
           good dumps of them.
The ROM set checks out but does not open this kit -- the kit is from another version of the game.
The kit's files were not found -- keep the kit folder beside the program, as it came.


The packages you make hold data from your ROM images: they are for your own use, not for
distribution. Armed Police Batrider is (c) 1998 Raizing / 8ing. Batrider: Chase! is a fan
arrangement and is not affiliated with them.
