# Amazon S3

## 1. What is S3?

Amazon S3 (Simple Storage Service) is AWS object storage used to store files such as images, videos, documents, backups, and logs.

**Example:** Store website images in S3 instead of keeping them on your [[02 - EC2 Instances|EC2 instance]].

## 2. Key Concepts

- **Bucket:** Container for objects.
    
- **Object:** Stored file and its metadata.
    
- **Object Key:** Object's name/path inside a bucket.
    
- **Region:** AWS location where the bucket is created.
    

```
my-bucket/
├── images/photo.jpg
├── documents/resume.pdf
└── backups/database.zip
```

S3 uses object keys and prefixes; folder-like paths are not traditional directories.

## 3. Create a Bucket and Upload a File

1. AWS Console → S3 → Create bucket.
    
2. Enter a globally unique bucket name and select a Region.
    
3. Keep Block Public Access enabled by default.
    
4. Create the bucket.
    
5. Open it → Upload → Add files → Upload.
    

A file's URL does not automatically make it publicly accessible.

## 4. How S3 Works

```
Application
    |
    | Upload (PUT)
    v
S3 Bucket → Object stored
    |
    | Download (GET)
    v
Application
```

Common uses:

- Website images and static files.
    
- Application uploads.
    
- Backups and logs.
    
- Analytics datasets and archives.
    
![[Pasted image 20261022000606.png|558]]
## 5. Storage Classes

|Class|Use|
|---|---|
|S3 Standard|Frequently accessed files|
|S3 Intelligent-Tiering|Changing or unknown access patterns|
|S3 Standard-IA|Infrequent access, rapid retrieval|
|S3 One Zone-IA|Infrequent access; single-AZ storage|
|S3 Glacier Instant Retrieval|Archive with immediate retrieval|
|S3 Glacier Flexible Retrieval|Archive with delayed retrieval options|
|S3 Glacier Deep Archive|Long-term, rarely accessed archives|

Storage class affects cost, retrieval time, and retrieval charges.

## 6. Security

- **IAM policies:** Control user and role permissions.
    
- **Bucket policies:** Control bucket access.
    
- **Block Public Access:** Helps prevent accidental public exposure.
    
- **Encryption:** Protects stored data.
    
- **Versioning:** Preserves multiple object versions.
    
- **IAM role for EC2:** Lets applications access S3 without hardcoding access keys.
    

Related: [[02 - EC2 Instances]]

## 7. AWS CLI Commands

List buckets:

```
aws s3 ls
```

Upload a file:

```
aws s3 cp ./photo.jpg s3://YOUR-BUCKET/images/photo.jpg
```

List bucket objects:

```
aws s3 ls s3://YOUR-BUCKET/
```

Download a file:

```
aws s3 cp s3://YOUR-BUCKET/images/photo.jpg ./photo.jpg
```

Configure the AWS CLI and appropriate permissions before running these commands.

## 8. Pricing

S3 costs can include:

- Data storage.
    
- Requests.
    
- Data retrieval.
    
- Data transfer.
    
- Optional features such as replication.
    

Check current AWS pricing before deployment.

Related: [[09 - EC2 Pricing]]

## Quick Revision

- S3 = object storage.
    
- Bucket = container.
    
- Object = stored file.
    
- Key = object identifier.
    
- Storage classes = different cost and retrieval options.
    
- Permissions control who can access objects.
    

**Remember:** [[02 - EC2 Instances|EC2]] runs applications; S3 stores files.

## Related Notes

- [[01 - EC2 Overview]]
    
- [[02 - EC2 Instances]]
    
- [[03_EC2 InstancesType]]
    
- [[04 - AMI]]
    
- [[05 - EBS]]
    
- [[06 - Security Groups]]
    
- [[09 - EC2 Pricing]]