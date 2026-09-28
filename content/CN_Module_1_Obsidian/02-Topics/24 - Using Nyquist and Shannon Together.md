# Using Nyquist and Shannon Together

## Core idea

### Shannon

Gives the **upper limit** imposed by noise and bandwidth:

\[ C=B`\log`{=tex}\_2(1+SNR) \]

### Nyquist

Can then be used to determine the signal levels required for a chosen
practical bit rate:

\[ Bit Rate=2B`\log`{=tex}\_2L \]

The PPT states: \> Shannon capacity gives the upper limit; Nyquist tells
us how many signal levels we need.

## Typical problem

Given: - bandwidth, - SNR, - desired practical bit rate,

do:

1.  Shannon → calculate maximum theoretical capacity.
2.  Choose a practical rate below that upper limit.
3.  Nyquist → solve for (L).

## Sample

**Q. A channel has bandwidth 1 MHz and SNR 63. Find the Shannon upper
limit and determine suitable signal levels for a chosen practical rate
of 4 Mbps.**
