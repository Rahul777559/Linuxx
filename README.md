#!/bin/bash
# ===== Variables =====
source="/home/user/documents"
destination="/home/user/backup"
date=$(date +%Y-%m-%d)

# ===== Start Message =====
echo "===== Backup Script ====="
echo "Backup started on $date"
echo "Source: $source"
echo "Destination: $destination"
echo ""

# ===== Create Backup Folder =====
mkdir -p "$destination/$date"

# ===== Copy Files =====
echo "Copying files..."
cp -r "$source/"* "$destination/$date/"

# ===== Check Status =====
if [ $? -eq 0 ]; then
    echo "Backup completed successfully!"
    echo "Files saved to: $destination/$date"
else
    echo "Backup failed!"
fi
