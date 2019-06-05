
Debian
====================
This directory contains files used to package vaultd/vault-qt
for Debian-based Linux systems. If you compile vaultd/vault-qt yourself, there are some useful files here.

## vault: URI support ##


vault-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install vault-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your vaultqt binary to `/usr/bin`
and the `../../share/pixmaps/vault128.png` to `/usr/share/pixmaps`

vault-qt.protocol (KDE)

