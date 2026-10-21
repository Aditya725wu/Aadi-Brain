# ☁️ EC2 Overview

> [!summary] What is EC2?
> **Amazon EC2 (Elastic Compute Cloud)** lets you create and run resizable virtual servers in AWS.

## 1. EC2 Instance

An **EC2 instance** is a virtual machine running in an AWS data center. It provides CPU, RAM, storage, an operating system, and network connectivity.

Think of it as **renting a computer from AWS** and accessing it remotely.

Related: [[02 - EC2 Instances]] · [[03_EC2 InstancesType]]

## 2. Elastic IP

An **Elastic IP (EIP)** is an allocated static public IPv4 address that can be associated with an AWS resource.

- A normal auto-assigned public IPv4 address can change after an instance is stopped and started.
- An Elastic IP provides a stable address while it remains allocated.
- You can reassociate it with another supported resource when required.
- Check current AWS public IPv4 pricing before allocating one.

## 3. Connecting to EC2 with SSH

**SSH (Secure Shell)** allows secure remote terminal access to a Linux instance.

```text
Your laptop → Network route → Security Group → EC2 instance → SSH terminal
```

Related: [[07 - SSH Connection]] · [[06 - Security Groups]] · [[08 - Key Pairs]]

## 4. SSH Port 22

SSH normally uses **TCP port 22**.

Example inbound rule:

| Setting | Example |
|---|---|
| Type | SSH |
| Protocol | TCP |
| Port | 22 |
| Source | Your public IP `/32` |

Avoid exposing SSH to `0.0.0.0/0` unless there is a specific, justified reason. Consider AWS Systems Manager Session Manager where appropriate.

## 5. Key Pair and `.pem`

An SSH key pair contains a public key and a private key. A downloaded `.pem` file commonly contains the private key.

Keep the private key secure and never share it.

Example:

```bash
ssh -i "my-key.pem" ubuntu@YOUR_EC2_PUBLIC_IP
```

The default username is commonly `ubuntu` for Ubuntu AMIs and `ec2-user` for Amazon Linux.

Related: [[08 - Key Pairs]] · [[07 - SSH Connection]]

## 6. Security Groups

A **Security Group** is a stateful virtual firewall associated with an EC2 network interface.

- **Inbound rules:** control incoming connections.
- **Outbound rules:** control outgoing connections.
- Return traffic for an allowed connection is automatically permitted.

Common ports:

| Purpose | Protocol | Port |
|---|---|---:|
| SSH | TCP | 22 |
| HTTP | TCP | 80 |
| HTTPS | TCP | 443 |

Open only the ports your workload needs.

Related: [[06 - Security Groups]]

## 7. Website Hosting Flow

```text
User's browser
      ↓
Internet
      ↓
Public IP / DNS
      ↓
Security Group (HTTP/HTTPS allowed)
      ↓
EC2 instance
      ↓
Web server (Nginx / Apache)
      ↓
Application
```

The web server and application must be installed and configured unless the selected image or setup already includes them.

## 8. Quick Revision

| Concept | Meaning |
|---|---|
| EC2 | AWS virtual server service |
| Instance | A virtual machine |
| Elastic IP | Allocated static public IPv4 address |
| Security Group | Stateful virtual firewall |
| SSH | Secure remote terminal access |
| Port 22 | Default SSH port |
| `.pem` | Common private-key file format |
| Inbound rule | Controls incoming connections |
| Outbound rule | Controls outgoing connections |

## 9. Related Notes

- [[02 - EC2 Instances]]
- [[03_EC2 InstancesType]]
- [[04 - AMI]]
- [[05 - EBS]]
- [[06 - Security Groups]]
- [[07 - SSH Connection]]
- [[08 - Key Pairs]]
- [[09 - EC2 Pricing]]
- [[10 - EC2 User Data]]
- [[11 - Auto Scaling Groups]]
- [[12 - Load Balancer]]
- [[13 - VPC]]

> **One-line definition:** EC2 is an AWS service for creating and running virtual computers in the cloud.
