# My Dev Setup

## Configure and setup zsh

```
sudo apt install zsh
```
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
```
cp robbyrussell-nix.zsh-theme ~/.oh-my-zsh/themes
```
```
if [ -n "$IN_NIX_SHELL" ]; then
  ZSH_THEME="robbyrussell-nix"
else
  ZSH_THEME="robbyrussell"
fi
```
```
plugins=(git zsh-syntax-highlighting zsh-autosuggestions nix-shell)
```

### Setup disks (if any extra)

```
mkfs.xfs /dev/sdc, mkfs.xfs /dev/sdb, mkfs.xfs /dev/sdd
```
Mount the devices to the directories

Update fstab

### Setup nix

```
sh <(curl -L https://nixos.org/nix/install) --daemon
```

### Setup github ssh

```
ssh-keygen -t rsa -b 4096 -C "purkaitabhinandan@gmail.com"
```

Update the key in the github UI

Verify 
```
ssh -T git@github.com
```

### Install rustup

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

### Extra deps
apt install pkg-config
apt install libssldev
apt install libssl-dev
apt-get update -y
apt-get install -y libclang-dev
apt-get install libblkid-dev
