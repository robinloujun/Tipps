# Initilization for new Ubuntu

Synchronize time between ubuntu and windows

```
sudo apt-get install nptdate
sudo ntpdate time.windows.com
sudo hwclock --localtime --systohc
```

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

## Dropbox

Download from the [homepage](https://www.dropbox.com/de/install-linux) or directly download the [deb file](https://www.dropbox.com/download?dl=packages/ubuntu/dropbox_2015.10.28_amd64.deb) and ```sudo dpkg -i Downloads/dropbox_2015.10.28_amd64.deb```  
In case of Error with dependencies ```sudo apt-get install -f```  
Can also try [this](https://www.dropbox.com/de/help/desktop-web/linux-commands) with [tar-file](https://github.com/robinloujun/Tipps/blob/master/Files/nautilus-dropbox-1.6.2.tar.bz2)  
In case of website problem click [here](https://github.com/robinloujun/Tipps/blob/master/Files/dropbox_2015.10.28_amd64.deb?raw=true)

## Skype

Download from the [homepage](https://www.skype.com/en/get-skype/) or directly download the [deb file](https://go.skype.com/skypeforlinux-64.deb) and launch ```sudo dpkg -i Downloads/skypeforlinux-64.deb```

## QtCreator

`sudo apt-get install build-essential libgl1-mesa-dev`  
Download from the [homepage](http://download.qt.io/official_releases/qt/), choose a version and download the installer, set the file permission using `chmod +x ~/Downloads/qt-opensource-linux-x64-5.11.1.run`, then run the installer with `~/Downloads/qt-opensource-linux-x64-5.11.1.run`.

## MATLAB

Download the installer from the [homepage](https://de.mathworks.com/downloads/web_downloads) and extract into a new folder like /home/user/MATLAB,   
then install with ```sudo ~/MATLAB/install```. There is an [intruduction](https://de.mathworks.com/help/install/ug/install-mathworks-software.html).
One more thing to do: add an entry to the launcher with ```sudo apt-get install matlab-support```    
Once user in matlab-support false, then [refer](https://de.mathworks.com/matlabcentral/answers/98599-why-will-matlab-not-start-up-properly-on-my-linux-or-unix-based-system)  
In case of error ```Cannot write to preference file "matlab.prf" in "/home/user/.matlab/R2008b".Check file permissions.```, run ```sudo chown rootuser /home/user/.matlab/```.

## JabRef

[Java-related](http://help.jabref.org/en/Installation#verify-java-installation) and `sudo apt-get install jabref`


## Customize the terminal
[A useful .bashrc generator](http://bashrcgenerator.com/)

```
export PS1="\[\033[38;5;11m\]\u@\h\[$(tput sgr0)\]\[\033[38;5;15m\]:\[$(tput sgr0)\]\[\033[38;5;46m\]\w\[$(tput sgr0)\]\[\033[38;5;10m\]:\[$(tput sgr0)\]\[\033[38;5;15m\] \[$(tput sgr0)\]"
```

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

## When harddisk not properly unpluged
i.e. `Error mounting /dev/sda1`   
Run `sudo ntfsfix /dev/sda1` to fix it

## Shell
Disable the touchpad:
```shell
synclient touchpadoff=1
```
Enable the touchpad:
```shell
synclient touchpadoff=0
```
