# Laboratory 05 - The Cloud Data Engineer

## Mission Overview

This activity explores block, file, and object storage and demonstrates deploying an S3-compatible MinIO storage server using Docker. A private bucket was created, and a sample file was uploaded through the web console.

## Objectives

- Compare block, file, and object storage.
- Deploy MinIO using Docker.
- Access the web console through KillerCoda port forwarding.
- Create a private storage bucket.
- Upload and verify an object.
- Document the procedure and screenshot evidence.

## Tools Used

- KillerCoda Ubuntu Playground
- Docker
- Go compiler for building MinIO from source
- MinIO Web Console
- GitHub and Markdown
- Web browser

## Deployment Summary

The Docker Hub and Quay image pulls returned access errors. A local image named lab5-minio:2025-04-22 was built from MinIO source and successfully deployed.

| Setting | Value |
|---|---|
| Container name | minio-server |
| Local image | lab5-minio:2025-04-22 |
| Source release | RELEASE.2025-04-22T22-12-26Z |
| API port | 9000 |
| Web Console port | 9001 |
| Bucket name | client-photos |
| Bucket access | Private |
| Uploaded object | nginx-running.png |

## Skills Learned

- Comparing the purposes of block, file, and object storage.
- Building a Docker image from a Dockerfile.
- Configuring a container using environment variables.
- Publishing separate API and console ports.
- Checking container status and logs.
- Creating a private bucket and uploading an object.
- Recording actual errors and solutions in technical documentation.

## Storage Limitation

This temporary deployment did not use a persistent volume or redundant storage. Data could be lost when the container is removed or the playground environment expires.

## Documentation

- [Storage Types Research](storage-types-research.md)
- [MinIO Deployment](minio-deployment.md)
- [Mission Reflection](reflection.md)

## Screenshot Evidence

### MinIO Deployment

![MinIO deployment](screenshots/minio-deployed.png)

### Bucket and Uploaded Object

![MinIO bucket upload](screenshots/minio-bucket-upload.png)

## AI Assistance Disclosure

ChatGPT assisted with explanations, troubleshooting guidance, and documentation drafts. I executed the deployment commands, created the bucket, uploaded the sample file, and captured the screenshots myself.
