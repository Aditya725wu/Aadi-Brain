# 🖥️ EC2 Instance Types

> [!summary] Purpose
> Choose an EC2 instance family based on CPU, RAM, storage, networking, and workload requirements.

**Parent notes:** [[01 - EC2 Overview]] · [[02 - EC2 Instances]]

## 1. Instance Naming Convention

A simplified pattern is:

```text
family + generation + optional variant + size
```

Examples:

| Instance | Meaning |
|---|---|
| `t3.micro` | T family, generation 3, micro size |
| `m7g.large` | M family, generation 7, Graviton-based variant, large size |
| `c7i.2xlarge` | C family, generation 7, Intel-based variant, 2xlarge size |

### Common size progression

```text
nano → micro → small → medium → large
     → xlarge → 2xlarge → 4xlarge → ...
```

Larger sizes generally provide more resources, but the exact vCPU, memory, storage, and network capacity depends on the family and size.

**Comparison tool:** https://instances.vantage.sh/

## 2. The Big Families: T → M → C → R → I → G/P/HPC

| Family | Mental model | Main purpose |
|---|---|---|
| **T** | Burstable | Low-cost, variable CPU workloads |
| **M** | Main / balanced | General-purpose workloads |
| **C** | Compute | CPU-intensive workloads |
| **R** | RAM | Memory-intensive workloads |
| **I** | I/O | High-performance local storage |
| **G** | Graphics / GPU | Graphics and selected GPU workloads |
| **P** | Powerful GPU | Demanding GPU computing and AI workloads |
| **HPC** | High-performance computing | Scientific and engineering workloads |

This is a practical mnemonic, not a complete list of every EC2 family.

## 3. Practical Family Selection

### T — Burstable General Purpose

**Examples:** `t3.micro`, `t3.small`, `t4g.micro`

- Good for learning, development, testing, and low-traffic applications.
- Uses CPU credits to support bursts of CPU utilization.
- Not the default choice for sustained high CPU usage.

**Example:** A small Flask API for a college project.

### M — General Purpose

**Examples:** `m7i.large`, `m7g.large`

- Balanced CPU, memory, and networking.
- Suitable for web servers, backend applications, and many small-to-medium workloads.

**Example:** A Node.js backend with moderate traffic.

### C — Compute Optimized

**Examples:** `c7i.large`, `c7g.large`

- Designed for high compute performance relative to memory.
- Suitable for batch processing, CPU-heavy services, and scientific computing.

**Example:** CPU-intensive data processing.

### R — Memory Optimized

**Examples:** `r7i.large`, `r7g.large`

- Higher memory capacity relative to vCPU than general-purpose options.
- Suitable for in-memory databases, caching, and memory-intensive analytics.

**Example:** A memory-intensive Redis workload.

### I — Storage Optimized

**Examples:** `i4i.large`, `i4g.large`

- Designed for high-performance local storage and I/O-intensive workloads.
- Useful for search engines and databases that benefit from fast local NVMe storage.
- Check local-storage persistence requirements before selecting an instance.

**Example:** A search index requiring fast local disk access.

### G / P — GPU Accelerated

- **G family:** graphics, visualization, and selected GPU-accelerated workloads.
- **P family:** demanding GPU computing, including AI training workloads.

**Example:** GPU-accelerated machine learning or rendering.

### HPC — High-Performance Computing

- Designed for demanding scientific and engineering workloads.
- Used for computational fluid dynamics, seismic analysis, and weather modeling.
- High-speed networking and parallel computation may be important.

## 4. Quick Decision Table

| Workload | Start by evaluating |
|---|---|
| Learning AWS / small test server | T |
| Website / backend API | T or M |
| CPU-heavy processing | C |
| Large in-memory dataset | R |
| High local disk I/O | I |
| GPU-based AI / rendering | G or P |
| Scientific parallel computing | HPC |

These are starting points. Validate the actual size against workload measurements, compatibility, regional availability, and cost.

## 5. Before Launching

1. **CPU architecture:** Confirm whether your software supports x86-64 (Intel/AMD) or ARM64 (AWS Graviton).
2. **vCPU and RAM:** Estimate what the application requires.
3. **Storage:** Compare [[05 - EBS]] with supported instance-store options.
4. **Networking:** Check bandwidth and network performance needs.
5. **Cost:** Compare On-Demand pricing with relevant [[14 - EC2 Purchasing Options]].
6. **Availability:** Confirm the family and size are offered in your selected AWS Region and Availability Zone.

## 6. Related Notes

- [[01 - EC2 Overview]]
- [[02 - EC2 Instances]]
- [[04 - AMI]]
- [[05 - EBS]]
- [[06 - Security Groups]]
- [[09 - EC2 Pricing]]
- [[11 - Auto Scaling Groups]]
- [[12 - Load Balancer]]
- [[13 - VPC]]
- [[14 - EC2 Purchasing Options]]
