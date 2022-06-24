## Flipper Zero - Windows Development Environment

## Summary 
- This article will be an overview of how to configure a Windows Development Environment for Flipper Zero
- A summary of required tools for Windows and highly suggested tools to assist with development 
- How to clone the Official Firmware to begin development
- How to build the firmware on Windows VIA Docker in CMD or Docker in WSL2 

## Instructions
1) You're going to need to start by **downloading and installing the appropriate tools for development**. I've listed a selection of tools for you to choose from and highlighted the ones that I specifically use with a :frog:. Any of the below tools will work for your required purposes. Please review the [`Required Tools`](https://github.com/FroggMaster/FlipperZero/blob/main/Notes%20and%20Documentation/Windows%20Development%20Environment.md#required-tools) section first.

2) Once you've installed the appropriate tools you're ready to hop into some development! We're going to start by cloning the Flipper Zero Firmware we want to modify.

3) Open **CMD** and navigate to a directory you want to clone the firmware into. Mine is stored in **F:\Projects** you'll note in the below command I include **/d** switch this is to change from the C: drive to the F: drive. 
```batch
cd /d F:\Projects
```
4) Next we're going to actually clone the Firmware we're going to modify. 
```git
git clone https://github.com/flipperdevices/flipperzero-firmware.git
```

5) Once this is done you make the neccesary changes that you want to the firmware files. If you need more information on how to do this I suggest you take a look at [`Hello World Plugin Tutorial`](https://github.com/DroomOne/Flipper-Plugin-Tutorial) to start

6) Once you've completed your changes you're ready to build your firmware! 

### Building with Docker in Windows

1) Open **CMD** ***as an adminsitrator***
2) Navigate to the root of your Firmware Directory
```batch
cd /d F:\Projects\flipperzero-firmware
```
3) Start the Docker Instance
```batch
docker-compose up -d
```
4) Build the Firmware
```batch
docker-compose exec dev make
```
5) You should find the newly built firmware files located in ***\<YourSaveLocation>*****\flipperzero-firmware\dist\f7**

### Building with Docker in WSL2 
1) Open **WSL2** VIA the Windows Start Menu
2) Navigate to the root of your Firmware Directory
```bash
cd /mnt/f/Projects/flipperzero-kokoe-firmware
```
3) Start the Docker Instance ***you will be prompted for admin credentials based on the account you setup when configuring WSL2***
```bash
sudo docker-compose up -d
```
4) Build the Firmware
```bash
docker-compose exec dev make
```
5) You should find the newly built firmware files located in ***\<YourSaveLocation>*****\flipperzero-firmware\dist\f7**

## Required Tools

### Docker
- [`Docker Desktop` Manage Docker instances on Windows](https://www.docker.com/get-started/)

### WSL
- [`WSL2` Windows Subsystem for Linux ](https://docs.microsoft.com/en-us/windows/wsl/install)
    - While WSL2 is not strictly required, I've found at times just Docker Desktop has failed, so I do recommended you setup both. **Docker Desktop will ask to install WSL2 along side, it is suggested you do this.**


## Optional But Highly Recommended
- Options with a :frog: next to them are my personal choice

### Text Editor
- [`VS Code` A plugin/community text editor from Microsoft](https://code.visualstudio.com) :frog:
- [`Notepad++` A source code editor for Windows](https://notepad-plus-plus.org) :frog:
    - I have both of these text editors installed, I find they both work great for different purposes. 
- [`Atom` A hackable text editor for the 21st century / Now depreciated by micrsoft](https://atom.io)


### Git Client
- [`SourceTree` A visual GIT client to help with managing GIT repositories.](https://www.sourcetreeapp.com) :frog:
- [`GitKraken` A visual GIT client to help with managing GIT repositories.](https://www.gitkraken.com)
- [`GitHub Desktop` A visual GIT client to help with managing GIT repositories.](https://desktop.github.com)

### Diff/Merge Tool
- [`DiffMerge` A diff/merge utility to help with handling merge conflicts](https://www.sourcegear.com/diffmerge/downloads.html) :frog:
- [`Kdiff3` A diff/merge utility to help with handling merge conflicts](http://kdiff3.sourceforge.net)
