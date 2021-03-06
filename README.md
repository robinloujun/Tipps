# Initilization for new Ubuntu

Synchronize time between ubuntu and windows

```
timedatectl set-local-rtc 1 --adjust-system-clock
```
to check the result, run `timedatectl` and the result should be `RTC in local TZ: yes`

## Basic tools
```shell
sudo apt-get install okular yakuake
```
Configurate the git
```shell
sudo apt-get install git-core
```
Add SSH key to github etc. with ```ssh-keygen -t rsa -b 4096 -C "anonymous@mail.com```  

Install Sublime Text 3 following [Sublime Installation](https://github.com/robinloujun/Tipps/blob/master/Sublime.md#installation)

## LaTeX

```shell
sudo apt-get install texlive-full
sudo apt-get install texstudio
```

## Sogou

```shell
sudo apt-get install fcitx-bin
```
Download from the [homepage](https://pinyin.sogou.com/linux/?r=pinyin) or directly download the [deb file](http://cdn2.ime.sogou.com/dl/index/1524572264/sogoupinyin_2.2.0.0108_amd64.deb?st=zJbjTyOEj5URSDHKoqOZ3A&e=1539533248&fn=sogoupinyin_2.2.0.0108_amd64.deb) and ```sudo dpkg -i Downloads/sogoupinyin_2.2.0.0108_amd64.deb```    
In case of website problem click [here](https://github.com/robinloujun/Tipps/blob/master/Files/sogoupinyin_2.2.0.0108_amd64.deb?raw=true)

In Settings -> Region & Language -> Manage Installed Languages, set the `Keyboard input method System` to fctix and install Chinese (symplified)

## Dropbox

Download from the [homepage](https://www.dropbox.com/de/install-linux) or directly download the [deb file](https://www.dropbox.com/download?dl=packages/ubuntu/dropbox_2015.10.28_amd64.deb) and ```sudo dpkg -i Downloads/dropbox_2015.10.28_amd64.deb```  
In case of Error with dependencies ```sudo apt-get install -f```  
Can also try [this](https://www.dropbox.com/de/help/desktop-web/linux-commands) with [tar-file](https://github.com/robinloujun/Tipps/blob/master/Files/nautilus-dropbox-1.6.2.tar.bz2)  
In case of website problem click [here](https://github.com/robinloujun/Tipps/blob/master/Files/dropbox_2015.10.28_amd64.deb?raw=true)

## Skype

Download from the [homepage](https://www.skype.com/en/get-skype/) or directly download the [deb file](https://go.skype.com/skypeforlinux-64.deb) and launch ```sudo dpkg -i Downloads/skypeforlinux-64.deb```

## QtCreator

`sudo apt-get install build-essential libgl1-mesa-dev`  
Download from the [homepage](http://download.qt.io/official_releases/qt/), choose a version and download the installer, set  the file permission using `chmod +x ~/Downloads/qt-opensource-linux-x64-5.11.1.run`, then run the installer with `~/Downloads/qt-opensource-linux-x64-5.11.1.run`.

The [Qt Creator with ROS Plug-in](https://ros-qtc-plugin.readthedocs.io/en/latest/index.html) is now also availabel in [Bionic](https://qtcreator-ros.datasys.swri.edu/downloads/installers/bionic/qtcreator-ros-bionic-latest-online-installer.run)

## IntelliJ

Download from the [homepage](https://www.jetbrains.com/idea/download/index.html#section=linux), choose the community version. Extract the files using ```sudo tar -zxvf ideaIC-2018.3.2.tar.gz -C /opt```, then initialize the IDE with ```/opt/idea-IC-183.4886.37/bin/idea.sh```.

## MATLAB

Download the installer from the [homepage](https://de.mathworks.com/downloads/web_downloads) and extract into a new folder like /home/user/MATLAB,   
then install with ```sudo ~/MATLAB/install```. There is an [intruduction](https://de.mathworks.com/help/install/ug/install-mathworks-software.html).
One more thing to do: add an entry to the launcher with ```sudo apt-get install matlab-support```    
Once user in matlab-support false, then [refer](https://de.mathworks.com/matlabcentral/answers/98599-why-will-matlab-not-start-up-properly-on-my-linux-or-unix-based-system)  
In case of error ```Cannot write to preference file "matlab.prf" in "/home/user/.matlab/R2018b".Check file permissions.```, run ```sudo chown rootuser /home/user/.matlab/R2018b```. (regarding the matlab version)

## JabRef

[Java-related](http://help.jabref.org/en/Installation#verify-java-installation) and `sudo apt-get install jabref`

## XMind (Mind Mapping APP)
Download from the [homepage](https://www.xmind.net/download/) and launch ```sudo dpkg -i Downloads/XMind-ZEN-for-Linux-64bit.deb```

## HP eprint
Download from the [homepage](https://developers.hp.com/hp-linux-imaging-and-printing/gethplip) and launch with
```shell
chmod +x Downloads/hplip-3.19.5.run
./Downloads/hplip-3.19.5.run
```

## ROS key problem

Since 06.2019 the key of ROS has been updated and the old one is no longer valid, causing the issues with apt update and apt install.

```shell
sudo apt-key del 421C365BD9FF1F717815A3895523BAEEB01FA116
sudo -E apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
```

## Customize the terminal
[A useful .bashrc generator](http://bashrcgenerator.com/)

```bash
export PS1="\[\033[38;5;11m\]\u@\h\[$(tput sgr0)\]\[\033[38;5;15m\]:\[$(tput sgr0)\]\[\033[38;5;46m\]\w\[$(tput sgr0)\]\[\033[38;5;10m\]:\[$(tput sgr0)\]\[\033[38;5;15m\] \[$(tput sgr0)\]"
```

Add git branch name into prompt:
```bash
GIT_RADAR="/home/robin/Documents/git-radar/git-radar --bash "
# if $GIT_RADAR_DO_NOT_FETCH is not set
if [ -z "$GIT_RADAR_DO_NOT_FETCH" ]; then
  GIT_RADAR="$GIT_RADAR --fetch "
fi

# write branch name into prompt
PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\[\033[0;32m\]$($GIT_RADAR) \[\033[1;30m\]$\[\033[00m\] '
```
git-radar found [here](/git-radar)

## Add Startup Application

Take yakuake as an example
In `Startup Applications Preferences`, add the following items

|||
|:--:|:--:|
|Name:|Yakuake|
|Command:|sh -c "sleep 3s;yakuake"|
|Comment:|Launch the KDE Yakuake|

## tmux
An option for splitting the terminal
### Installation

```
sudo apt-get update
sudo apt-get install git automake build-essential pkg-config libevent-dev libncurses5-dev
rm -fr /tmp/tmux
git clone https://github.com/tmux/tmux.git /tmp/tmux
cd /tmp/tmux
sh autogen.sh
./configure && make
sudo make install
cd -
rm -fr /tmp/tmux
```

### Shortcuts

In tmux, hit the prefix `ctrl+b` and then:

<center>
  
  |Command|Function|
  |:---:|:---|
  |% | vertical split|
  |" | horizontal split|

</center>

# For XPS 15 9560

## Before installing Ubuntu
**Pre-setting in Windows:**      
Boot laptop and press F12 -> BIOS Setup    
System Configuration -> SATA Operation    
Change SATA Operation from "RAID On" to "AHCI" (So the installer can detect the hard disk)
Check that Secure Boot -> Secure Boot Enable -> Disabled.

## Problem: cannot reboot

- NVIDIA driver: System Settings -> Software & Updates -> NVIDIA Corporation: Unknow - Using NVIDIA binary library
- Grub: `sudo gedit /etc/default/grub` -> Find GRUB_CMDLINE_LINUX="" and change it to GRUB_CMDLINE_LINUX=”reboot=efi”

## Position of Certificate Authority (CA) in Ubuntu
/etc/ssl/certs/

### A note
http://ppa.launchpad.net/bzindovic/suitesparse-bugfix-1319687/ubuntu
```shell
E: The repository 'http://ppa.launchpad.net/bzindovic/suitesparse-bugfix-1319687/ubuntu bionic Release' does not have a Release file.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
```
In Software & Updates

|Item||
|--|--|
|type|binary|
|URI|http://ppa.launchpad.net/bzindovic/suitesparse-bugfix-1319687/ubuntu|
|Distribution|bionic|
|Components|main|
|Comment||
