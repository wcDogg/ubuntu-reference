# Ubuntu Directories and Files


## Navigation

```bash
clear       # Clear terminal
Ctr+L

pwd         # Print working directory
.           # Ref to current directory
..          # Ref to current directory's parent

cd ~/       # /home/user/
cd /dir     # /dir
cd ..       # Up one level

tree        # List directory content in a tree
ls          # List directory content
ls -l       # In a pretty list
ls -a       # Including hidden
ls -la      # Pretty list + hidden

sudo reboot # Reboot computer
exit        # Log out
```

## Directories

```bash
# Create
mkdir projects

# Delete empty directory
rmdir projects

# Delete directory and it's contents
rm -r projects
```

## Files

```bash
# TOUCH
# If file doesn't exist a zero-byte file is created
# If file exists, data is unchanged, modification and access time is updated
touch hello.txt

# EDITOR
# If file exists, it's opened in editor
# If file doesn't exist, it's created and opened in editor
editor hello.txt
nano hello.txt

# ECHO
# If file doesn't exist, create
# Write or overwrite contents
echo "Hello, World" > hello.txt
# Append string
echo "It's good to see you're still here" >> hello.txt

# CAT
# View a file's contents 
cat hello.txt


```

## SCP: Move Files between Ubuntu to PC

From PowerShell, NOT SSHed to server: 

```bash
# FROM UBUNTU
# Directory and its contents
scp -r -i ~/.ssh/wcd-ubuntu.pem ubuntu@10.xxx.xxx.xxx:/home/ubuntu/my-project C:\Users\wcd\my-project

# Single file
scp -i ~/.ssh/wcd-ubuntu.pem ubuntu@10.xxx.xxx.xxx:/home/ubuntu/my-project/hello.txt C:\Users\wcd\my-project/hello.txt

# FROM PC
# Directory and its contents
scp -r -i ~/.ssh/wcd-ubuntu.pem C:\Users\wcd\my-project ubuntu@10.xxx.xxx.xxx:/home/ubuntu/my-project 

# Single file
scp -i ~/.ssh/wcd-ubuntu.pem C:\Users\wcd\my-project/hello.txt ubuntu@10.xxx.xxx.xxx:/home/ubuntu/my-project/hello.txt 
```


## Search For and Within Files

```bash
find /etc -name hosts     # Files named 'hosts' under given directory
find /etc -name "hosts*"  # Files starting with 'hosts'

grep expression files     # ???
grep expression files -r  # Recursively search all files
```

