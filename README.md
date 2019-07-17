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

### On MacOS
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

### On MacOS
```shell
brew install tree
```

## Install Anaconda and Pytorch
[Anaconda](https://www.anaconda.com/distribution/)
```shell
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/menpo/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/bioconda/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/msys2/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/cloud/conda-forge/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/main/
conda config --add channels https://mirrors.sjtug.sjtu.edu.cn/anaconda/pkgs/main/
conda config --add channels https://mirrors.sjtug.sjtu.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
```
[Pytorch](https://pytorch.org/)

