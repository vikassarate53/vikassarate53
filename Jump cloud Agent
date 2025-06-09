1) Create Local Administrator Account

Create a local administrator account with the following details:

Username: Csadmin

Password: WelcomeToCorsearch@2025**

net user Csadmin "WelcomeToCorsearch@2025**" /add
net localgroup Administrators Csadmin /add

2) Rename the Device
# Get the device's service tag (serial number)
$serviceTag = (Get-WmiObject -Class Win32_BIOS).SerialNumber.Trim()

# Define the new computer name
$newName = "CORWKS-$serviceTag"

# Rename the computer
Rename-Computer -NewName $newName -Force

# Restart the computer
Restart-Computer


3)JumpCloud Agent Installation
Set-ExecutionPolicy Unrestricted

cd $env:temp | Invoke-Expression; Invoke-RestMethod -Method Get -URI https://raw.githubusercontent.com/TheJumpCloud/support/master/scripts/windows/InstallWindowsAgent.ps1 -OutFile InstallWindowsAgent.ps1 | Invoke-Expression; ./InstallWindowsAgent.ps1 -JumpCloudConnectKey "jcc_eyJwdWJsaWNLaWNrc3RhcnRVcmwiOiJodHRwczovL2tpY2tzdGFydC5qdW1wY2xvdWQuY29tIiwicHJpdmF0ZUtpY2tzdGFydFVybCI6Imh0dHBzOi8vcHJpdmF0ZS1raWNrc3RhcnQuanVtcGNsb3VkLmNvbSIsImNvbm5lY3RLZXkiOiIzOTMzYTViMDg3ZjVhMjVlMzBmOGQzODg1YjRkZjFmYWNlNGRlZmQzIn0g"
