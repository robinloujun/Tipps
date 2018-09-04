## Initilization for new Ubuntu
```
sudo apt-get install kate
sudo apt-get install okular
sudo apt-get install yakuake
sudo apt-get install git-core
```
add SSH key to github etc. with ```ssh-keygen -t rsa -b 4096 -C "anonymous@mail.com```

## Sogou

Download from the [homepage](https://pinyin.sogou.com/linux/?r=pinyin) and ```sudo dpkg -i Downloads/sogoupinyin_2.2.0.0108_amd64.deb```  

## Dropbox

Download from the [homepage](https://www.dropbox.com/de/install-linux) and ```sudo dpkg -i Downloads/dropbox_2015.10.28_amd64.deb```  
In case of Error with dependencies ```sudo apt-get install -f```  
Can also try [this](https://www.dropbox.com/de/help/desktop-web/linux-commands) with tar-file

## Skype

Download from the [homepage](https://www.skype.com/en/get-skype/) and launch ```sudo dpkg -i Downloads/skypeforlinux-64.deb```

## MATLAB

Download the installer from the [homepage](https://de.mathworks.com/downloads/web_downloads) and extract into a new folder like /home/xxx/MATLAB,   
then install with ```sudo ~/MATLAB/install```. There is an [intruduction](https://de.mathworks.com/help/install/ug/install-mathworks-software.html).

## LaTeX

```
sudo apt-get install texlive-full
sudo apt-get install texstudio
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

## Sublime Text 3

source: [homepage](https://www.sublimetext.com/docs/3/linux_repositories.html#apt)

```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://download.sublimetext.com/ apt/dev/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
sudo apt-get update
sudo apt-get install sublime-text
```
Can also be installed with [tar-file](https://download.sublimetext.com/sublime_text_3_build_3143_x64.tar.bz2)
