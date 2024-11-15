# Command Prompt

## User

### Get the Current Domain\User

```bat
whoami
```

### Run a Command as Another User

```bat
runas /user:domain\username powershell
```

### Determine if Running in Elevated Privileges

[From Here](https://stackoverflow.com/questions/7985755/how-to-detect-if-cmd-is-running-as-administrator-has-elevated-privileges)

```bat
net session
```

If you are NOT an admin, you get an access is denied message.

```
System error 5 has occurred.

Access is denied.
```

If you ARE an admin, you get a different message, the most common being:

```
There are no entries in the list.
```
