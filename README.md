# EnvSetup

- [Install Oh My Zsh](#install-oh-my-zsh)
  - [via curl](#via-curl)
  - [via wget](#via-wget)
  - [Install zsh-autosuggestions](#install-zsh-autosuggestions)
  - [Install zsh-syntax-highlighting](#install-zsh-syntax-highlighting)
- [Install tmux](#install-tmux)
  - [On Ubuntu and Debian](#on-ubuntu-and-debian)
  - [On CentOS and Fedora](#on-centos-and-fedora)
  - [On macOS](#on-macos)
- [Configure tmux](#configure-tmux)
- [Configure vim](#configure-vim)
- [Install tree](#install-tree)
  - [On Ubuntu](#on-ubuntu)
  - [On macOS](#on-macos-1)
- [Install jq](#install-jq)
  - [On Ubuntu](#on-ubuntu-1)
  - [On macOS](#on-macos-2)
- [Modify hosts file](#modify-hosts-file)
  - [Hosts file format](#hosts-file-format)
  - [On macOS](#on-macos-3)
  - [On Ubuntu](#on-ubuntu-2)
- [Install imgcat](#install-imgcat)
- [Install Anaconda and Pytorch](#install-anaconda-and-pytorch)

Environment Setup Handbook

## Install Oh My Zsh

### via curl

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

### via wget

```shell
sh -c "$(wget -O- https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Set zsh as default shell if need
```shell
sudo chsh -s /bin/zsh [username]
```

### Install zsh-autosuggestions

```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

Activate the plugin in ~/.zshrc

```text
plugins=([plugins...] zsh-autosuggestions)
```

### Install zsh-syntax-highlighting 

```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

Activate the plugin in ~/.zshrc

```text
plugins=([plugins...] zsh-syntax-highlighting)
```

## Install tmux

### On Ubuntu and Debian

```shell
sudo apt install tmux
```

### On CentOS and Fedora

```shell
sudo yum install tmux
```

### On macOS

```shell
brew install tmux
```

## Configure tmux

```shell
cp .tmux.conf ~/.tmux.conf
cp .shortcut ~/.shortcut
```

Add the following command into .zshrc
```shell
source ~/.shortcut
```

## Configure vim

```shell
cp .vimrc ~/.vimrc
```

Install vundle into .vim
```shell
git clone https://github.com/gmarik/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

Install vim plugins
```shell
vim +BundleInstall +qall
```

## Install tree

### On Ubuntu

```shell
sudo apt-get install tree
```

### On macOS

```shell
brew install tree
```

## Install jq

### On Ubuntu

```shell
sudo apt-get install jq
```

### On macOS

```shell
brew install jq
```

## Modify hosts file

### Hosts file format

Entries in the hosts file have the following format:

```text
IPAddress DomainName [DomainAliases]
```

The IP address and the domain names should be separated by at least one space or tab.

The hosts file changes take effect immediately except in cases that the DNS entries are cached by applications.

### On macOS

Add the following entries into `/etc/hosts`:

```text
# Added by DevOps
127.0.0.1	local.vpc.com
192.168.1.20	intranet.vpc.com
# End of section

# GitHub
# From https://ipaddress.com/website/github.com
140.82.113.3	github.com
# From https://ipaddress.com/website/github.global.ssl.fastly.net#ipinfo
199.232.69.194	github.global.ssl.fastly.net
# From https://ipaddress.com/website/assets-cdn.github.com
185.199.108.153	assets-cdn.github.com
185.199.109.153	assets-cdn.github.com
185.199.110.153	assets-cdn.github.com
185.199.111.153	assets-cdn.github.com
2606:50c0:8000::153	assets-cdn.github.com
2606:50c0:8001::153	assets-cdn.github.com
2606:50c0:8002::153	assets-cdn.github.com
2606:50c0:8003::153	assets-cdn.github.com
# sudo killall -HUP mDNSResponder;say DNS cache has been flushed
```

### On Ubuntu

Add the following entries into `/etc/hosts`:

```text
# Added by DevOps
127.0.0.1	local.vpc.com
192.168.1.20	intranet.vpc.com
# End of section

# GitHub
# From https://ipaddress.com/website/github.com
140.82.113.3	github.com
# From https://ipaddress.com/website/github.global.ssl.fastly.net#ipinfo
199.232.69.194	github.global.ssl.fastly.net
# From https://ipaddress.com/website/assets-cdn.github.com
185.199.108.153	assets-cdn.github.com
185.199.109.153	assets-cdn.github.com
185.199.110.153	assets-cdn.github.com
185.199.111.153	assets-cdn.github.com
2606:50c0:8000::153	assets-cdn.github.com
2606:50c0:8001::153	assets-cdn.github.com
2606:50c0:8002::153	assets-cdn.github.com
2606:50c0:8003::153	assets-cdn.github.com
# sudo killall -HUP mDNSResponder;say DNS cache has been flushed
```

## Install imgcat

```shell
curl https://www.iterm2.com/utilities/imgcat > imgcat
chmod +x imgcat
sudo mv imgcat /usr/local/bin
```

## Install Anaconda and Pytorch

Install [Anaconda](https://www.anaconda.com/distribution/)

Add channels for conda:

```shell
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
```

Please refer to https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/ if getting trouble 

Install [Pytorch](https://pytorch.org/)

Attention: remove "-c pytorch" when installing pytorch
