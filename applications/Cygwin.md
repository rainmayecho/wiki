Cygwin
======

Packages to install
-------------------

- gvim
- openssh
- git

Automatic home directory change
-------------------------------

/etc/nsswitch.conf:

```
db_home: /%H
```

Username
--------

```bash
mkpasswd > /etc/passwd
```

```
vi /etc/passwd
Change username (Shook->shook)
Change home dir (/home/Shook->/cygdrive/c/Users/Shook)
```

ssh and git
-----------

Add id_rsa_personal and id_rsa_work to ~/.ssh/ (from keepass)

```
cd ~/.ssh
cp id_rsa_personal id_rsa
cd
mkdir git
cd git
git clone git@shook.id:configs_scripts
```

Configs
-------

In elevated CMD (not cygwin) prompt:

```
cd /Users/Shook
mklink .bashrc git\configs_scripts\rcfiles\bashrc
mklink .vimrc git\configs_scripts\rcfiles\vimrc
mklink .bash_profile git\configs_scripts\rcfiles\bash_profile
mklink .gitconfig git\configs_scripts\rcfiles\gitconfig
mklink .inputrc git\configs_scripts\rcfiles\inputrc
```

In a cygwin terminal:

```
ln -s /usr/bin/gvim.exe /usr/bin/vim.exe
cp -r ~/git/configs_scripts/vim ~/.vim
```

Vim
---

```
vim
:PluginInstall
```
