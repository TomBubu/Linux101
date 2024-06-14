# Remove Edge browser from Win10
cd C:\Program Files (x86)\Microsoft\Edge\Application\83.0.478.61\Installer 
setup.exe --uninstall --system-level --verbose-logging --force-uninstall 

# Disable Hiberfil.sys (Win10)
Klikni na start, napis cmd a klikni nan pravym a spusti ho ako spravca. V nom potom zadaj powercfg -h off tym za zbavis hiberfil.sys

# Stop telemetry
1. gpedit.msc
2. Computer Configuration > Administrative Templates > Windows Components > Data Collection and Preview
3. Double click Allow telemetry
4. Disable

# Stop autoupdate 
BY POLICY:
1. win+r
2. gpedit.msc 
3. Computer Configuration > Administrative Templates > Windows Components > Windows Update
4. Double-click the Configure Automatic Updates policy on the right side
5. Check the Disabled option to turn off automatic updates permanently on Windows 10
6. Click the Apply button.
7. Click the OK button.

BY REGISTRY:
1. win+r
2. regedit 
3. HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows
4. Right-click the Windows (folder) key, select the New submenu, and then choose the Key option.
5. Name the new key WindowsUpdate and press Enter
6. Right-click the newly created key, select the New submenu, and choose the Key option
7. Name the new key AU and press Enter.
8. Right-click the AU key, select the New submenu, and choose the DWORD (32-bit) Value option.
9. Name the new key NoAutoUpdate and press Enter.
10. Double-click the newly created key and change its value from 0 to 1.
11. Click the OK button.
12. Restart your computer

# Remove bloatware
PS C:\WINDOWS\system32> get-appxpackage|findstr Maps
Name              : Microsoft.WindowsMaps
PackageFullName   : Microsoft.WindowsMaps_5.1909.2813.0_x64__8wekyb3d8bbwe
InstallLocation   : C:\Program Files\WindowsApps\Microsoft.WindowsMaps_5.1909.2813.0_x64__8wekyb3d8bbwe
PackageFamilyName : Microsoft.WindowsMaps_8wekyb3d8bbwe
Dependencies      : {Microsoft.NET.Native.Framework.2.2_2.2.27912.0_x64__8wekyb3d8bbwe, Microsoft.NET.Native.Runtime.2.2_2.2.27328.0_x64__8wekyb3d8bbwe, Microsoft.VCLibs.140.00_14.0.27810.0_x64__8wekyb3d8bbwe, Microsoft.WindowsMaps_5.1909.2813.0_neutral_split.scale-125_8wekyb3d8bbwe...}



https://github.com/Sycnex/Windows10Debloater
First Method

    Download the .zip file on the main page of the github and extract the .zip file to your desired location
    Once extracted, open PowerShell (or PowerShell ISE) as an Administrator
    Enable PowerShell execution Set-ExecutionPolicy Unrestricted -Force
    On the prompt, change to the directory where you extracted the files: e.g. - cd c:\temp
    Next, to run either script, enter in the following: e.g. - .\Windows10DebloaterGUI.ps1



remove-appxpackage -package Microsoft.People_10.1902.633.0_x64__8wekyb3d8bbwe
remove-appxpackage -package Microsoft.WindowsMaps_5.1906.1972.0_x64__8wekyb3d8bbwe
remove-appxpackage -package Microsoft.YourPhone_0.19051.7.0_x64__8wekyb3d8bbwe

Get-AppxPackage *3dbuilder* | Remove-AppxPackage
Get-AppxPackage *windowsalarms* | Remove-AppxPackage
Get-AppxPackage *windowscalculator* | Remove-AppxPackage
Get-AppxPackage *windowscommunicationsapps* | Remove-AppxPackage
Get-AppxPackage *windowscamera* | Remove-AppxPackage
Get-AppxPackage *officehub* | Remove-AppxPackage
Get-AppxPackage *skypeapp* | Remove-AppxPackage
Get-AppxPackage *getstarted* | Remove-AppxPackage
Get-AppxPackage *zunemusic* | Remove-AppxPackage
Get-AppxPackage *windowsmaps* | Remove-AppxPackage
Get-AppxPackage *solitairecollection* | Remove-AppxPackage
Get-AppxPackage *bingfinance* | Remove-AppxPackage
Get-AppxPackage *zunevideo* | Remove-AppxPackage
Get-AppxPackage *bingnews* | Remove-AppxPackage
Get-AppxPackage *onenote* | Remove-AppxPackage
Get-AppxPackage *people* | Remove-AppxPackage
Get-AppxPackage *windowsphone* | Remove-AppxPackage
Get-AppxPackage *photos* | Remove-AppxPackage
Get-AppxPackage *windowsstore* | Remove-AppxPackage
Get-AppxPackage *bingsports* | Remove-AppxPackage
Get-AppxPackage *soundrecorder* | Remove-AppxPackage
Get-AppxPackage *bingweather* | Remove-AppxPackage
Get-AppxPackage *xboxapp* | Remove-AppxPackage
