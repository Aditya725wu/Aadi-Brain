# Bipolar Coding

## Definition
Bipolar encoding uses three voltage levels:

`+V, 0V, -V`

## Schemes
- AMI
- Pseudoternary

## AMI — Alternate Mark Inversion

### Rule
- `0 → 0V`
- `1 → alternate +V and -V`

### Example
Data: `1 0 1 1 0 1`

Signal: `+V 0V -V +V 0V -V`

### Memory
**AMI → 1 alternates**

---

## Pseudoternary

### Rule
- `1 → 0V`
- `0 → alternate +V and -V`

### Memory
**Pseudoternary → 0 alternates**

---

## Polar vs Bipolar

| Polar | Bipolar |
|---|---|
| `+V, -V` | `+V, 0V, -V` |
| 2 levels | 3 levels |
| NRZ-L, NRZ-I | AMI, Pseudoternary |
