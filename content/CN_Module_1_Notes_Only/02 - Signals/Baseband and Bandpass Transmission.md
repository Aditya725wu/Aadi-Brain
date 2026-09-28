# Baseband and Bandpass Transmission

## Baseband Transmission

Baseband transmission sends the digital signal directly through the transmission channel.

It requires a **low-pass channel**.

To preserve the shape of a digital signal, the channel must have an infinite or very wide bandwidth.

### Basic idea

`Digital Signal → Low-pass Channel → Receiver`

## Bandpass Transmission

A bandpass channel has a frequency range between a lower and upper cutoff frequency.

A digital signal cannot be sent directly through a bandpass channel.

It must first be converted into an **analog signal** before transmission.

### Basic idea

`Digital Data → Analog Conversion → Bandpass Channel → Receiver`

## Comparison

| Baseband | Bandpass |
|---|---|
| Direct digital signal transmission | Digital signal is converted to analog |
| Uses low-pass channel | Uses bandpass channel |
| Preserves digital shape with suitable bandwidth | Uses a selected frequency band |
