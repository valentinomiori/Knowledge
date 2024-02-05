
# Linux

## Scripting

### Bang lines

Bash:

\#!/bin/bash

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
