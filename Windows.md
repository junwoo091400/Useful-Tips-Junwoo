# Tips for Windows OS

1. Access BASH (CMD) quickly by Clicking on Explorer 'address' line, and typing 'cmd'.
- https://www.howtogeek.com/270810/how-to-quickly-launch-a-bash-shell-from-windows-10s-file-explorer/
2. You can edit your credentials saved for different applications (ex. Git, OneDrive, Microsoft) by accessing Credential Manager
- https://support.microsoft.com/en-us/help/4026814/windows-accessing-credential-manager
3. Figure out which process is stopping safe removal of a memory device by:
- Starting 'Event Viewer', and opening up 'Windows Logs' -> 'System'
- Right click on "System" and choose "Filter Current Log"
- In the dialog that comes up, enter "225" (without quotes) where it says "All Event IDs"
- https://superuser.com/questions/87364/can-windows-tell-me-what-is-using-my-usb-drive
4. Remove 'Long path' limit, especially for moving files that have a LONGGG names.
- Inside `regedit`, go to `Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem` and change the value of the key `LongPathsEnabled` to `1`.
- https://www.howtogeek.com/266621/how-to-make-windows-10-accept-file-paths-over-260-characters/