# 🖥️ EC2 Instances

> [!summary] What is an EC2 instance?
> An **EC2 instance** is a virtual server running in AWS that provides computing resources to applications.

**Parent note:** [[01 - EC2 Overview]]

## 1. Main Components

| Component | Purpose |
|---|---|
| CPU | Executes instructions and processes workloads |
| RAM | Holds data temporarily while programs run |
| Storage | Stores the OS, applications, and files |
| Operating System | Provides the environment to run software |
| Network Interface | Connects the instance to a network |

### Common operating systems

- Ubuntu
- Amazon Linux
- Windows Server

The OS image is selected using an [[04 - AMI]] when launching an instance.

## 2. What Can We Run on EC2?

- Host websites — [[12 - Load Balancer]] may be used as traffic grows.
- Deploy backend applications and APIs.
- Run development and testing environments.
- Execute scripts and computing workloads.
- Host application services.

## 3. Practical Example: Hosting a Website

```text
User's browser
      ↓
Internet
      ↓
EC2 public IP / DNS
      ↓
Security Group (HTTP/HTTPS allowed)
      ↓
EC2 instance
      ↓
Web server (Nginx / Apache)
      ↓
Web application
```

Typical setup checklist:

1. Choose a suitable [[04 - AMI]].
2. Select an appropriate [[03_EC2 InstancesType|instance type]].
3. Configure a [[06 - Security Groups|security group]].
4. Ensure networking and a reachable endpoint are configured.
5. Install and configure the web server and application.

## 4. Storage

An instance may use attached [[05 - EBS]] volumes for persistent block storage. Some instance families also offer local instance-store storage, which has different persistence characteristics.

Do not assume local instance-store data will survive an instance stop, termination, or hardware failure; check the instance documentation.

## 5. Connecting to an Instance

For Linux instances, a common method is SSH:

```bash
ssh -i "my-key.pem" ubuntu@YOUR_EC2_PUBLIC_IP
```

The instance must be reachable over the network, its security group must permit the connection, and authentication must succeed.

Related: [[07 - SSH Connection]] · [[08 - Key Pairs]] · [[06 - Security Groups]]

## 6. Quick Revision

**EC2 instance = virtual server + operating system + compute resources + networking.**

The instance provides the environment; your application and its dependencies must be installed and configured separately unless already included in the chosen image.

## 7. Related Notes

- [[01 - EC2 Overview]]
- [[03_EC2 InstancesType]]
- [[04 - AMI]]
- [[05 - EBS]]
- [[06 - Security Groups]]
- [[07 - SSH Connection]]
- [[08 - Key Pairs]]
- [[09 - EC2 Pricing]]
- [[13 - VPC]]
