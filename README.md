# EnvSetup

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

## Modify hosts file

### Hosts file format

Entries in the hosts file have the following format:

```text
IPAddress DomainName [DomainAliases]
```

The IP address and the domain names should be separated by at least one space or tab.

### On macOS

Add the following entries into `/etc/hosts`:

```text
# Added by DevOps
127.0.0.1	local.vpc.com
192.168.1.20	intranet.vpc.com
# End of section
```

### On Ubuntu

Add the following entries into `/etc/hosts`:

```text
# Added by DevOps
127.0.0.1	local.vpc.com
192.168.1.20	intranet.vpc.com
# End of section
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
