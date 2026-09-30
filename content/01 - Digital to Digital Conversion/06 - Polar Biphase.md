# Polar Biphase

## Definition
Polar biphase schemes use a transition in the middle of every bit.

## Main schemes
- Manchester
- Differential Manchester

## Manchester
A transition always occurs in the middle of the bit. The direction of the middle transition represents the bit.

## Differential Manchester
A transition always occurs in the middle of the bit. The bit value is determined by whether there is a transition at the beginning of the bit.

## Why?
The middle transition provides timing information and helps synchronization.

## Bandwidth
The module states that Manchester and Differential Manchester require approximately **2× the minimum bandwidth of NRZ**.

## Memory
**Biphase → middle transition → synchronization**
