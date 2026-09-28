# Nyquist Bit Rate

## Noiseless Channel

Nyquist bit rate gives the **theoretical maximum bit rate for a noiseless channel**.

It depends on:

- Bandwidth `B`
- Number of signal levels `L`

> **FORMULA**
>
> `Bit Rate = 2B log2(L)`

where:

- `B` = bandwidth in Hz
- `L` = number of signal levels

## Special Case

If `L = 2`:

`log2(2) = 1`

Therefore:

`Bit Rate = 2B`

## Numerical Example 1

A noiseless channel has:

`B = 3000 Hz`

`L = 2`

Then:

`Bit Rate = 2 × 3000 × log2(2)`

`= 6000 bps`

Therefore:

**Maximum bit rate = 6 kbps**

## Numerical Example 2

Given:

`B = 3000 Hz`

`L = 4`

Since:

`log2(4) = 2`

`Bit Rate = 2 × 3000 × 2`

`= 12,000 bps`

Therefore:

**Maximum bit rate = 12 kbps**

## Important Point

Increasing the number of signal levels can increase the theoretical bit rate, but increasing levels may reduce system reliability.
