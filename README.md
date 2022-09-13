# VipAccess_GUI
Offers a GUI front end to the [python-vipaccess](https://github.com/dlenski/python-vipaccess) developed by [dlenski](https://github.com/dlenski).

## Background

Installation of Symantec's VIP Access for Windows on a linux machine (Zorin OS 16.1) for use via Wine was unsuccessful. I therefore came across python-vipaccess, which is a free and open source software (FOSS) implementation of Symantec's VIP Access client (now owned by Broadcom). Wanting the ability to generate the 6-digit codes identical to what Symantec's official apps produce, but via a GUI interface, I discovered zenity after a bit of googling.

## Pre requisites

- python-vipaccess and xclip
- zenity and awk are assumed to be already installed, if not, just add them to the `sudo apt install` line below

## Installation

	pip3 install python-vipaccess
	sudo apt install xclip

## Create the provision output

	vipaccess provision -o ~/.vipaccess

This file is created with read/write permissions only for the current user. Make it readonly for all to preserve the Token ID in case of accidental overwrites.

	chmod -w ~/.vipaccess

## Create/download the files for the VipAccess GUI

- the executable script

		~/.local/bin/VipAccess
	
- the .desktop file

		~/.local/share/applications/VipAccess.desktop
	
- the icon file

		~/.local/share/icons/VipAccess.png

Remember to replace the ~ with /home/yourusername in the above executable script and the .desktop file.

## Finally install the application

	sudo desktop-file-install ~/.local/share/applications/VipAccess.desktop

This checks the syntax of the launcher and (if it has no errors) installs it into `/usr/share/applications`. If all goes well the new application will show up in the start menu under Other

## To do it all automatically

Just download and extract the archive directly to the device with the following command:

	curl -skL https://raw.githubusercontent.com/UncleSam1966/VipAccess_GUI/master/runonce.tar.gz | tar -xzvf -

Then run it manually with `./runonce`. Note that the runonce script will delete itself when it's done.

## Usage
- Run the VipAccess application either from the applications menu or desktop or favorites.
- Register the Token ID that is displayed with your organisation's remote access setup portal, along with the displayed 6-digit access code.
- Thereupon when you are ready to enter the access code upon remote login to the organisation, you can use the paste function as the 6-digit code would aready have been copied into the clipboard.
