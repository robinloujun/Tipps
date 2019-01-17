# Sublime Text 3

## Installation

source: [homepage](https://www.sublimetext.com/docs/3/linux_repositories.html#apt)

```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://download.sublimetext.com/ apt/dev/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
sudo apt-get update
sudo apt-get install sublime-text
```

In 18.04 -> install the stable release
```
sudo apt-add-repository "deb https://download.sublimetext.com/ apt/stable/"
```

Can also be installed with [tar-file](https://download.sublimetext.com/sublime_text_3_build_3143_x64.tar.bz2)

## Install Package Control
Following the [instruction](https://packagecontrol.io/installation)  
Open the console with ```ctrl+'`'```
```
import urllib.request,os,hashlib; h = 
'6f4c264a24d933ce70df5dedcf1dcaee' + 
'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package 
Control.sublime-package'; ipp = 
sublime.installed_packages_path(); 
urllib.request.install_opener( urllib.request.build_opener( 
urllib.request.ProxyHandler()) ); by = 
urllib.request.urlopen( 'http://packagecontrol.io/' + 
pf.replace(' ', '%20')).read(); dh = 
hashlib.sha256(by).hexdigest(); print('Error validating 
download (got %s instead of %s), please try manual install' 
% (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' 
).write(by) 
```

## Fix problem with Fcitx Input
Source: (sublime-text-imfix)[https://github.com/lyfeyaj/sublime-text-imfix]
```shell
sudo apt-get update && sudo apt-get upgrade
git clone https://github.com/lyfeyaj/sublime-text-imfix.git
cd sublime-text-imfix
./sublime-imfix
```
Final step: Reboot
