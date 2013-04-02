#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ(2.57)

AC_INIT(caja-gksu, 1.5.0, http://www.mate-desktop.org/)
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

IT_PROG_INTLTOOL
AM_GLIB_GNU_GETTEXT

PKG_CHECK_MODULES(CAJA, [libcaja-extension])

AC_CONFIG_FILES([
	Makefile
	po/Makefile.in
	caja-gksu/Makefile
	])
AC_OUTPUT
