# ☁️ EC2 Overview

> **EC2 (Elastic Compute Cloud)** provides resizable virtual servers in the AWS Cloud.

---

## 🖥️ 1. EC2 Instance

An **EC2 Instance** is a **virtual machine (virtual computer)** running inside AWS.

It provides resources such as:

- **CPU** → Processing power
    
- **RAM** → Memory
    
- **Storage** → Disk space
    
- **Operating System** → Ubuntu, Amazon Linux, Windows, etc.
    
- **Networking** → IP addresses and network connectivity
    

### Simple Understanding

Think of an EC2 instance as **renting a computer from AWS**.

```text
Your Computer
├── CPU
├── RAM
├── Storage
└── Operating System

        ↓ Similar concept

EC2 Instance
├── CPU
├── RAM
├── Storage
└── Operating System
```

The difference is that your physical computer is with you, while an EC2 instance runs in an **AWS data center** and can be accessed remotely.

---

## 📍 2. Elastic IP

An **Elastic IP** is a **static public IPv4 address** that can be associated with an EC2 instance.

### Why do we need it?

An EC2 instance's normal public IP can change when the instance is stopped and started.

Example:

```text
Before:
EC2 → 13.201.10.50

Stop → Start

After:
EC2 → 3.110.25.80
```

This can be inconvenient if an application or service depends on the IP address.

With an Elastic IP:

```text
Elastic IP
     ↓
EC2 Instance
     ↓
Application
```

The public IP remains the same while it is associated with the resource.

### Important

- Elastic IP is not automatically assigned.
    
- You allocate an Elastic IP and associate it with an EC2 instance.
    
- An Elastic IP can be reassociated with another EC2 instance when required.
    
- AWS may charge for public IPv4 addresses, including Elastic IP usage, depending on the current pricing rules.
    

---

# 🔐 3. Connecting to an EC2 Instance

One common way to connect to a Linux EC2 instance is **SSH (Secure Shell)**.

SSH allows us to remotely access the terminal of the EC2 instance.

```text
Your Laptop
     │
     │ SSH
     ↓
EC2 Instance
```

After connecting, you can execute commands on the remote machine.

For example:

```bash
ls
cd
mkdir
sudo apt update
python3
npm install
```

---

# 🚪 4. SSH Port 22

SSH normally uses:

```text
Port: 22
Protocol: TCP
```

The EC2 instance is protected by a **Security Group (SG)**.

A Security Group works like a **virtual firewall** that controls network traffic to and from the instance.

Example inbound rule:

```text
Type:       SSH
Protocol:   TCP
Port:       22
Source:     Your IP
```

### ⚠️ Security Note

You don't normally need to allow SSH from the entire internet.

Avoid unnecessarily using:

```text
0.0.0.0/0
```

for SSH because it allows connections from any IPv4 address.

When possible, restrict SSH access to your own IP address:

```text
YOUR_IP/32
```

---

# 🔑 5. `.pem` Key

When creating an EC2 instance, you can create or select an **SSH key pair**.

The private key may be downloaded as a:

```text
.pem
```

file.

Example:

```text
my-key.pem
```

The private key is used to authenticate when connecting to the EC2 instance.

### Example

```bash
ssh -i "my-key.pem" ubuntu@13.201.10.50
```

Here:

```text
ssh
│
├── -i
│    └── Specifies the private key
│
├── my-key.pem
│    └── Private SSH key
│
└── ubuntu@13.201.10.50
     │       │
     │       └── EC2 public IP
     └────────── EC2 username
```

For Ubuntu, the default username is commonly:

```text
ubuntu
```

For Amazon Linux, it is commonly:

```text
ec2-user
```

---

# 🛡️ 6. Security Group

A **Security Group** acts as a virtual firewall for an EC2 instance.

It controls:

- **Inbound traffic** → Traffic coming into the instance
    
- **Outbound traffic** → Traffic going out of the instance
    

Example:

```text
Security Group
│
├── SSH   → TCP 22
├── HTTP  → TCP 80
└── HTTPS → TCP 443
```

For example, if you host a website:

```text
Internet
   │
   ├── Port 80  → HTTP
   │
   └── Port 443 → HTTPS
              ↓
         Security Group
              ↓
          EC2 Instance
```

---

# 🧠 7. Complete EC2 Connection Flow

```text
                    AWS
                     │
             ┌───────▼───────┐
             │  EC2 Instance │
             │               │
             │ CPU           │
             │ RAM           │
             │ Storage       │
             │ OS            │
             └───────┬───────┘
                     │
              Security Group
                     │
                 Port 22
                     │
                  SSH
                     │
                     ▼
                Your Laptop
```

Authentication happens using the SSH private key:

```text
Laptop
  │
  │ SSH + .pem key
  ↓
Security Group
  │
  │ Port 22 allowed
  ↓
EC2 Instance
```

---

# 📌 Quick Revision

|Concept|Meaning|
|---|---|
|**EC2**|AWS service for virtual servers|
|**EC2 Instance**|A virtual machine|
|**Elastic IP**|Static public IPv4 address|
|**Security Group**|Virtual firewall|
|**SSH**|Secure remote connection|
|**Port 22**|Default SSH port|
|**`.pem`**|SSH private key file|
|**Inbound Rule**|Controls incoming traffic|
|**Outbound Rule**|Controls outgoing traffic|

---

# 🔗 Related Topics

- [[2. Instance Types]]
    
- [[3. AMI]]
    
- [[4. EBS]]
    
- [[5. Security Groups]]
    
- [[6. Key Pairs]]
    
- [[7. EC2 Pricing]]
    
- [[8. EC2 User Data]]
    
- [[9. Auto Scaling]]
    
- [[10. Load Balancer]]
    

---

## 💡 One-Line Definition

> **EC2 is an AWS service that lets you create and run virtual computers in the cloud.**