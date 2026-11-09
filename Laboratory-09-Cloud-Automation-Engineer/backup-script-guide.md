# Backup Script Guide

## 1. Purpose

The backup script automatically compresses the application data directory into a timestamped `.tar.gz` archive. Timestamped filenames help distinguish backups created at different times.

## 2. Bash Script

```bash
#!/bin/bash

SOURCE_DIR="app-data"
BACKUP_DIR="backups"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")

echo "Initiating automated backup..."

if [ ! -d "$SOURCE_DIR" ]; then
    echo "Error: Source directory '$SOURCE_DIR' does not exist."
    exit 1
fi

mkdir -p "$BACKUP_DIR"

if tar -czf "$BACKUP_DIR/backup_$TIMESTAMP.tar.gz" "$SOURCE_DIR"; then
    echo "Backup completed successfully at $TIMESTAMP!"
else
    echo "Error: Backup failed."
    exit 1
fi
```

## 3. File Permissions

The command `chmod +x backup.sh` adds executable permission to the script, allowing it to be run directly using `./backup.sh`, subject to the user's other permissions and system restrictions.

## 4. Cron Schedule

```cron
0 2 * * * /root/backup.sh
```

Replace `/root/backup.sh` with the actual absolute path of the script if it is stored elsewhere.

The five Cron time fields are:

| Field | Value | Meaning |
|---|---|---|
| Minute | 0 | At minute zero |
| Hour | 2 | At 2 AM |
| Day of Month | * | Every day of the month |
| Month | * | Every month |
| Day of Week | * | Every day of the week |

The script is scheduled to run daily at 2:00 AM according to the system's configured timezone.

## 5. Verification

The script was tested by running `./backup.sh` and checking the generated archive in the `backups/` directory.

The Cron configuration was checked using `crontab -l`.

## 6. Screenshots

- `screenshots/script-execution.png`
- `screenshots/cron-schedule.png`
