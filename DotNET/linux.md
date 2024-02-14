# DotNET linux

## Installation

- Scripted installation

```sh
wget https://dot.net/v1/dotnet-install.sh -O dotnet-install.sh
chmod +x ./dotnet-install.sh
./dotnet-install.sh
./dotnet-install.sh --channel 6.0

echo "" >> ~/.bashrc
echo "# .NET" >> ~/.bashrc
echo "export DOTNET_ROOT=$HOME/.dotnet" >> ~/.bashrc
echo "export DOTNET_INSTALL_DIR=$DOTNET_ROOT" >> ~/.bashrc
echo "export PATH=$PATH:$DOTNET_ROOT:$DOTNET_ROOT/tools" >> ~/.bashrc
echo "export DOTNET_CLI_TELEMETRY_OPTOUT=true" >> ~/.bashrc
```
