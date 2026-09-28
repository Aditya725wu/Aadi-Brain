# Shannon Capacity

## Noisy Channel

Shannon capacity gives the **theoretical maximum data rate for a noisy channel**.

It considers:

- Channel bandwidth
- Signal-to-noise ratio

> **FORMULA**
>
> `C = B log2(1 + SNR)`

where:

- `C` = channel capacity in bps
- `B` = bandwidth in Hz
- `SNR` = signal-to-noise ratio in linear form

## Important

Use **linear SNR**, not SNR in dB, directly in the Shannon formula.

If SNR is given in dB:

> **FORMULA**
>
> `SNR = 10^(SNRdB/10)`

## Numerical Example

Given:

`B = 3000 Hz`

`SNR = 3162`

Then:

`C = 3000 log2(1 + 3162)`

`C = 3000 log2(3163)`

Approximately:

`C ≈ 34.86 kbps`

Therefore, the theoretical channel capacity is approximately **34.86 kbps**.

## Important Interpretation

If SNR approaches zero:

`C = B log2(1 + 0)`

`C = 0`

Therefore, when noise is extremely strong compared with the signal, the theoretical capacity approaches zero.
