# Fold-Back 4×4 Stream-Deck Macropad

## Project Overview
A compact **4×4 programmable macropad** (16 MX-style keys) designed for beginners. The case is **3D-printed** with an integrated fold-back kickstand that opens to a ~45° angle for desktop use and folds flat for storage. The board uses a **Seeed XIAO RP2040** running **KMK (CircuitPython)**, sending `Ctrl+Alt+1..16` for soundboard hotkeys.

This project is intended to replicate a Stream Deck experience on a budget. All parts will be assembled, tested, and documented for future Hack Club members.

---

## Features
- 4×4 MX key layout (16 programmable buttons)  
- Fold-back kickstand (living hinge / pin hinge)  
- 3D-printed case (Hackpad-compatible)  
- Uses XIAO RP2040 with KMK firmware  
- Easily expandable for extra layers / hotkeys  
- Compact and portable

---

## Bill of Materials (BOM)

| Qty | Part | Notes / Hack Club Request |
|-----|------|---------------------------|
| 1   | Seeed XIAO RP2040 | Main microcontroller |
| 16  | MX-style mechanical switches | Cherry / Gateron / Kailh compatible |
| 16  | MX keycaps | Clear / translucent or black |
| 16  | Diodes 1N4148 | For matrix wiring |
| 1   | 3D-printed case | Top, bottom, internal spacers, fold-back hinge |
| 4   | M3 screws + nuts | Secure case layers |
| 1   | M2 hinge pin / 1.6 mm rod | For fold-back hinge |
| ~8  | Hook-up wires | Row/column connections |
| 0–1 | 0.96" I2C OLED | Optional, for status display |

---

## Assembly Instructions (Beginner-Friendly)

1. **3D Print the case**: Top plate, bottom, internal spacers, fold-back hinge.  
2. **Insert switches** into the top plate. If needed, secure with a dab of hot glue.  
3. **Wire diodes** for each switch (anode → row, cathode → column).  
4. **Connect row and column wires** to the XIAO RP2040 pins:  
   - Rows: GP0–GP3  
   - Columns: GP4–GP7  
5. **Install KMK firmware** (see `/Firmware/code.py`).  
6. **Test keys** in a key-testing program. Map to EXP Soundboard or other sound apps.  
7. **Assemble case layers** with screws and standoffs.  
8. **Attach fold-back hinge** using M2 pin. Ensure 45° open angle.  
9. **Optional:** Add OLED display and rubber feet.

---

## Wiring / Hand-Wire Schematic

- 4×4 matrix (16 switches) with diodes.  
- Rows → GP0–GP3  
- Columns → GP4–GP7  
- Diode orientation: Anode to row, cathode to column  

*See `/PCB/handwire_schematic.png` for diagram.*

---

## Firmware — KMK (XIAO RP2040)

- File: `/Firmware/code.py`  
- Sends `Ctrl+Alt+1..16` by default  
- Compatible with any standard key mapping for soundboard apps  
- Requires KMK libraries on CIRCUITPY drive

---

## Notes / Hack Club Submission

- Hackpad-approved **3D-printed case only**  
- Design is beginner-friendly and compact  
- All files included for Hack Club review: CAD `.STEP`, hand-wire schematic `.png`, firmware `.py`, BOM  
- Future optional add-ons: OLED, extra keys, custom keycap icons
