# Ubuntu: File System


## File System

```bash
/bin/         # Basic programs.
/boot/        # Kali Linux kernel + other files required for early boot process.
/dev/         # Device files.
/etc/         # Configuration files.
/home/        # User's personal files.
/lib/         # Basic libraries.
/lost+found/  # ??
/media/       # Mount points for removable devices - CD/DVD-ROM, USB keys, etc.
/mnt/         # Temporary mount point.
/opt/         # Extra applications provided by third parties.
/root/        # Administrator's (root's) personal files.
/run/         # Volatile runtime data that does not persist across reboots. 
/sbin/        # System programs.
/srv/         # Data used by servers hosted on this system.
/tmp/         # Temporary files - often emptied at boot.
/usr/         # Applications.
/usr/share/   # Architecture-independent data.     
/usr/local/   # Used by admin to install apps manually without overwriting files 
              # handled by the packaging system (dpkg).

/var/         # Variable data handled by services - log files, queues, spools, caches.
              # Not yet included in the FHS.

/proc/ +      # Used by the kernel for exporting data to user space.
/sys/         # Specific to the Linux kernel - and not part of the FHS.  
```

## $HOME

The `$HOME` environment variable: 

  * Usually points to `/home/user/`.
  * Is referred to with a `~` tilde.

`dotfiles` is the collective term for application files traditionally found directly under `~/`. 

* The most common are config files which are indicated with a dot - `~/.appconfig` - hence the term. 
* `dotfiles` are hidden by default - to see them, use `ls -la`.

The world is transitioning to the **XDG Base Directory Specification**:

```bash
/home/          # User's personal files.
~/              # /home/user/ - Applications.
~/.config/      # Application config files.
~/.cache/       # Application cache files.
~/.local/sub/   # Application data files.
```