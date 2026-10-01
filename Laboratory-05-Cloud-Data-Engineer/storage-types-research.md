# Types of Cloud Storage

## Comparison Table

| Storage Type | Description | Primary Use Case | Cloud Provider Example |
|---|---|---|---|
| Block Storage | Stores data in fixed-size blocks that an operating system accesses like a disk. | Database storage and virtual machine disks requiring fast reads and writes. | Amazon Elastic Block Store (EBS) |
| File Storage | Organizes data into files and folders and supports shared file-system access. | Shared directories and applications that need file-system access. | Amazon Elastic File System (EFS) |
| Object Storage | Stores each item as an object containing data and metadata, identified by a key within a bucket. | Large collections of images, videos, backups, and other unstructured data. | Amazon Simple Storage Service (S3) |

## Recommendation for the Client

Object storage is a suitable choice for the client's millions of user-uploaded images because it supports large collections of unstructured data. Applications can upload and retrieve individual photos through APIs while keeping them separate from temporary web server containers. Access controls and lifecycle policies can also help manage and protect the photo collection.

## Reference

Amazon Web Services. (n.d.). *What's the difference between block, object, and file storage?*
https://aws.amazon.com/compare/the-difference-between-block-file-object-storage/
