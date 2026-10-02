# Mission Reflection

This activity helped me understand why object storage is useful for a photo-sharing application. Millions of photos can be stored as individual objects with keys and metadata, and applications can access them through APIs. Block storage provides disk volumes, but the application team would need to manage a file system and additional infrastructure for sharing and scaling. Object storage separates uploaded photos from temporary application containers.

Docker made deployment more manageable by packaging MinIO and its runtime into a container. However, the original image download failed, and the alternative registry also returned an access error. I continued by building a local Docker image from MinIO source code. This required more preparation than pulling an existing image, but it allowed me to run the server with the required ports and environment variables.

I learned that a bucket is a logical container for objects in an object storage system. I created a bucket named client-photos, kept its access private, and uploaded nginx-running.png. Seeing the file in the Object Browser provided evidence that the upload worked. It also helped me connect the storage concepts with an actual administration task.

Large companies protect stored data through redundancy, such as replication across servers or locations and erasure coding. Backups, versioning, monitoring, and recovery procedures provide additional protection. These features must be configured and tested; simply running an object storage server does not automatically prevent data loss. My temporary deployment used no persistent volume or redundant storage, so it was only a proof of concept.

My confidence with the Linux command line is growing through practice and troubleshooting. I used Docker commands to build an image, launch a container, inspect its status, and read its logs. The errors reminded me to examine actual output before assuming a command succeeded. Documenting the working procedure and screenshots also made my GitHub portfolio more useful and reproducible.
