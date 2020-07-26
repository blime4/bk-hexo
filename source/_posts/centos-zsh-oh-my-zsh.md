---
title: centos zsh oh-my-zsh
tags:
  - centos
  - zsh
  - oh-my-zsh
categories: Tutorial
abbrlink: aac7725
date: 2020-07-15 13:30:10
---

# zsh

```
yum -y install zsh
chsh -s /bin/zsh
reboot
```

# oh-my-zsh

```
yum -y install git
git clone https://gitee.com/blime/ohmyzsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

# 修改主题

```
vim ~/.zshrc
ZSH_THEME=ys
source ~/.zshrc
```