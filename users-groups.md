# Ubuntu: Users and Groups


## Users

```bash
# Current user
whoami

# Current user ID
id        

# Impersonate a user
su - <user>

# List users
cat /etc/passwd
cut -d: -f1 /etc/passwd
# Entry for root looks like
ubuntu:x:1000:1000:Ubuntu:/home/ubuntu:/bin/bash

# x = Password is stored in /etc/shadow
# 1000:1000 = uid:gid
# /home/ubuntu = User's home directory
# /bin/bash = User's default shell

# Hashed password for root looks like
sudo cat /etc/shadow
ubuntu:!:19247:0:99999:7:::

# Adding a user creates a user + group
# Follow prompts to create account
sudo adduser <user>
# Delete user
sudo userdel <user>

# Set or change password
sudo passwd <user> <password>
# Change user name
sudo usermod -l <new_name> <current_name>
# Change shell
sudo usermod <user> --shell /bin/bash

# Give user SSH access
sudo editor /etc/ssh/sshd_config
# Add this line with root + user
AllowUsers root <user-1> 
# Restart SSH daemon
systemctl restart sshd
```

## Groups

```bash
# List groups
cat /etc/group
# Create a group
sudo groupadd <group-name>
# Delete a group
sudo groupdel <group-name>

# Add user to group - append user's groups
# User will need to log out/in
sudo usermod -aG <group-name> <user>
# Remove user from group
sudo gpasswd -d <user> <group-name>

# See current user's groups
groups
# See a user's groups
groups <user>
# See commands current user can run
sudo -l

# View the sudoers file
# The sudo group may be named %sudo or %wheel
sudo cat /etc/sudoers
# Edit the sudoers file - not recommended
# Consider using /etc/sudoers.d/ instead
sudo visudo

# Give user root power by adding this line
<user> ALL = ALL
# Give user specific permissions - ie, can add users
<user> ALL = /sbin/useradd

# Add group to sudoers file
sudo visudo
# Give group sudo power
%group-name ALL = NOPASSWD:ALL
```

## Managing Rights

Each file + directory has permissions for 3 user categories:

* `u` - The user owner
* `g` - The group owner, representing all users in a group
* `o` - Others

There are 3 types of rights that can be combined:

* `r` - Read
* `w` - Write / modify
* `x` - Execute

Read, write, and execute for files is straightforward. For directories:

* Read access gives the right to view a list of contents - files + directories.
* Write access gives the right to create + delete files
* Execute access gives the right to cross through a directory to access content - ie, using `cd`.

Having execute access without read access restricts user rights to only files that are known by name.

```bash
chown user file         # Change user owner of the file.
chgrp group file        # Change group owner
chown user:group file   # Change owner + group.
chmod rights file       # Change file permissions.
```
