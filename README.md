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
