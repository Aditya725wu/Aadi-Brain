# Circuit Switching and Packet Switching

## Circuit Switching

Circuit switching establishes a **dedicated communication path** between the sender and receiver before communication begins.

The path remains reserved during the communication session.

### Basic idea

`Sender → Dedicated Path → Receiver`

### Main characteristic

Resources are reserved for the connection.

---

# Packet Switching

In packet switching, data is divided into **packets**.

The packets are transmitted through the network.

A dedicated end-to-end path does not have to remain reserved for the entire communication.

### Basic idea

`Data → Packets → Network → Destination`

Different packets may use different routes depending on the network and switching method.

## Comparison

| Feature | Circuit Switching | Packet Switching |
|---|---|---|
| Path | Dedicated path | Shared network |
| Resource reservation | Yes | Generally no dedicated reservation |
| Data | Continuous communication stream | Divided into packets |
| Efficiency for bursty data | Lower | Higher |
| Setup | Requires connection setup | Can transmit packets without dedicated circuit |

## Important Terms

### Packet

A small unit of data transmitted through a packet-switched network.

### Circuit

A dedicated communication path established between communicating endpoints.

## Exam Answer Tip

For a comparison question, write:

**Definition → Working → Comparison table → suitable diagram → conclusion based on the stated requirement.**
