# tmux

### Installation

```
sudo apt-get update
sudo apt-apt install git automake build-essential pkg-config libevent-dev libncurses5-dev
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

# Dropbox on Ubuntu

Download from the [homepage](https://www.dropbox.com/de/install-linux) and ```sudo dpkg -i Downloads/dropbox_2015.10.28_amd64.deb```  
In case of Error with dependencies ```sudo apt-get install -f```  
Can also try [this](https://www.dropbox.com/de/help/desktop-web/linux-commands) with tar-file

# Skype for Linux

Download from the [homepage](https://www.skype.com/en/get-skype/) and launch ```sudo dpkg -i Downloads/skypeforlinux-64.deb```

# Sublime Text 3

source: [homepage](https://www.sublimetext.com/docs/3/linux_repositories.html#apt)

```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://download.sublimetext.com/ apt/dev/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
sudo apt-get update
sudo apt-get install sublime-text
```
Can also be installed with [tar-file](https://download.sublimetext.com/sublime_text_3_build_3143_x64.tar.bz2)
