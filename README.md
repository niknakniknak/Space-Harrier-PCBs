# Space Harrier — PCB photographs

High-resolution photographs of a **working** Sega Space Harrier four-board stack.
Both sides of every board.

Shot on a Panasonic DC-S9 at roughly 11000 x 7500 px. Photographed and released by
Chris Watson, 2026.

These were taken to support an FPGA implementation of the hardware, so the emphasis
is on legibility: part numbers, custom-chip markings and trace routing rather than
presentation. Every part number below was read directly off the silkscreen or the
device label, and the ROM labels were cross-checked against MAME's `segahang.cpp`.

**These are photographs of a machine known to work.** That matters if you are using
them to diagnose a faulty board: differences you find are differences, not both of
us being wrong.

---

## The boards — set `sharrier`, the i8751 MCU version

| Board | Function | Bare PCB | Top | Solder |
|---|---|---|---|---|
| 834-5797 | CPU: 68000 main (unencrypted) + 68000 sub + i8751 MCU, 2x D8255, ADC0804 with HEF4051 analog mux, 2x ULN2003 cabinet drivers | 171-5318 | PLS91046 | PLS91052 |
| 834-5798 | Video: sprite, road and tilemap. 315-5011, 315-5012, 2x 315-5049, 6x 315-5025, PALs 315-5106/07/08/68/69/70/71/72, Sony CXK5808 SRAM, 25.1748 MHz | 171-5320 | PLS91048 | PLS91050 |
| 834-5799 | Sound: Z80 (D780C) + YM2203C, 2x M8544 filters, EPR-7231..7234, PAL 315-5103, 16 MHz | 171-5268 | PLS91034 | PLS91039 |
| 834-5800 | ROM / sprite data: 27256 array EPR-7199..7230, HC244 buffers | 171-5321 | PLS91036 | PLS91044 |

ROMs confirmed: `epr-7181.ic2`, `epr-7182.ic54`, `dpr-7184a.ic84`, `dpr-7188a.ic97`
(CPU); `epr-7196.ic31` (video); `epr-7199.ic1`..`epr-7230.ic36` (sprite data);
`epr-7231.ic5` (sound). All match MAME `sharrier`.

**Note on the MCU:** the socket at IC32 holds a **P87C51SBPN "CR8208"** — a
reprogrammed OTP 87C51 substitute, not the original Intel i8751H labelled
315-5163A. Functionally equivalent, but worth knowing if MCU behaviour is ever in
question.

## The undumped PALs

The video board carries PALs 315-5106, 315-5107 and 315-5108 (video timing) and
315-5168 (the VRAM slot arbiter that stalls the CPU off video RAM). None has been
dumped. Their pin lists can be read from the schematics, but their contents cannot,
and anyone implementing this hardware ends up deriving behaviour around them. If
these photographs help someone get further with that, they have paid for themselves.

## Enduro Racer

Enduro Racer's CPU and video boards were photographed at the same time and will be
published separately. The two games share the same bare PCBs — note 171-5320 above,
which is also Enduro's video board — so each is a useful reference for the other.
`EPR-6844` (IC123) appears on both video boards; it is common to the whole Hang-On
family.

## Licence

Creative Commons Attribution 4.0 (CC BY 4.0). Use them for anything, including
commercially. Attribution is required, and the credit should read:

    Photo by Chris Watson, CC BY 4.0

Please use the name rather than the handle. Preservation is the point -- if they
are useful, take them.
