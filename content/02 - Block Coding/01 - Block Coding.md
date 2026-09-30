# Block Coding

## Definition
Block coding replaces a group of `m` data bits with a group of `n` coded bits.

Notation:

`mB/nB`

Usually `n > m`, so redundancy is added.

## Purpose
Redundant bits are added to improve:
- Synchronization
- Transmission performance

## 4B/5B
Every 4 data bits are replaced by 5 coded bits.

`4 bits → 5 bits`

The module shows **4B/5B used with NRZ-I**.

## Memory
**Block coding = m bits → n bits + redundancy**
