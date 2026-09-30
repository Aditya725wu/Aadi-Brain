# Synchronization

## 1. Definition

**Synchronization** is the process of keeping the **sender's and receiver's timing matched** so that the receiver can correctly identify the beginning and end of each bit.

In digital communication, the sender transmits bits one after another:

```
1     0     1     1     0
|-----|-----|-----|-----|-----|
```

The receiver must know exactly where each bit interval starts and ends.

If the receiver's timing becomes different from the sender's timing, the receiver may read the signal at the wrong instant and interpret the data incorrectly.

---

## 2. Why Synchronization is Needed

A digital signal is transmitted continuously over time, but the receiver needs to divide it into individual **bit intervals**.

For example:

```
Data:      1    0    1    1    0
          |----|----|----|----|----|
           Bit  Bit  Bit  Bit  Bit
```

The receiver needs to know:

- When a bit starts
- When a bit ends
- When the next bit should be read

Therefore, the **sender and receiver clocks must remain synchronized**.

### Simple idea

> **Correct timing → correct bit detection**

> **Incorrect timing → possible incorrect bit detection**

---

# 3. Clock Synchronization

The sender and receiver normally have their own clocks.

Ideally:

```
Sender clock:   |---|---|---|---|---|
Receiver clock: |---|---|---|---|---|
```

Their timing should match.

But in reality, the receiver's clock can be slightly **faster or slower**.

For example:

```
Sender:    |----|----|----|----|----|
Receiver:  |---|---|---|---|---|
```

Initially, the difference may be very small.

But over time, the difference can accumulate.

This is called **clock drift** or timing mismatch.

---

# 4. Effect of Lack of Synchronization

Suppose the sender sends:

```
1 0 1 1 0
```

The sender divides the signal into:

```
| 1 | 0 | 1 | 1 | 0 |
```

If the receiver's clock is slightly faster, its bit boundaries gradually move relative to the sender's:

```
Sender:
|  1  |  0  |  1  |  1  |  0  |

Receiver:
| 1 | 0 | 1 | 1 | 0 | ...
```

Eventually, the receiver may sample the signal at incorrect positions.

### Result

```
Clock mismatch
      ↓
Bit boundaries become misaligned
      ↓
Receiver samples incorrectly
      ↓
Wrong data may be detected
```

---

# 5. Clock Mismatch Example

Your module gives an example where the **receiver clock is 0.1% faster** than the sender.

### Case 1: 1 kbps

Sender:

1 kbps=1000 bps1\text{ kbps}=1000\text{ bps}

Receiver is 0.1% faster:

1000×0.1100=11000\times\frac{0.1}{100}=1

So the receiver effectively sees:

1000+1=1001 bps1000+1=\boxed{1001\text{ bps}}

### Case 2: 1 Mbps

Sender:

1 Mbps=1,000,000 bps1\text{ Mbps}=1,000,000\text{ bps}

Difference:

1,000,000×0.1100=10001,000,000\times\frac{0.1}{100}=1000

Therefore:

1,000,000+1000=1,001,000 bps1,000,000+1000 = \boxed{1,001,000\text{ bps}}

### Important observation

A very small **0.1% clock difference** becomes a larger absolute difference when the data rate is high.

---

# 6. Receiver Faster vs Slower

### Receiver is faster

Add the difference:

Rr=Rs+difference\boxed{R_r=R_s+\text{difference}}

Example:

```
Sender = 1 Mbps
Receiver = 0.1% faster

Receiver = 1.001 Mbps
```

### Receiver is slower

Subtract the difference:

Rr=Rs−difference\boxed{R_r=R_s-\text{difference}}

Example:

```
Sender = 1 Mbps
Receiver = 0.1% slower

Difference = 1000 bps

Receiver = 999,000 bps
```

---

# 7. Self-Synchronization

A **self-synchronizing digital signal** contains timing information within the signal itself.

The receiver can use **transitions in the signal** as timing clues.

For example:

```
Signal:

──────┐      ┌──────
      └──────┘
         ↑
     transition
```

The transition gives the receiver information about the timing of the transmitted bits.

So:

```
Signal transition
       ↓
Timing information
       ↓
Receiver maintains timing
       ↓
Synchronization
```

---

# 8. Why Transitions Are Important

Consider a long sequence of identical bits:

```
0 0 0 0 0 0 0 0
```

The signal may remain at the same level for a long time:

```
────────────────────────
```

There are very few/no transitions to provide timing information.

This makes synchronization more difficult.

A coding scheme that provides regular transitions can make synchronization easier.

For example, **Manchester encoding** uses a transition in the middle of every bit specifically to provide synchronization information. Your module discusses this later under polar biphase encoding.

---

# 9. Synchronization and Line Coding

Synchronization is closely connected with **line coding**.

Different line coding schemes produce different numbers and patterns of signal transitions.

Therefore, the choice of line coding affects how easily the receiver can maintain synchronization.

For example:

```
Line coding
     ↓
Signal transitions
     ↓
Timing information
     ↓
Synchronization
```