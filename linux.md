
# Linux

## Scripting

### Bang lines

Bash:

\#!/bin/bash

### Flags

```sh
set -x # Print command outputs
set -e # Exit on first error
```

### Variable Declaration/Assignment

```sh
a = 15 # Very different!! a is interpreted as a command
a=15   # Proper variable declaration/assignment
```

### Entering the Current Script File Directory

Shell:

```sh
exdir=$(dirname $(readlink -f "$0"))
```

Bash:

```sh
cd "$(dirname "${BASH_SOURCE[0]}")"
```

## Devices

Reload udev rules:

```sh
sudo udevadm control --reload-rules && sudo udevadm trigger
```

## Security

### Service Production Secrets

#### Create a Service

`/etc/systemd/system/TestSecrets.service`

```conf
[Unit]
Description=Test secret read from env file.
DefaultDependencies=no
After=network.target

[Service]
Type=simple
User=<user>
Group=<user>
EnvironmentFile=/root/secrets/TestSecrets.env
ExecStart=/home/<user>/TestSecrets.sh
TimeoutStartSec=0
RemainAfterExit=yes

[Install]
WantedBy=default.target
```

- The environment file is in a directory accessible only by the root user.
- The service is processed by the root user, but the process `TestSecrets.sh` is run by a normal user..
- The protection of secrets is from normal users only (the system administrator can view the secrets).

#### Create a Directory and Assign Permissions

```sh
mkdir /root/secrets
chmod 700 /root/secrets
```

#### Create an Environment File `/root/secrets/TestSecrets.env`

```sh
VARIABLE="This is a secret."
```

#### Create a Simple Script

`/home/<user>/TestSecrets.sh`

```sh
#!/bin/bash

echo "User: $(whoami)"
echo "Variable: ${VARIABLE}"
```

#### Reload and Start the Service

```sh
systemctl daemon reload
systemctl start TestSecrets.service
```

#### View the Script Service Output from Logs

```sh
journalctl -u TestSecrets.service
```

Outputs something like this:

```txt
Started Test secret read from env file.
User: <user>
Variable: This is a secret.
```

### Environment

#### Running a Command Importing an Environment File

```sh
eval $(sudo cat "/root/secrets/<file name>.env") <command>
```
