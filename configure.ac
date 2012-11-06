#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ(2.57)

AC_INIT(caja-gksu, 1.4.0, http://www.mate-desktop.org/)
AM_INIT_AUTOMAKE(AC_PACKAGE_NAME, AC_PACKAGE_VERSION)
AC_CONFIG_SRCDIR(caja-gksu/libcaja-gksu.c)
AM_CONFIG_HEADER(config.h)

AM_MAINTAINER_MODE

AC_DEFINE(PACKAGE, AC_PACKAGE_NAME, [package name])
AC_DEFINE(VERSION, AC_PACKAGE_VERSION, [package version])
AC_DEFINE([GETTEXT_PACKAGE], ["caja-gksu"], [gettext domain])
GETTEXT_PACKAGE=caja-gksu
AC_SUBST(GETTEXT_PACKAGE)

# Checks for programs.
AC_PROG_CC
AC_PROG_INSTALL
AC_PROG_LIBTOOL

ALL_LINGUAS="ar ca cs da de es fr gl hu it ja ko lt pl pt pt_BR ro ru nb nl sk sv xh th zh_CN"

IT_PROG_INTLTOOL
AM_GLIB_GNU_GETTEXT

##################################################
# Check for gtk-doc.
##################################################

AC_ARG_WITH(html-dir, [  --with-html-dir=PATH path to installed docs ])

if test "x$with_html_dir" = "x" ; then
  HTML_DIR='${datadir}/gtk-doc/html'
else
  HTML_DIR=$with_html_dir
fi

AC_SUBST(HTML_DIR)

PKG_CHECK_MODULES(GKSU, [libgksu2 >= 2.0.8, gtk+-2.0 >= 2.4.0])

gtk_doc_min_version=1.0
AC_MSG_CHECKING([gtk-doc version >= $gtk_doc_min_version])
if pkg-config --atleast-version=$gtk_doc_min_version gtk-doc; then
  AC_MSG_RESULT(yes)
  GTKDOC=true
else
  AC_MSG_RESULT(no)
  GTKDOC=false
fi

dnl Let people disable the gtk-doc stuff.
AC_ARG_ENABLE(gtk-doc, [  --enable-gtk-doc  Use gtk-doc to build documentation [default=yes]], enable_gtk_doc="$enableval", enable_gtk_doc=yes)

AM_CONDITIONAL(ENABLE_GTK_DOC, test x$enable_gtk_doc = xyes)
AM_CONDITIONAL(GTK_DOC_USE_LIBTOOL, test x$use_libtool = xyes)
# end of gtk-doc check

AC_ARG_ENABLE(caja-extension, [  --enable-caja-extension  Build the caja extensions module [default=yes]], enable_caja_extension="$enableval", enable_caja_extension=yes)
AM_CONDITIONAL(ENABLE_CAJA_EXTENSION, test x$enable_caja_extension = xyes)

if test x$enable_caja_extension = xyes; then
   PKG_CHECK_MODULES(CAJA, [libgksu2 >= 2.0.0, libcaja-extension])
fi

AC_CONFIG_FILES([
	Makefile
	po/Makefile.in
	caja-gksu/Makefile
	])
AC_OUTPUT
