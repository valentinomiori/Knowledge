# PowerShell

## Scripting

### Change CWD to Script Directory

```ps1
$ThisScriptPath = $MyInvocation.MyCommand.Path
$DIR = Split-Path $ThisScriptPath
Write-host "Script path: $DIR"

# Temporarily change to the correct folder
Push-Location $DIR

# Do stuff...

# Now back to previous directory
Pop-Location
```

### Logical Operators

| AND  | OR  | XOR  | NOT         |
|------|-----|------|-------------|
| -and | -or | -xor | -not *or* ! |

Example: 

```ps1
echo $($true -and $true)
echo $($true -and !$false)
```