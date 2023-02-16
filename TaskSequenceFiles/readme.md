This is a fork of the https://github.com/windows-admins/Intune/tree/main/TaskSequenceFiles repo.

Modifications made were to make the script wait for the profile assignment in Intune to complete and use a parameter for the group tag instead of hardcoding it. This way you can configure the group tag for each task sequence without having to edit the script each time.

You need to customize these variables in Script2.ps1 based on your tenant and app registration.

$Tenant = ""
$clientid = ""
$clientSecret = ""

Read more about this process: https://credibledev.com/intune-hardware-hash-import-during-task-sequence

YouTube Tutorial on the Process: https://youtu.be/-F1IF9kybbU

Script1 - Copies files needed to target machine
Script2 - Uses Get-WindowsAutoPilotInfo script to collect and upload hardware hash. Also contains Teams setup which is optional
Script3 - Does clean up and removes the Config Manager client from the machine, then kicks the device out to OOBE

-------------------------

This part is from the original readme

The purpose of this package is to be able to image a machine via configmgr and have it upload the hardware hash and group tag to your intune tenant and dump you out to OOBE

This will require an azure app registration to work
You have the option of adding teams notifications as well
