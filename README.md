# Disabling-Windows-Real-Time-Protection
Disabling Windows Real Time Protection in a Dell Inspiron 15 3000 Windows 11 


Disable real-time protection:

    Open Local Group Policy Editor (type gpedit.msc in the search box)
    Computer Configuration > Administrative Templates > Windows Components > Microsoft Defender Antivirus > Real-time Protection
    Enable Turn off real-time protection
    Restart the computer

Disable Microsoft Defender:

    Open Local Group Policy Editor (type gpedit.msc in the search box)
    Computer Configuration > Administrative Templates > Windows Components > Microsoft Defender Antivirus
    Enable Turn off Microsoft Defender Antivirus
    Restart the computer
    
    
    Regedit.exe
    HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender
    New > DWORD DisableAntiSpyware
    Set it to 1
    Reboot

If the above doesn't work then one more step:

    Regedit.exe
    HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Real-Time Protection (create this key if not existing)
    New > DWORD DisableBehaviorMonitoring; set it to 1
    New > DWORD DisableOnAccessProtection; set it to 1
    New > DWORD DisableScanOnRealtimeEnable; set it to 1
    Reboot
Note: Please use at your own caution, if neccessary and you have physical access to the device a complete clean install of windows may be neccessary I used the link below 
https://pureinfotech.com/reset-windows-11-boot/

In my case for some reason windows security settings were whited-out and I wasn't able to access any of the settings, tamper prevention remained on and when I reset my laptop windows defender automatically restarted.
