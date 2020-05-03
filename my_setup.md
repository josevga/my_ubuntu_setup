# My setup (inuc) - Ubuntu 20.04

<!-- {ignore=true} -->

Ubuntu 20.04
Date: 2020-04-24

# Table of Contents

[TOC]

# Conky

Link: https://linuxconfig.org/ubuntu-20-04-system-monitoring-with-conky-widgets

	sudo apt install conky-all
	cp /etc/conky/conky.conf ~/.conkyrc
	
[Back to top](#table-of-contents)

# AnyDesk

Link: http://deb.anydesk.com/howto.html

How to to install AnyDesk DEB repository: run the following commands as root user.

	sudo su

    wget -qO - https://keys.anydesk.com/repos/DEB-GPG-KEY | apt-key add -

    echo "deb http://deb.anydesk.com/ all main" > /etc/apt/sources.list.danydesk-stable.list

    apt update
    apt install anydesk

[Back to top](#table-of-contents)

# SNX Checkpoint VPN SSL client

Link: https://unix.stackexchange.com/questions/450229/getting-checkpoint-vpn-ssl-network-extender-working-in-the-command-line

Install snx build 800007075

    wget https://starkers.keybase.pub/snx_install_linux30.sh?dl=1 -O snx_install.sh

    sudo dpkg --add-architecture i386
    sudo apt-get update
    sudo apt-get install libstdc++5:i386 libx11-6:i386 libpam0g:i386
    
    chmod a+rx snx_install.sh
    sudo ./snx_install.sh`

Check if any dynamic libraries are missing with:

    sudo ldd /usr/bin/snx

To connect:

    $ snx
    Check Point's Linux SNX
    build 800007075
    Please enter your password:

To disconnect:

    $snx -d
    SNX - Disconnecting...
    done.

[Back to top](#table-of-contents)

# Brave

    sudo apt update
    sudo apt -y install curl software-properties-common apt-transport-https 

    curl -s https://brave-browser-apt-release.s3.brave.com/brave-core.asc | sudo apt-key --keyring /etc/apt/trusted.gpg.d/brave-browser-release.gpg add -

    echo "deb [arch=amd64] https://brave-browser-apt-release.s3.brave.com/ stable main" | sudo tee /etc/apt/sources.list.d/brave-browser-release.list

    sudo apt update
    sudo apt install -y brave-browser

[Back to top](#table-of-contents)

# Other Gnome & Ubuntu stuff

## Media codecs to play MP3, MPEG4 and other media files

    sudo apt install ubuntu-restricted-extras

## Gnome Shell Extensions on Ubuntu 20.04

    sudo apt install gnome-shell-extensions

## Gnome Dconf-Editor

    Sudo apt install dconf-editor

## Dock customized

    gsettings set org.gnome.shell.extensions.dash-to-dock extend-height false
    gsettings set org.gnome.shell.extensions.dash-to-dock dock-position LEFT
    gsettings set org.gnome.shell.extensions.dash-to-dock transparency-mode FIXED
    gsettings set org.gnome.shell.extensions.dash-to-dock transparency-mode DYNAMIC
    gsettings set org.gnome.shell.extensions.dash-to-dock dash-max-icon-size 32
    gsettings set org.gnome.shell.extensions.dash-to-dock unity-backlit-items true

## Gnome Pomodoro

Gnome Pomodoro extension

    sudo apt-get install gnome-shell-pomodoro

## Mattermost client

[Mattermost dowload deb package](https://mattermost.com/download/)

[Back to top](#table-of-contents)

# Brother DCP-9015CDW

https://www.brother.es/servicios-al-cliente/dcp-9015cdw/descargas

1. Download the tool.(linux-brprinter-installer-*.*.*-*.gz)
The tool will be downloaded into the default "Download" directory.
2. Open a terminal window.
3. Go to the directory you downloaded the file to in the last step. By using the cd command.
`cd Baixades`
4. Enter this command to extract the downloaded file:
`gunzip linux-brprinter-installer-2.2.1-1.gz`
5. Get superuser authorization with the command:
`sudo su`
6. Run the tool:
`bash linux-brprinter-installer-2.2.1-1 DCP-9015CDW`
7. The driver installation will start. Follow the installation screen directions.

[Back to top](#table-of-contents)

# Documentation and other references

## Logitech MX Anywhere 2 customization (optional, not needed):  
https://blog.onee3.org/2016/09/how-to-get-logitech-mx-anywhere-2-to-work-with-ubuntu/

## Cleaning apt failed, unwanted and cache packages.

To remove the packages that failed to install completely,

    sudo apt-get autoclean

Additionally, to remove the apt-cache,

    $ sudo apt-get clean

Finally, to remove the unwanted software dependencies,

    $ sudo apt-get autoremove

[Back to top](#table-of-contents)

# Pending...

More apps and setup stuff...

[Back to top](#table-of-contents)
