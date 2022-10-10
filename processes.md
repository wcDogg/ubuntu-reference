# Ubuntu: Processes


```bash
# Run app in foreground
google-chrome 
     
# List running processes with PID
ps aux
# Keyboard interrupt
Ctrl+C   

sudo kill -9 15618

# Run app in background
google-chrome &  
# In background with stdout and stderr messages suppressed
google-chrome > /dev/null 2>&1 & 
# List jobs running in background
jobs
# Pause a job in background
Ctrl+Z
# Restart job in background
bg %job-number
# Restore job to foreground
fg %<job-number>

# Reload a background process
kill -1 <PID>
# Forcibly Kill a background job
kill -9 <PID>
# Gracefully terminate a background job
kill -15 <PID>
```
