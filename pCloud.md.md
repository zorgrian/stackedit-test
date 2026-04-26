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

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY5MDUzMjgxMCwxODcxODIwNjE3XX0=
-->