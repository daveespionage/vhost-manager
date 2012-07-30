To use the (sort of) automated sites folder on windows with xampp:

* put files in /bin
* edit the vhost file where it says "[YOUR_WINDOWS_USER_NAME_HERE]" to ... your windows user name
* disable UAC (otherwise the script will alert you every time it runs)
	** go to control panel > system and security > Change User Account Control settings
	** move slider to the bottom (do not notify)
* open cmd as admin (symlinks cannot be created unless in admin cmd)
	** hit the windows key or click the start bubble
	** type "cmd" and hit ctrl+shift+enter (at the same time)
* set up environment
	** mkdir c:\bin
	** copy vhost and runvhost.bat to c:\bin
	** mkdir c:\sites
	** cd c:\sites
	** mklink /D sitename c:\work\site\sitepublicfolder
	** repeat for all additional sites
* if you have custom environment settings:
	** open a new notepad instance
	** in an empty text file, type or paste custom environment lines
	** save to c:\sites\.sitename (no extension!)
	** repeat for all additional sites with custom environment settings
Windows makes it absurdly complicated to get a scheduled task that runs without popping up a windown in front of you every 5 minutes, so scheduled tasks are out.  
Your best bet is
* create a shortcut on the desktop 
	** Target: C:\bin\runvhost.bat
	** Run: Minimized
	** Advanced: Run as administrator
	
Now when you add a new symlink, click the shortcut AND PRESTO!