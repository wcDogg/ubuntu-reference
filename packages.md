# Ubuntu: Packages


```bash
# See what's installed
dpkg -l

# Path to all files associated with an app
whereis <app> 
# Path to app + version
which <app>   

# Check the distro + 3rd parties for the latest package list
# Does NOT download or install packages
sudo apt update   
# Update all currently installed packages to their latest version              
sudo apt -y upgrade 

# Install an app
sudo apt -y install nmap  

# Uninstall apps
sudo apt purge xrdp     # Remove app + its files
sudo apt clean          # Clean up after remove or purge
sudo apt autoremove -y  # Remove unused packages

# Fix a failed install 
sudo apt -f install  
sudo apt -f -y install
sudo apt install --fix-broken -y
```
