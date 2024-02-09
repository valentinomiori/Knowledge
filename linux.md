
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

## Security

### Environment

#### Running a Command Importing an Environment File

```sh
eval $(sudo cat "/root/secrets/<file name>.env") <command>
```
