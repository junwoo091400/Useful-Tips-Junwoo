# Useful Tips

### Windows
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
- 

### GIT
1. Remove 'filename too long' error in Git. (ex. Notion backup files)
```Git has a limit of 4096 characters for a filename, except on Windows when Git is compiled with msys. It uses an older version of the Windows API and there's a limit of 260 characters for a filename.

So as far as I understand this, it's a limitation of msys and not of Git. You can read the details here: https://github.com/msysgit/git/pull/110

You can circumvent this by using another Git client on Windows or set core.longpaths to true as explained in other answers.

git config --system core.longpaths true
Git is build as a combination of scripts and compiled code. With the above change some of the scripts might fail. That's the reason for core.longpaths not to be enabled by default.

The windows documentation at https://docs.microsoft.com/en-us/windows/desktop/fileio/naming-a-file has some more information:

Starting in Windows 10, version 1607, MAX_PATH limitations have been removed from common Win32 file and directory functions. However, you must opt-in to the new behavior.

A registry key allows you to enable or disable the new long path behavior. To enable long path behavior set the registry key at HKLM\SYSTEM\CurrentControlSet\Control\FileSystem LongPathsEnabled (Type: REG_DWORD)
```
- So, open up the CMD with `administrator access`, and type in `git config --system core.longpaths true`
- https://stackoverflow.com/questions/22575662/filename-too-long-in-git-for-windows



### Security
1. Change SSH passphrase with `ssh-keygen -p`
- https://blog.sleeplessbeastie.eu/2016/04/04/how-to-change-ssh-private-key-passphrase/