#  Reg queries

Cheat sheet reg queries Windows

## Read information

### Get user env var

```
reg query HKCU\Environment /v {Variable Name}
```

### Get AppData path

```
reg query HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders /v AppData
```

### Get user document's folder

```
reg query HKCU\Software\Microsoft\Windows\CurrentVersion\Explorer\Shell Folders
```

### Get last registred key

```
reg query HKCU\Software\Microsoft\Windows\CurrentVersion\Applets\RegEdit /v LastKey
```

### Get typed URL

```
reg query HKCU\Software\Microsoft\InternetExplorer\TypedURLS
```

### Get system policies

```
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System
```

### Get security policy

```
reg query HKLM\SYSTEM\CurrentControlSet\Control\Lsa /v forceguest
```

### Get automatic updates status

```
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\Auto Update /v AUOptions
```

### Get Admin token

```
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System /v FilterAdministratorToken
```

### Get Windows Defender settings 

=> Group Policy switch:

```
reg query HKLM\SOFTWARE\Policies\Microsoft\Windows Defender /v DisableAntiSpyware
```

### Get service config

```
reg query HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services /s
```

### Get Firewall config

```
reg query HKLM\SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy
```

### Get UAC (User Account Control) config

```
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System /v ConsentPromptBehaviorAdmin
```

### Get autorun config

```
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\Explorer /v NoDriveTypeAutoRun
```

### Wrapper to search terms

=> Get all keys that match "XXX":

```
reg query HKLM\SOFTWARE\Microsoft /s /f XXX /k
```

## Tweak settings

### Take cover

**Always backup** the Registry **before** tweaking entries!

### Windows Defender

#### Disable Windows Defender

```
reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender" /v DisableAntiSpyware /t REG_DWORD /d 1 /f
```

#### Enable Windows Defender

```
reg delete "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender" /v DisableAntiSpyware
```

### UAC

#### Disable UAC

```
reg add "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System" /v EnableLUA /t REG_DWORD /d 0 /f
```

#### Enable UAC

```
reg add "HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System" /v EnableLUA /t REG_DWORD /d 1 /f
```
