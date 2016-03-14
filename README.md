Darkmod installer (for tdm 2.02) - Debian Software Package

Created by Freyk
https://sites.google.com/site/freykssite01
http://forums.thedarkmod.com/user/13309-freyk/


** Introduction **
This is the source for creating a debian softwarepackage, 
for installing the darkmod updater.
The softwarepackage instructs the packagemanager,
to create a darkmod-folder in /usr/share/games, extracts the updater to that
folder and set the right permissions.
It also extracts desktop-shortcuts in /usr/share/applications for the updater
and the game-binary.

installation
Install packages
extract the source folder from the zip file to another folder.


Compiling
navigate to the source folder
and run the following command:
dpkg-deb --build TheDarkMod_2.04

Bugs
Tested with xubuntu 14.0

Known Bugs:
- When you run the deb file with your application manager, serveral security
warning will be shown. (solving the bad quality is worked on)
- The softwarepackage doesnt have the darkmod gamebinary, so the shortcut doesn't work.



** Bugfixes ***
v005 (20150226)
-	Removed scriptlines in postin that generates the desktop files for the tdm-updater and gamebinary.
-	Created new .desktop files for the tdm-updater and gamebinary.
-	The .desktop-file for the updater launches "shell" that executes the tdm-updater
	with parameter "--noselfupdate". 
	And added "$SHELL" to the exec commando, 
	so the tdm-updater doesnt automaticly close the terminal window anymore.
-	The tdm-updater must be manually updated by executing it in a terminal. 
-	Added a copy command to postin to copy the .desktop-files to /usr/share/applications

v004 (20160214)
-	Changes in control file (following debian policy packaging rules)
-	Changed package name (following debian policy packaging rules)
-	Added scriptlines in postrm to remove the tdm .desktop files during uninstall


v003 (20160211)
-	Changed Permissions
-	Added postrm-script
-	Checked the .desktop files with desktop-file-validate and repaired errors

v002 (20160207)
-	Unknown

V001 (unknown)
-	Unknown
