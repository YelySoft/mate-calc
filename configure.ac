dnl Process this file with autoconf to produce a configure script.
AC_PREREQ(2.62)
AC_INIT([mate-calc], [1.17.0], [http://mate-desktop.org])

AM_INIT_AUTOMAKE([1.9 foreign no-dist-gzip dist-xz check-news])
AC_CONFIG_HEADERS(config.h)
AM_MAINTAINER_MODE
MATE_MAINTAINER_MODE_DEFINES
m4_ifdef([AM_SILENT_RULES],[AM_SILENT_RULES([yes])])

AC_ISC_POSIX
AC_PROG_CC
AC_HEADER_STDC

GLIB_GSETTINGS
MATE_COMPILE_WARNINGS(maximum)

dnl ###########################################################################
dnl Dependencies
dnl ###########################################################################

GLIB_REQUIRED=2.31
GIO_REQUIRED=2.25.10

GTK_REQUIRED=3.0

PKG_CHECK_MODULES(MATE_CALC, [
    gtk+-3.0 >= $GTK_REQUIRED
    glib-2.0 >= $GLIB_REQUIRED
    gio-2.0 >= $GIO_REQUIRED
    libxml-2.0
    gmodule-export-2.0
])

PKG_CHECK_MODULES(MATE_CALC_CMD, [
    glib-2.0 >= $GLIB_REQUIRED
    gio-2.0 >= $GIO_REQUIRED
    libxml-2.0
])

GLIB_MKENUMS=`$PKG_CONFIG --variable=glib_mkenums glib-2.0`
AC_SUBST(GLIB_MKENUMS)

AC_CHECK_LIB(m, log)

dnl ###########################################################################
dnl Internationalization
dnl ###########################################################################

IT_PROG_INTLTOOL([0.35.0])
AC_SUBST(GETTEXT_PACKAGE, mate-calc)

dnl ###########################################################################
dnl Documentation
dnl ###########################################################################

YELP_HELP_INIT

dnl ###########################################################################
dnl Files to generate
dnl ###########################################################################

AC_OUTPUT([
Makefile
src/Makefile
po/Makefile.in
data/Makefile
help/Makefile
])
