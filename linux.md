
# Linux

## Scripting

### Bang lines

Bash:

\#!/bin/bash

### Entering the Current Script File Directory

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
