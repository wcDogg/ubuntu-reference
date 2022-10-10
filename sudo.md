# Ubuntu: sudo

```bash
# Sudo is installed on Ubuntu by default
which sudo

# Escalate to root
sudo su
sudo -i

# Exit root user, return to self
exit 

# Impersonate root user
sudo su -
# Impersonate a user
su - <user>

# You just ran a long command but forgot to use sudo.
# Instead of typing it over again, do this.
sudo !!
```
