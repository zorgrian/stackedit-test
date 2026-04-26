1. SAFE BACKUP (local → pCloud)
```bash
rclone copy /mnt/DATA pcloud:DATA --progress --checksum
```
### Why this is safe:

*   `copy` → never deletes anything
*   only adds/updates
*   cannot wipe your cloud
2. SAFE RESTORE (pCloud → local)

```bash
rclone copy pcloud:DATA /mnt/DATA --progress --checksum
```
## Or run the following:
`backup-to-pcloud.sh`:

```bash
#!/usr/bin/env bash
set -euo pipefail

SRC="/mnt/DATA"
DST="pcloud:DATA"

echo "Backup: $SRC → $DST"
read -p "Proceed? (yes/no): " ans
[[ "$ans" == "yes" ]] || exit 1

rclone copy "$SRC" "$DST" --progress --checksum
```

`restore-from-pcloud.sh`:

```bash
#!/usr/bin/env bash
set -euo pipefail

SRC="pcloud:DATA"
DST="/mnt/DATA"

echo "Restore: $SRC → $DST"
read -p "Proceed? (yes/no): " ans
[[ "$ans" == "yes" ]] || exit 1

rclone copy "$SRC" "$DST" --progress --checksum
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbODIyMzIxNTg4LDE4NzE4MjA2MTddfQ==
-->