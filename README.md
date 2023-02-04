#  Reg queries

Cheat sheet reg queries Windows

## Read information

### Get system policies

```
reg query HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System
```

### Get Admin token

```
reg query HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System /v FilterAdministratorToken
```

### Get service config

```
reg query HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services /s
```

### Get Firewall config

```
reg query HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy
```

### Get UAC (User Account Control) config

```
reg query HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System /v ConsentPromptBehaviorAdmin
```

### Get autorun config

```
reg query HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\Explorer /v NoDriveTypeAutoRun
```

### Wrapper to search terms

=> Get all keys that match "XXX":

```
reg query HKLM\SOFTWARE\Microsoft /s /f XXX /k
```
