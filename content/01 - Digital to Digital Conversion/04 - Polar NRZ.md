# Polar NRZ

Polar encoding uses positive and negative voltage levels.

## NRZ-L

### Rule
The **level** determines the bit.

For the module convention:
- `0 → +V`
- `1 → -V`

### Example
`1 0 1 1 0 → -V +V -V -V +V`

### Memory
**NRZ-L → Level**

---

## NRZ-I

### Rule
The **inversion/change** determines the bit.

For the module convention:
- `1 → change`
- `0 → no change`

### Example
Start at `+V`.

Data: `1 0 1 1 0`

Levels: `-V -V +V -V -V`

### Memory
**NRZ-I → Inversion**

---

## Numerical

For NRZ-L/NRZ-I:

`S = N/2`

For the bandwidth relation used in the module:

`Bmin = S`

Example: `N = 10 Mbps`

`S = 5 Mbaud`

`Bmin = 5 MHz`

**Note:** the slide's printed 500 kbaud/500 kHz for 10 Mbps is inconsistent with the stated data rate; direct calculation gives 5 Mbaud/5 MHz.
