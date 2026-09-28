# Signal-to-Noise Ratio (SNR)

## Definition

SNR is used to measure the quality of a communication system.

It indicates the strength of the signal with respect to the noise power.

It is the ratio between **signal power and noise power**.

> **FORMULA**
>
> `SNR = P_signal / P_noise`

SNR is usually expressed in decibels.

> **FORMULA**
>
> `SNR_dB = 10 log10(SNR)`

## Interpretation

### High SNR

Signal power is much greater than noise power.

→ Better signal quality.

### Low SNR

Noise power is relatively large.

→ Poorer signal quality.

## Numerical Example

Given:

`Signal power = 10 mW`

`Noise power = 1 μW`

Convert:

`10 mW = 10,000 μW`

Therefore:

`SNR = 10,000 / 1`

`SNR = 10,000`

Now:

`SNR_dB = 10 log10(10,000)`

`SNR_dB = 40 dB`

Therefore:

**SNR = 10,000**

**SNRdB = 40 dB**

## Important Point

For an ideal noiseless channel, noise power approaches zero and the SNR approaches an extremely large value. A truly noiseless physical channel is an idealization.
