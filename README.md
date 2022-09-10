# VipAccess_GUI
Offers a GUI front end to the  python-vipaccess developed by dlenski.

Pre requisites: python-vipaccess, xclip, (zenity, awk)

Installation:

	pip3 install python-vipaccess xclip

Create the provision output:

	vipaccess provision -o ~/.vipaccess

Create/download the files for the VipAccess GUI:

- the executable script:

	~/.local/bin/VipAccess
	
- the .desktop file:

	~/.local/share/applications/VipAccess.desktop
	
- the icon file:

	~/.local/share/icons/VipAccess.png
	
Finally install the application:

	sudo desktop-file-install ~/.local/share/applications/VipAccess.desktop

If all goes well the new application wil show up in the start menu under Other

Usage: Run the VipAccess application from the start menu or desktop or favorites. Register the Token ID that is displayed with your organisation's remote access setup portal, along with the displayed 6-digit access code. There upon when you are ready to enter the access code upon remote login to the organisation you can use the paste function as the 6-digit code would aready have been copied into the clipboard.
