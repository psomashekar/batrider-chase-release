# Batrider: Chase! — the N64 Game Pak

Everything to make a physical copy of the N64 version: the instruction booklet, the cartridge label and the box.
Build the ROM itself with the kit ([`../Batrider_Chase_Kit`](../Batrider_Chase_Kit)) from your own arcade ROMs.

| Folder | Contents |
|---|---|
| [`manual/`](manual) | the instruction booklet, 117 × 173 mm (the size of a Game Pak booklet), in English and Japanese |
| [`manual/print/`](manual/print) | the same booklets imposed two pages to a sheet for a duplex printer, with crop marks |
| [`box-art/`](box-art) | the cartridge label and the box: print files, die lines and previews |

## 1. The cartridge

What the ROM needs from the board:

| | needed | why |
|---|---|---|
| ROM size | **512 Mbit (64 MB)** | the ROM is 49,430,528 bytes (47.1 MB). A 256 Mbit (32 MB) board cannot hold it. |
| Save | **EEPROM 16 Kbit** (2 KB) | the settings, the OPTIONS and each mode's rankings. An EEPROM 4K board keeps the settings and OPTIONS but no rankings. SRAM and FlashRAM boards **do not save**. |
| Lockout chip (CIC) | **6102** (NTSC) or **7101** (PAL), matching your console | the boot code (libdragon's open-source IPL3) is made for the 6102 / 7101 family. A board set up for 6105, 6103 or 6106 games won't boot it. |
| Region | the CIC's only | the ROM is region-free, so only the CIC has to match the console: NTSC for US / Japanese consoles, PAL for PAL ones. On UltraCIC boards that's a jumper or a firmware setting. |
| ROM speed | retail timing | the game streams its stages from the ROM all the time, so the flash must keep up at the header's standard timing. |
| RAM | **Expansion Pak in the console** | without one the game does not start. |
| Extras | none | no Rumble Pak, Controller Pak, RTC or 64DD. |

### What to order

**A blank, reflashable 64 MB repro PCB, flashed by you.** The ROM holds data from your own arcade ROM set and is for
your own use, so don't send it to a shop to flash. Look for:

- **N64 repro PCB, 512 Mbit / 64 MB, reflashable**, with a flash chip that Sanni's open-source Cart Reader can write:
  Fujitsu **MSP55LV512** or **MSP55LV100S**, Spansion **S29GL512**, or Intel **4400L0ZDQ0** (64 MB version), plus the
  Altera MAX II CPLD. The CPLD only maps the upper 32 MB when the board is wired for 64 MB, so a "32/64 MB" board has
  to be set up as 64 MB.
- **EEPROM 16K** save (the 16K EEPROM chip fitted, not SRAM or FlashRAM).
- **CIC 6102 / 7101**, or an **UltraCIC**-type chip set to your region.
- A **cart reader / flasher** that writes repros: Sanni's Cart Reader (see "Reflashing N64 Repros" in its wiki), or a
  pre-built one.
- An **N64 replacement shell** (NTSC/PAL style, not the Japanese one, so the label recess fits) and a **3.8 mm
  gamebit** driver. A gray, smoke-black or translucent-blue shell suits the art.

**The plug-and-play alternative:** an open-hardware **SummerCart64** (or a PicoCart64) in a standard shell. It takes
ROMs up to 64 MB, emulates EEPROM 16K and the CIC, and loads from an SD card. It isn't a single-game cart, but it needs
no flashing hardware, and the label fits it too. (SummerCart64's own tool can set it to boot a ROM directly; see its
documentation.)

No repro board has been tried with this ROM yet. After flashing, check it on the console: the WARNING screen, then the
studio's logo, then a save. Change a setting, switch off, and check that it's kept.

## 2. The cartridge label

<img src="box-art/preview_label.png" width="260" alt="Label preview" align="right">

| file (in `box-art/`) | use |
|---|---|
| `batrider_chase_n64_label.pdf` | for a print shop: art only, 54.5 × 62.5 mm trim + **2 mm bleed** |
| `batrider_chase_n64_label_cut.pdf` / `_cut.svg` | the die-cut contour alone (magenta), on the same page size |
| `batrider_chase_n64_label_proof.pdf` | the art with the cut line and the 2 mm safe area (cyan dashes), for checking |
| `batrider_chase_n64_label_600dpi.png` | the art at 600 dpi with its bleed, for sticker shops that take PNG |
| `batrider_chase_n64_label_sheet_letter.pdf` / `_a4.pdf` | eight labels with gray cut lines, for sticker paper at home |

- **Shape:** the US / PAL N64 front label is **54.5 mm wide × 62.5 mm tall**. Its top edge is an arc of 325 mm
  diameter (2.3 mm higher in the middle than at the corners), with **4 mm** radius top corners and **3 mm** bottom
  corners. Reproduction shells vary by a millimeter or so: measure the recess on yours.
- **Stock:** gloss or semi-gloss white vinyl (or paper) sticker with permanent adhesive, laminated if you can. Order it
  **die-cut to the contour**.
- **At home:** print the sheet at **100 % / Actual size** on full-sheet sticker paper, then cut on the gray lines. A
  3–4 mm corner punch helps with the corners.

## 3. The box

<p align="center"><img src="../images/preview_box_front.png" width="520" alt="Box front preview"></p>

| file (in `box-art/`) | use |
|---|---|
| `batrider_chase_n64_box.pdf` | the flat sheet, art only: **268 × 329 mm trim, 274 × 335 mm with the 3 mm bleed** |
| `batrider_chase_n64_box_dieline.pdf` / `.svg` | the dieline alone (cut = magenta solid, fold = blue dashed), for the die maker or a cutting plotter |
| `batrider_chase_n64_box_proof.pdf` | the art with the dieline on top and the panels named, as a proof |
| `batrider_chase_n64_box_a3.pdf` / `_12x18.pdf` | the proof on one A3 / 12 × 18 in sheet with crop marks, for printing at home or a copy shop and cutting by hand |
| `panels/box_*.png` | each face alone at 600 dpi with 3 mm bleed (front, back, both spines, both ends), for a shop that has its own N64 template |
| `preview_*.png` | previews only, not for print |

- **Size:** the NTSC-U N64 box, a landscape carton **180 × 127 × 31 mm** that opens at the two short ends. The style
  is **reverse tuck end**: a tuck flap on each end, dust flaps on the spines, and a glue flap under the front's lower
  edge.
- **Stock:** 350–400 gsm (16–18 pt) **SBS / C1S** paperboard, printed CMYK on the white side, **gloss or matte
  lamination** outside. Score the folds before folding them.
- **Inside:** retail N64 boxes have a cardboard tray that holds the cartridge and booklet. Reproduction **N64 cardboard
  inserts** are sold ready-made and fit this box size.
- **Before a big run:** these sizes come from collectors' measurements of retail boxes. Order one proof, or ask the
  shop to check them against their own N64 template. If they have one, send them `panels/` instead of the flat sheet.

The artwork is RGB, so the shop converts it to CMYK and the deep blues may come out a little duller. The box's front
art is enlarged from about 150 dpi, so it looks a little soft up close. Ask for a printed proof if the color matters.

The back of the box says it is unofficial and non-commercial, not licensed or endorsed by the owners of the game or of
the system. Some print shops ask for that line when a box carries another company's marks, so keep it.

## 4. The instruction booklet

| file (in `manual/`) | use |
|---|---|
| `batrider_chase_manual_n64.pdf` | English, page by page at 117 × 173 mm, for a print shop or for reading |
| `batrider_chase_manual_n64_ja.pdf` | Japanese, the same |
| `print/batrider_chase_manual_n64_letter.pdf` | English, imposed on US Letter for printing at home |
| `print/batrider_chase_manual_n64_ja_a4.pdf` | Japanese, imposed on A4 for printing at home |

**At home:** print the `print/` file duplex, **flip on the short edge**, at **100 % / Actual size**. Cut at the crop
marks, fold, and staple at the spine.
