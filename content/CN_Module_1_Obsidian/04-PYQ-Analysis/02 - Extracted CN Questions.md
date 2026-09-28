# Extracted CN Questions from Provided Papers

## 2025 CN MSE --- 05/10/2025 --- 7IT202

### Q1

**A)** Consider IP address `192.168.10.17/28`: 1. What is the subnet
mask? 2. What is the sub-network address? 3. What is range of IP
addresses in any 4 subnet? 4. How many usable hosts are available in
this subnet?

**B)** Sliding Window Protocol with Go-Back-N: - Link capacity = 1
Mbps - Propagation delay = 1.25 sec - Frame size = 1 KB - Calculate
sequence number required to complete transmission.

**C)** Given routing-table entry: - Destination: `192.168.2.0` - Subnet
Mask: `255.255.255.0` - Next Hop: `10.0.0.1` - Interface: `eth0` -
Metric: 1

Questions ask the meaning of destination, significance of next hop, and
interface used for packets destined for `192.168.2.0`.

**D)** Draw IP header and explain each field in IPv4.

### Q2

**A)** Define: - Static Routing - Propagation Delay - Round Trip Time

**B)** Calculate token-ring cycle time using: - Data rate = 4 Mbps -
Number of stations = 20 - Station separation = 100 m - Bit delay at each
station = 2.5 bits - Token reinsertion packet = 1000 bits - Transmission
speed = (2`\times10`{=tex}\^8) m/s - Token size = 24 bits

------------------------------------------------------------------------

## 2026 CN MSE --- 04/09/2026 --- 7CS204

### Q1 A --- OSI

A student opens a web page from a remote server. Explain with a suitable
example how data is encapsulated while moving down the OSI layers at the
sender and decapsulated while moving up the layers at the receiver.
State the role of Network and Transport layers.

### Q1 B --- OSI vs TCP/IP

Compare the OSI reference model and TCP/IP protocol suite with respect
to layer structure, functions and practical use. Show mapping between
corresponding layers.

### Q1 C --- Transmission impairment

A digital signal travelling through a communication link becomes weaker,
its waveform changes, and unwanted electrical disturbances are observed
at the receiver. Identify the three types of transmission impairments
and explain each briefly.

### Q2 A --- Line coding

For binary sequence `110010`, draw waveforms using: 1. Unipolar NRZ 2.
Polar NRZ 3. Bipolar AMI 4. Manchester encoding

Clearly mark bit boundaries and transitions.

### Q2 B --- Multiplexing

Explain and compare: - FDM - TDM - WDM

Include basic working principle and one suitable application or
advantage of each.

### Q3 A --- ARQ

Host A sends 10 frames to Host B using Go-Back-4 ARQ. Sequence of frame
transmissions including retransmissions is required if every 6th frame
transmitted by A is corrupted or lost. Compare retransmissions with
Selective Repeat ARQ.

### Q3 A (OR) --- Byte stuffing

Emergency response system: - FLAG = `7E` - ESC = `7D` - Actual data
contains `7E` or `7D`

Data: `45 7E 23 7D 91 7E 56`

Tasks: 1. Design suitable framing using byte stuffing. 2. Show original
data. 3. Show stuffed data. 4. Draw complete transmitted frame.

### Q3 B --- CSMA

Compare CSMA/CD and CSMA/CA and justify why CSMA/CA is more suitable for
WLAN than CSMA/CD.

### Q3 C --- Ethernet

Draw Ethernet frame format, show field sizes, and briefly explain the
function of each field.
