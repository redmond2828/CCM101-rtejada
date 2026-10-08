# System Baseline Report

## Environment

KillerCoda Ubuntu 24.04.

## Memory Check

Command: `free -h`

- Total RAM: 1.9Gi
- Used RAM: 400Mi
- Available RAM: 1.5Gi

![Memory check](screenshots/memory-check.png)

## Disk Check

Command: `df -h /`

- Root filesystem: /dev/vda1
- Total capacity: 19G
- Used space: 5.5G
- Available space: 13G
- Disk utilization: 30%

Checking disk space before a traffic surge is critical because growing logs and application data can fill the disk and cause service failures.

![Disk check](screenshots/disk-check.png)
