DISTCLEANFILES = *~

if ENABLE_CAJA_EXTENSION
CAJA_EXTENSION_DIR = caja-gksu
else
CAJA_EXTENSION_DIR =
endif

SUBDIRS = po $(CAJA_EXTENSION_DIR)
DIST_SUBDIRS = $(SUBDIRS)

EXTRA_DIST = config.rpath intltool-extract.in intltool-merge.in intltool-update.in
