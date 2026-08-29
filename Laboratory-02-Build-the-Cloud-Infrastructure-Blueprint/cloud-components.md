# Cloud Infrastructure Components

Cloud infrastructure consists of hardware and software resources that work together to deliver cloud services. The following components were identified in the Ubuntu Linux environment provided by the KillerCoda Playground.

## Observed Resource Summary

| Infrastructure Component | Observed Resource in KillerCoda |
|---|---|
| Compute | 1 virtual CPU core using an Intel Xeon E312xx processor |
| Storage | 20 GB virtual disk with a 19 GB main partition |
| Networking | Active `enp1s0` interface with the primary IP address 172.30.1.2 |
| Operating System | Ubuntu 24.04.4 LTS with Linux kernel 6.8.0-138-generic |

## 1. Compute Resources

**Example:** One virtual CPU core using an Intel Xeon E312xx processor

**Purpose:** Compute resources process instructions, perform calculations, and run applications and services.

**Importance in Cloud Computing:** Compute resources provide the processing power required to operate virtual machines, containers, websites, databases, and other cloud workloads. Cloud providers can increase or decrease compute capacity depending on the needs of an application.

**Relation to KillerCoda:** The `lscpu` and `nproc` commands showed that the KillerCoda server uses an Intel Xeon E312xx processor and provides one virtual CPU core. This CPU executes Linux commands and supports the applications running inside the environment.

## 2. Storage Resources

**Example:** A 20 GB virtual disk with a 19 GB ext4 main partition

**Purpose:** Storage resources save operating system files, applications, documents, logs, and other forms of data.

**Importance in Cloud Computing:** Storage allows cloud applications to keep and retrieve data. It also supports backups, file sharing, databases, and the long-term preservation of information.

**Relation to KillerCoda:** The `lsblk` and `df -hT` commands showed a 20 GB virtual disk. Its main partition has a capacity of 19 GB and is mounted at `/`, while other partitions are mounted at `/boot` and `/boot/efi`.

## 3. Networking Resources

**Example:** The `enp1s0` network interface with the IP address 172.30.1.2

**Purpose:** Networking resources allow users, servers, storage systems, and cloud services to communicate with one another.

**Importance in Cloud Computing:** Networking provides connectivity between cloud resources and allows users to access cloud applications through the internet. It also supports traffic management, resource isolation, and secure communication.

**Relation to KillerCoda:** The `hostname -I` and `ip -brief address` commands showed that the active `enp1s0` interface uses the primary IP address 172.30.1.2. A Docker bridge network with the IP address 172.17.0.1 was also present in the environment.

## 4. Operating System

**Example:** Ubuntu 24.04.4 LTS with Linux kernel 6.8.0-138-generic

**Purpose:** The operating system manages the server's processor, memory, storage, network interfaces, processes, users, and applications.

**Importance in Cloud Computing:** An operating system provides the environment needed to run cloud applications and manage infrastructure resources. Linux is widely used for cloud servers because it is stable, secure, flexible, and compatible with many cloud technologies.

**Relation to KillerCoda:** The `/etc/os-release` file and `uname -r` command confirmed that the server runs Ubuntu 24.04.4 LTS with kernel version 6.8.0-138-generic. This Linux environment allowed the inspection of the server's compute, storage, and networking resources.
