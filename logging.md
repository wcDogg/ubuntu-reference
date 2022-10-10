# Ubuntu: Logging


```bash
dmesg           # Retrieve kernel logs
journalctl      # Dump all logs chronologically
journalctl -r   # Reverse chronological
journalctl -f   # Continuously print new log entries as they are appended to DB
journalctl -u ssh.service  # Logs from a specific system unit

```

