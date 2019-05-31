# Install:

1. MongoDB
2. Node (including NPM)
3. Visual Studio Code
4. Git

# History

References:

- [Raspberry Pi](https://github.com/rkristelijn/pi-ci-mean)
- [Debian](https://github.com/rkristelijn/debian-mexn)
- [Ubuntu](https://github.com/rkristelijn/ubuntu-mexn)
- [Windows](https://github.com/rkristelijn/wsl-mexn)
- [OSX](https://github.com/rkristelijn/osx-mexn)

First, I started off using a [Raspberry Pi](https://github.com/rkristelijn/pi-ci-mean) for Fullstack JavaScript development. Visual Studio Code runs, but it is a bit slow. Then I started using a VirtualBox with Raspbian for x68. This worked great, however limited to 32bit. MongoDB stopped support for 32bit, so I switched to [Debian](https://github.com/rkristelijn/debian-mexn) (Raspbian is derived from Debian) in a Virtual Box on Windows. However [still slow](https://github.com/rkristelijn/wsl-mexn) and not utalizing all my hardware, so I switched to Debian on the bare metal. Super performance, but no wifi driver, so I switched to [Ubuntu](https://github.com/rkristelijn/ubuntu-mexn). Great GUI, bit of performance loss, but very happy. However, now I want to use 3 screens on my [UDOO](https://www.udoo.org/forum/threads/udoox86-ultra-with-3-monitors-fullhd-successfully-installation-with-slackware-14-2-and-fedora-26.7710/) and it seems Mint supports it. Mint is [derived from Ubuntu](https://itsfoss.com/linux-mint-vs-ubuntu/)

Which version? [Linux Mint 18.2 "Sonya" - Cinnamon](https://linuxmint.com/edition.php?id=261), an ISO file flashed with [Startup Disk Creator](https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-ubuntu#0). 

Booting from USB: At first it booted only with two monitors: HDMI-1 and HDMI-3 (DP-3), but after replugging DP-2 it worked.

So I installed it.

# Visual Studio Code

Was not in software center, [but downloading the deb from the web](https://code.visualstudio.com/download), it detected the deb and started up the installer.

# Chrome

Same as above with [downloading Chrome](https://www.google.com/intl/nl/chrome/) In fact, if you use the default, which is Firefox, you get a message to update in github.com.

# Settings

Update your user so you don't have to type your password over and over again:

`sodo vi /etc/sudoers` using `i`, add `user ALL=(ALL) NOPASSWD:ALL` at the last line, `<esc> :wq!`. Works the same as in Debian and Ubuntu.

# Git

```bash
sudo apt-get install git
```

# MongoDB

```bash
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA31620334BD75D9DCB49F368818C72E52529D4

echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.0.list

sudo apt-get update

sudo apt-get install -y mongodb-org
```

Here I got into problems:

```bash
The following packages have unmet dependencies:
 mongodb-org : Depends: mongodb-org-shell but it is not going to be installed
               Depends: mongodb-org-server but it is not going to be installed
               Depends: mongodb-org-mongos but it is not going to be installed
               Depends: mongodb-org-tools but it is not going to be installed

```

Fixing the dependancies using `sudo apt-get install -f` didn't work.

I had to [remove the key](https://askubuntu.com/questions/107177/how-can-i-remove-gpg-key-that-i-added-using-apt-key-add):

Note the key needs to match to your apt-get list entry
```
sudo apt-key list
sudo apt-key del E52529D4
sudo rm /etc/apt/sources.list.d/mongodb-org-4.0.list
```

My [Mint 18.2 version](https://linuxmint.com/download_all.php) is pointing to Ununtu Xenial:

| Mint | Ubuntu | 
| 19.1 "Tessa" | Ubuntu "Bionic" |
| 19 "Tara" | Ubuntu "Bionic" |
| 18.3 "Sylvia" | Ubuntu "Xenial" |
| **18.2 "Sonya"** | **Ubuntu "Xenial"** |
