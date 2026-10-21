
# Amazon EBS (Elastic Block Store)

## 1. What is EBS?

**Amazon EBS** provides block storage volumes that you can attach to EC2 instances.

Think of EBS as an external hard disk for your cloud server.

**Example:** Your EC2 instance runs Ubuntu, while an EBS volume stores application files, databases, and other persistent data.

Related: [[02 - EC2 Instances]] · [[04 - AMI]]
![[Pasted image 20261022001444.png|540]]
## 2. How EBS Works

```
EC2 Instance
     |
     | Attach volume
     v
EBS Volume
     |
     v
Operating System sees a disk
     |
     v
Format → Mount → Store data
```

- An EBS volume is created in a specific Availability Zone.
    
- It can be attached to compatible EC2 instances in the same Availability Zone.
    
- You can format and mount it to store files.
    
- EBS data generally persists independently of the running life of the instance, depending on the volume and deletion settings.
    

## 3. EBS vs Instance Store vs S3

|Feature|EBS|Instance Store|S3|
|---|---|---|---|
|Storage type|Block|Local block|Object|
|Main use|OS, databases, files|Temporary high-speed data|Files, backups, assets|
|Persistence|Designed to persist independently of the instance|Tied to instance lifecycle; data may be lost|Persistent object storage|
|Access|Attached to EC2|Local to supported instance|API / SDK / CLI|

**Remember:** EBS is like a disk, while S3 stores objects.

Related: [[01 - EC2 Overview]] · [[01 - S3 Overview]]

## 4. EBS Volume Types

|Type|Typical use|
|---|---|
|`gp3`|General-purpose SSD; common default choice|
|`gp2`|Earlier general-purpose SSD|
|`io2`|High-performance, provisioned-IOPS SSD|
|`st1`|Throughput-intensive HDD workloads|
|`sc1`|Infrequently accessed HDD workloads|

Choose based on performance, IOPS, throughput, capacity, and cost. HDD types are not suitable as boot volumes.

## 5. Practical: Create and Attach an EBS Volume

1. Open **AWS Console → EC2 → Volumes**.
    
2. Choose **Create volume**.
    
3. Select the volume type and size.
    
4. Select the same Availability Zone as your EC2 instance.
    
5. Create the volume.
    
6. Select it and choose **Actions → Attach volume**.
    
7. Select your EC2 instance.
    

The volume is attached, but a new volume may still need partitioning, formatting, and mounting before use.

## 6. Linux Commands to Prepare a New Volume

First, identify the correct device:

```
lsblk
```

For a new, empty data volume, after verifying the correct device, create a filesystem. The example below assumes the device is `/dev/nvme1n1` and is safe to format.

```
sudo mkfs -t xfs /dev/nvme1n1
```

Create a mount directory and mount it:

```
sudo mkdir -p /data
sudo mount /dev/nvme1n1 /data
```

Verify:

```
df -h
lsblk
```

> [!warning]  
> Formatting the wrong device can destroy data. Device names vary, and formatting is only appropriate for a new or intentionally erased volume. Do not format your root disk.

For persistence across reboots, configure `/etc/fstab` using the volume's UUID and test the configuration before rebooting.

## 7. Snapshots

An **EBS snapshot** is a point-in-time backup of an EBS volume stored by AWS.

Common uses:

- Back up important data.
    
- Restore a volume after data loss.
    
- Create another volume from a snapshot.
    
- Support recovery and migration workflows.
    

Snapshots can incur storage charges.

Related: [[04 - AMI]]

## 8. Important Points

- EBS volumes exist in a specific Availability Zone.
    
- Resizing a volume may also require extending the partition and filesystem.
    
- The volume's deletion-on-termination setting determines whether it is deleted when the instance terminates.
    
- Encryption helps protect data at rest.
    
- Detaching a volume does not normally delete its data.
    

## 9. Quick Revision

- **EBS:** Persistent block storage for EC2.
    
- **Volume:** Virtual disk attached to an instance.
    
- **Snapshot:** Point-in-time backup.
    
- **Mount:** Makes a filesystem accessible at a directory.
    
- **gp3:** Common general-purpose SSD choice.
    

## Related Notes

- [[01 - EC2 Overview]]
    
- [[02 - EC2 Instances]]
    
- [[03_EC2 InstancesType]]
    
- [[04 - AMI]]
    
- [[06 - Security Groups]]
    
- [[09 - EC2 Pricing]]
    
- [[01 - S3 Overview]]