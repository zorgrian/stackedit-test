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

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg3MTgyMDYxN119
-->