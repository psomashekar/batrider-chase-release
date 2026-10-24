# Batrider: Chase! for the Nintendo 64: the manual, the label and the box

Everything here is ready to print. The ROM itself comes from the builder kit
([`../batrider_chase_kit/`](../batrider_chase_kit/), see the [main README](../README.md)).

## The manual

| file | what it is |
|---|---|
| `manual/batrider_chase_manual_n64.pdf` | the English manual, one page at a time, at its own size (117 × 173 mm), to read on screen |
| `manual/batrider_chase_manual_n64_ja.pdf` | the same in Japanese |
| `manual/print/batrider_chase_manual_n64_letter.pdf` | the English manual imposed two pages to a US Letter sheet, with crop marks |
| `manual/print/batrider_chase_manual_n64_ja_a4.pdf` | the Japanese manual imposed two pages to an A4 sheet, with crop marks |

To print the booklet: print the `print/` file **double-sided, flipped on the short edge, at 100 %** (not "fit to
page"), cut at the crop marks, fold, and staple. It is the size of an N64 manual and lies flat in the box.

## The label and the box

| file | what it is | send it to |
|---|---|---|
| `box/label_n64.pdf` | the front label, 54.5 × 62.5 mm trim + 2 mm bleed, art only | a sticker / label printer, with the cut file |
| `box/label_n64_cut.pdf` | the label's die line alone (magenta), on the same page | the same printer (the die-cut shape) |
| `box/label_n64_proof.pdf` | the two together, the safe area dashed in cyan | you, to check |
| `box/label_n64_600dpi.png` | the label's art with its bleed at 600 dpi (1382 × 1571) | a sticker shop that takes PNG, with `label_n64_cut.svg` |
| `box/label_n64_cut.svg` | the die line as SVG (`CutContour`), on the same page | a die maker, a cutting plotter |
| `box/label_n64_sheet_letter.pdf`, `_a4.pdf` | eight labels on a sheet with gray cut lines | your own printer, on sticker paper |
| `box/box_n64.pdf` | the box flat, 268 × 329 mm + 3 mm bleed (274 × 335 mm), art only | a packaging printer, with the die line |
| `box/box_n64_dieline.pdf` | its die alone: cut solid magenta, fold dashed blue, on the same page | the same printer |
| `box/box_n64_dieline.svg` | the die as SVG (`Cut`, `Fold`), on the same page | a die maker, a cutting plotter |
| `box/box_n64_proof.pdf` | the two together, the panels named | you, to check |
| `box/panels/box_*.png` | each face alone (front, back, both spines, both ends), upright, 3 mm bleed, 600 dpi | a shop with its own N64 box template |
| `box/box_n64_a3.pdf`, `_12x18.pdf` | the proof on one A3 / 12 × 18 in sheet with crop marks | a copy shop's large-format printer, cut by hand |

The type is vector; the art is 300 dpi, but on the box's front it is enlarged from about 150 dpi, so it looks a little
soft up close.

### The label

A North American Game Pak's front label: **54.5 mm wide × 62.5 mm tall**. The top edge is an arc of a 325 mm circle
(2.3 mm high across the label's width), with 4 mm corners at the top and 3 mm corners at the bottom. Reproduction
shells vary by a millimeter or so: **measure the recess on the shell you get** before you print a run.

Stock: glossy or matte white sticker vinyl (or paper), laminated if you can. Keep words 2 mm in from the edge (the
proof's cyan box).

### The box

A reverse tuck-end carton the size of a North American N64 game's box: **180 × 127 mm faces (landscape) and 31 mm
deep**. (Box protectors for it are made 182.6 × 128.6 × 33.3 mm inside.) The 117 × 173 mm manual lies flat inside it.
On the flat, the panels run down the sheet: the back (upside down), the top spine, the front, the bottom spine, and the
glue flap. The left end and its tuck are on the back, the right end and its tuck on the front, and the dust flaps on
the spines.

Stock: 16-18 pt (0.4-0.45 mm) SBS / C1S folding carton, gloss or matte laminated. Score the folds before folding them,
and glue the flap under the front's lower edge. A real box also has a cardboard tray to hold the cartridge; this one
has none.

## The cartridge

What `batrider_n64_chase.z64` needs from a board:

| | |
|---|---|
| ROM | **49,430,528 bytes (47.1 MB)**: a **512 Mbit (64 MB)** board. A 256 Mbit (32 MB) board, the common cheap kind, is too small |
| byte order | big-endian `.z64` (it starts `80 37 12 40`). Most flashing tools take it as it is; some want `.n64` (byte-swapped) |
| save | **EEPROM 16 Kbit (2 KB)**. It holds the settings, the OPTIONS and each mode's rankings. With a 4 Kbit EEPROM the game keeps the settings and OPTIONS but no rankings; with no EEPROM it keeps nothing. Not SRAM or FlashRAM |
| boot chip (CIC) | **6102** for an NTSC console (North America, Japan), **7101** for a PAL one. The ROM boots with libdragon's open-source IPL3, which is made for that pair |
| shell | an NTSC shell for an NTSC console, a PAL shell for a PAL console (their tabs differ); any color |
| ROM speed | the header's standard timing: any board made for retail-speed ROMs. The game streams its stages from the ROM continuously, so the flash must keep up at that timing |
| other | no Rumble Pak or Controller Pak support. **The console needs an Expansion Pak (8 MB)**: without one the game stops on an "Expansion Pak required" screen |

When you order, say: *"N64 reproduction cartridge, 512 Mbit flash, EEPROM 16 Kbit save, CIC 6102 (NTSC), North
American gray shell, custom ROM (47 MB .z64) and custom front label (54.5 × 62.5 mm)."* Send the `.z64` and
`label_n64.pdf` with `label_n64_cut.pdf`, or put the label on yourself.

The other way is a **SummerCart64**: open hardware in a standard N64 shell, 64 MB of SDRAM, a 16 Kbit EEPROM emulated,
and the CIC built in. The ROM goes on its SD card, and the label fits its shell.

**No reproduction board has been tried with this ROM yet.** The ROM carries content from your ROM set, so a cartridge
made from it is for your own use.
