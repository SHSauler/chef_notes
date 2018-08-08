Settings for using WSL for Ubuntu 16.04

### bashrc

Append to `.bashrc`

```
alias cdrive='cd /mnt/c'
export PATH="$HOME/.local/bin:/mnt/c/Program Files/Oracle/VirtualBox:$PATH"
export VAGRANT_WSL_ENABLE_WINDOWS_ACCESS="1"
```
