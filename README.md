# Batrider: Chase!

**Batrider: Chase!** is a new way to play Raizing's *Armed Police Batrider* (1998) on the **Nintendo 64** and the
**PlayStation Vita**. It boots to the CHASE! title: START plays the mode chosen in the host menu, either **CHASE!** or
**ORIGINAL** (the arcade game as it was), and each mode keeps its own high scores.

This repository holds no part of the game. The packages are sealed, and the only key that opens them is the arcade
ROM set you already own: the builder kit reads your ROMs, checks them, and writes the N64 ROM and the Vita VPK from
them on your own computer.

## What's here

| folder | what it is |
|---|---|
| [`batrider_chase_kit/`](batrider_chase_kit/) | the builder kit: the `batrider-kit` program for Windows, Linux and macOS, and the sealed packages |
| [`n64/manual/`](n64/manual/) | the N64 instruction manual, in English and Japanese, on screen and ready to print |
| [`n64/box/`](n64/box/) | the N64 cartridge label and box art, ready for a printer ([`n64/README.md`](n64/README.md)) |

## 1. What you need

**Armed Police Batrider, Japan, B version (Fri Feb 13 1998)**: MAME's `batriderj`, in any of these forms:

- `batriderj.zip` together with its parent `batrider.zip` (a MAME split set)
- a merged `batrider.zip` that holds the `batriderj` clone
- a non-merged `batriderj.zip`
- the loose ROM files: `prg0b.u22`, `prg1b.u23`, `prg2.u21`, `prg3.u24`, `snd.u77`, `rom-1.bin` ... `rom-6.bin`

The other versions (Europe, USA, China, Korea, Taiwan, and the Japanese A version from 1997) have a different program
and will not open the kit. Your files are only read, never changed, and nothing is sent anywhere.

Nothing needs to be installed: the kit's programs stand alone.

## 2. Making the packages

1. Download this repository (**Code > Download ZIP**, or `git clone`) and unzip it.
2. Put your ROM zips in `batrider_chase_kit/roms/`.
3. Run the kit:
   - **Windows:** double-click `batrider_chase_kit/batrider-kit.exe`.
   - **Linux:** `./batrider-kit-linux`
   - **macOS:** `./batrider-kit-macos-arm64` (Apple silicon) or `./batrider-kit-macos-intel` (Intel)

On Linux and macOS, run it from a terminal in the `batrider_chase_kit` folder. If it will not start, make it
executable first (`chmod +x batrider-kit-*`). macOS may also ask you to allow it: open **System Settings > Privacy &
Security**, or run `xattr -d com.apple.quarantine batrider-kit-macos-*`.

The kit finds the ROM files, checks each one (size, CRC32 and SHA-1), and writes:

```
output/n64/batrider_n64_chase.z64
output/vita/batrider_vita.vpk
output/manual/        the N64 and Vita manuals, in English and Japanese
```

Each package is checked against its size and SHA-256 as it is written.

### Options

The same options work on every system (shown here with the Windows name):

```
batrider-kit.exe                        both platforms, ROMs from the roms folder
batrider-kit.exe n64                    the N64 alone
batrider-kit.exe vita --roms D:\mame\roms
batrider-kit.exe --out D:\batrider      write somewhere other than the output folder
```

Keep the `kit/` folder beside the program: it holds the sealed packages (`kit.json` lists them).

## 3. Playing

**Nintendo 64.** Copy `batrider_n64_chase.z64` to a flashcart (SummerCart64, EverDrive 64, ...).

- The console needs the **Expansion Pak** (8 MB). Without one, the game stops on an "Expansion Pak required" screen.
- Save type: **EEPROM 16K**. It keeps the settings, the OPTIONS and each mode's rankings.
- To make a cartridge of your own, with its label and box, see [`n64/README.md`](n64/README.md).

**PlayStation Vita.** Copy `batrider_vita.vpk` to the Vita and install it with VitaShell.

The manuals cover the rest: the controls, CHASE!'s rules, the options and the host menu.

## Troubleshooting

- **"Not found (or not the right version)":** the kit needs the Japanese B version (`batriderj`) exactly. Check that
  both `batriderj.zip` and its parent `batrider.zip` are in the `roms` folder, or point `--roms` at your MAME `roms`
  folder.
- **"The kit's files were not found":** keep the `kit/` folder beside the program, as it came.
- **The N64 shows "Expansion Pak required":** fit an Expansion Pak in the console's top slot.
- **No high scores are kept on the N64:** set the flashcart's save type to EEPROM 16K.

## Copyright

Batrider: Chase! and the builder kit © 2026 Pramod Somashekar. All rights reserved.

*Armed Police Batrider* © 1998 Raizing / Eighting. Nintendo 64 is a trademark of Nintendo. PlayStation and PlayStation
Vita are trademarks of Sony Interactive Entertainment. This project is not affiliated with or endorsed by any of them.
