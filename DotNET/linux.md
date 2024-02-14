# DotNET linux

## Installation

- Scripted installation

```sh
wget https://dot.net/v1/dotnet-install.sh -O dotnet-install.sh
chmod +x ./dotnet-install.sh
./dotnet-install.sh
./dotnet-install.sh --channel 6.0

echo "export DOTNET_ROOT=$HOME/.dotnet" >> .bashrc
echo "export PATH=$PATH:$DOTNET_ROOT:$DOTNET_ROOT/tools" >> .bashrc
```
