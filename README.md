# linux recipes

Install packages and setup environment on Ubuntu.
It is specifically aimed for machine learning development.
Maybe there will be branches in the futrue.

## setup docker

Check `dockerfiles/README.md`.

### executing docker commands as a non-root user

```
sudo usermod -aG docker $USER
```

Some examples of `Dockerfile` are in the submodule `dockerfiles/`.

## setup packages

```
./scripts/packages_setup.sh
```

## setup ssh

```
sudo systemctl status ssh
sudo systemctl start ssh
```

### [copy client key to server](notes/copy_key_to_server.md)

### add key to Github

```
ssh-keygen
```
Add `~/.ssh/id_rsa.pub` to [Github settings](https://github.com/settings/keys)

## setup xrdp

```
sudo systemctl status xrdp
sudo adduser xrdp ssl-cert
```

## setup jupyter

```
./scripts/jupyter_setup.sh
```

## setup dotfiles

```
./scripts/dotfiles_setup.sh
```

## setup vim

### install vim

```
git clone https://github.com/vim/vim --depth 1 ~/Downloads/vim
cd ~/Downloads/vim/src
make distclean
make
sudo make install
cd -
```

### setup [coc.nvim](https://github.com/neoclide/coc.nvim)

```
./scripts/coc-nvim_setup.sh
```

## setup tmux

```
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
~/.tmux/plugins/tpm/scripts/install_plugins.sh
```

## setup python3 virtual environment

```
source ~/.bashrc
mkvirtualenv <env_name>
```
[reference packages](notes/requirements.txt)

## [setup gpu](notes/gpu_setup.md)

## Acknowledgements

This project is inspired by Anish's repository [linux-bootstrap](https://github.com/anishathalye/linux-bootstrap)
