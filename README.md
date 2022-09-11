# VipAccess_GUI
Offers a GUI front end to the [python-vipaccess](https://github.com/dlenski/python-vipaccess) developed by [dlenski](https://github.com/dlenski).

## Pre requisites:

	python-vipaccess and xclip. (zenity and awk are assumed to be already installed, if not just add them to the `sudo apt install` line below)

## Installation:

	pip3 install python-vipaccess
	sudo apt install xclip

## Create the provision output:

	vipaccess provision -o ~/.vipaccess

This file is created with read/write permissions only for the current user.

## Create/download the files for the VipAccess GUI:

- the executable script:

		~/.local/bin/VipAccess
	
- the .desktop file:

		~/.local/share/applications/VipAccess.desktop
	
- the icon file:

		~/.local/share/icons/VipAccess.png

Remember to replace the ~ with /home/yourusername in the above executable script and the .desktop files.

## Finally install the application:

	sudo desktop-file-install ~/.local/share/applications/VipAccess.desktop

This checks the syntax of the launcher and (if it has no errors) installs it into `/usr/share/applications`. If all goes well the new application will show up in the start menu under Other

## Usage:
- Run the VipAccess application either from the applications menu or desktop or favorites.
- Register the Token ID that is displayed with your organisation's remote access setup portal, along with the displayed 6-digit access code.
- Thereupon when you are ready to enter the access code upon remote login to the organisation, you can use the paste function as the 6-digit code would aready have been copied into the clipboard.
