Get-WmiObject is used to get information about the operating system
`win32_OperatingSystem` used for learning about the OS 
`Win32_Process` list process
`Win32_Service` services
`Win32_Bios` BIOS information

### File Systems
1. FAT12
2. FAT16
3. FAT32
4. NTFS
5. exFAT
File allocation table

	 When a Windows system is part of a workgroup, all `netlogon` requests are authenticated against that particular Windows system's `SAM` database.

## Integrity Control Access Control List (icacls)

The possible inheritance settings are:

- `(CI)`: container inherit
- `(OI)`: object inherit
- `(IO)`: inherit only
- `(NP)`: do not propagate inherit
- `(I)`: permission inherited from parent container

Basic access permissions are as follows:

- `F` : full access
- `D` :  delete access
- `N` :  no access
- `M` :  modify access
- `RX` :  read and execute access
- `R` :  read-only access
- `W` :  write-only access

```cmd-session
C:\htb> icacls c:\users /grant joe:f
```


Get-Service will retrieve services to your powershell that you can then pipe to see what is running 
```powershell-session
PS C:\htb> Get-Service | ? {$_.Status -eq "Running"} | select -First 2 |fl
```

service accounts login failure script can be used as an exploit
```
sc qc
```
is used to query information abt services

```cmd-session
C:\WINDOWS\system32> sc sdshow wuauserv
```
`Security Descriptor Definition Language`
is used to gather security info on services
`Discretionary Access Control List` (`DACL`)
`System Access Control List` (`SACL`)


 Credential Guard is a feature in Windows 10 that protects against credential theft attacks by isolating the operating system's LSA process.

