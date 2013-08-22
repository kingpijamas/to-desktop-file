to-desktop-file
===============

Bash utility to integrate progams to ubuntu's dash. It creates a .desktop file based on your specifications and then installs it

NOTES
	There's still obviously lots more to do, but it is currently very practical when
	having to deal with your everyday static program.

	For more info on .desktop files, please consult:
	https://help.ubuntu.com/community/UnityLaunchersAndDesktopFiles

USAGE
	My typical use would be 
		to-desktop-file -f "program-name" -i "/opt/program-folder/icon.png" -L /opt/program-folder
	And, if the executable isn't called <program-name>, but <program-name>.sh (or the sorts)
		to-desktop-file -f "program-name" -i "/opt/program-folder/icon.png" -e "/opt/program-folder/program-name.sh" -L /opt/program-folder

SYNOPSIS
	to-desktop-file [-f <app-name>] [-c <comment>] [-e <invocation-command>] [-T] [-t <type>] [-i <absolute-path-to-icon>] [-k <extra-categories>] [-L] [-l <symlink-location>] [-S] [-o <MIME-types-to-open>] [-N] [-h] [<absolute-path-to-program-directory>]

OPTIONS
	-f <app-name>
		Set the app name to <app-name>. This is the name that will
		appear in the desktop entry (and in the links, if -l or -L were
		also called)
	-c <comment>
		Set the comment to <comment>. If this is not called, a default
		comment will be used. Don't be lazy.
	-e <invocation-command>
		Set the 'Exec' attribute of the .desktop file to
		<invocation-command>.
	-T
		Set the application to appear as a terminal application. The
		default value for that attribute is 'false'.
	-t
		Set the application type to <type>. The default value is
		'Application'. Careful with this: do you really want to
		integrate a non-application to the dash?
	-i <absolute-path-to-icon>
		Quite self-explanatory. By default, the icon is set to be any
		image file with the app-name (i.e. without extension)
		[! however, this does not work in ubuntu, so please specify the
		specific path to the installer, with the extension and all].
	-k <extra-categories>
		Add extra categories to your application (i.e. other than
		'Application').
	-L
		Create a symlink to this application in the default location
		(/usr/local/bin). This is probably the best option regarding
		symlinks.
	-l <symlink-location>
		Create a symlink to this application in <symlink-location>.
		USE WITH CARE.
	-S
		Set the StartupNotify attribute to true (it is false by
		default).
	-o <MIME-types-to-open>
		Add all the MIME file formats you want the your application to
		open by default.
	-N
		Set the NoDisplay attribute to true (it is false by default)
	-h
		Print the usage
