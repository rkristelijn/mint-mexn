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

Which version? [Linux Mint 19.1 "Tessa" - Cinnamon](https://linuxmint.com/edition.php?id=261), an ISO file flashed with [Startup Disk Creator](https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-ubuntu#0)

