DISTCLEANFILES = *~

if ENABLE_CAJA_EXTENSION
CAJA_EXTENSION_DIR = caja-gksu
else
CAJA_EXTENSION_DIR =
endif

SUBDIRS = po man gksu $(CAJA_EXTENSION_DIR)
DIST_SUBDIRS = $(SUBDIRS)

icondir = $(datadir)/pixmaps
dist_icon_DATA = gksu-icon.png gksu-root-terminal.png

desktopdir = $(datadir)/applications
desktop_in_files = gksu.desktop.in
dist_desktop_DATA = $(desktop_in_files:.desktop.in=.desktop)
@INTLTOOL_DESKTOP_RULE@

scriptsdir = $(datadir)/gksu
dist_scripts_DATA = gksu-migrate-conf.sh

EXTRA_DIST = config.rpath intltool-extract.in intltool-merge.in intltool-update.in
