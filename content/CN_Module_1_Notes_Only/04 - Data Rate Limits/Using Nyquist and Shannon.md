# Using Nyquist and Shannon Together

Nyquist and Shannon answer different questions.

## Nyquist

Nyquist considers a **noiseless channel** and tells us the maximum bit rate for a given bandwidth and number of signal levels.

> **FORMULA**
>
> `Bit Rate = 2B log2(L)`

## Shannon

Shannon considers a **noisy channel** and gives the theoretical upper limit imposed by bandwidth and SNR.

> **FORMULA**
>
> `C = B log2(1 + SNR)`

## How They Work Together

For a practical noisy channel:

### Step 1 — Shannon

Calculate the maximum theoretical capacity.

This gives the **upper limit**.

### Step 2 — Select a practical bit rate

Choose a bit rate at or below the Shannon upper limit.

### Step 3 — Nyquist

Use Nyquist to determine the number of signal levels required for that chosen bit rate.

From:

`R = 2B log2(L)`

we can derive:

> **FORMULA**
>
> `L = 2^(R/(2B))`

## Example

Given:

`B = 1 MHz`

`SNR = 63`

First use Shannon:

`C = 1,000,000 log2(1 + 63)`

`C = 1,000,000 log2(64)`

`C = 6 Mbps`

So Shannon gives an upper limit of **6 Mbps**.

Suppose a practical bit rate of **4 Mbps** is selected.

Now use Nyquist:

`4,000,000 = 2 × 1,000,000 × log2(L)`

`2 = log2(L)`

Therefore:

`L = 4`

So **4 signal levels** are required.

## Key Point

> **Shannon → tells the upper limit.**

> **Nyquist → tells the required signal levels for a selected bit rate.**
