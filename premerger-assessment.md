## CHECAR USUÁRIOS

# What users/localgroups are on the machine?
net users
net localgroups

# More info about a specific user. Check if user has privileges.
net user user1

# View Domain Groups
net group /domain

# View Members of Domain Group
net group /domain <Group Name>

# Firewall
netsh firewall show state
netsh firewall show config

# How well patched is the system?
wmic qfe get Caption,Description,HotFixID,InstalledOn


# scheduled tasks

schtasks /query /fo LIST /v
Otedo

## Unquoted service paths

# Using WMIC
wmic service get name,displayname,pathname,startmode |findstr /i "auto" |findstr /i /v "c:\windows\\" |findstr /i /v """

# Using sc
sc query
sc qc service name

# Look for Binary_path_name and see if it is unquoted.

## Checar portas e serviços

- check services.msc

  $ net start (check current processes)

  $ netstat -nao
  
  0.0.0.0 listening to all interfaces
  127.0.0.1 listen on local machine
  192.168.*.* listening on local network

## Checar processos 

Sysinternals Process Explorer 
Obs: Processos rodando no svchosts.exe, precisa clicar no executável e ir em processo/servicos

tasklist /svc | find "svchost.exe"


