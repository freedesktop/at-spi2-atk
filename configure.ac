
AC_INIT([at-spi2-atk], [0.1.0], [accessibility-atspi@lists.linux-foundation.org])
AC_CONFIG_AUX_DIR(config)

AT_SPI_ATK_MAJOR_VERSION=0
AT_SPI_ATK_MINOR_VERSION=1
AT_SPI_ATK_INTERFACE_AGE=0
AT_SPI_ATK_BINARY_AGE=0
AT_SPI_ATK_VERSION="$AT_SPI_MAJOR_VERSION.$AT_SPI_MINOR_VERSION"
AC_SUBST(AT_SPI_ATK_VERSION)

# libtool versioning
LT_RELEASE=$AT_SPI_MAJOR_VERSION.$AT_SPI_MINOR_VERSION
LT_CURRENT=0
LT_REVISION=0
LT_AGE=0
LT_VERSION_INFO='-version-info ${LT_CURRENT}:${LT_REVISION}:${LT_AGE}'
AC_SUBST(LT_VERSION_INFO)
AC_SUBST(LT_RELEASE)
AC_SUBST(LT_CURRENT)
AC_SUBST(LT_REVISION)
AC_SUBST(LT_AGE)

AM_INIT_AUTOMAKE([-Wall foreign])

AC_PROG_CC
AM_PATH_PYTHON(2.4)
AM_DISABLE_STATIC
AM_PROG_LIBTOOL
PKG_PROG_PKG_CONFIG

AC_CONFIG_HEADERS([config.h])

PKG_CHECK_MODULES(DBUS, [dbus-1 >= 1.0])
AC_SUBST(DBUS_LIBS)
AC_SUBST(DBUS_CFLAGS)

PKG_CHECK_MODULES(DROUTE, [droute-0.1 >= 0.1])
AC_SUBST(DROUTE_LIBS)
AC_SUBST(DROUTE_CFLAGS)

PKG_CHECK_MODULES(DBIND, [dbind-0.1 >= 0.1])
AC_SUBST(DBIND_LIBS)
AC_SUBST(DBIND_CFLAGS)

PKG_CHECK_MODULES(GLIB, [glib-2.0])
AC_SUBST(GLIB_LIBS)
AC_SUBST(GLIB_CFLAGS)

PKG_CHECK_MODULES(DBUS_GLIB, [dbus-glib-1 >= 0.7.0])
AC_SUBST(DBUS_GLIB_LIBS)
AC_SUBST(DBUS_GLIB_CFLAGS)

PKG_CHECK_MODULES(GOBJ, [gobject-2.0 >= 2.0.0])
AC_SUBST(GOBJ_LIBS)
AC_SUBST(GOBJ_CFLAGS)

PKG_CHECK_MODULES(GMODULE, [gmodule-2.0 >= 2.0.0])	
AC_SUBST(GMODULE_LIBS)
AC_SUBST(GMODULE_CFLAGS)

PKG_CHECK_MODULES(LIB_XML, [libxml-2.0 >= 2.0.0])
AC_SUBST(LIB_XML_LIBS)
AC_SUBST(LIB_XML_CFLAGS)

PKG_CHECK_MODULES(ATK, [atk >= 1.17.0])
AC_SUBST(ATK_LIBS)
AC_SUBST(ATK_CFLAGS)

PKG_CHECK_MODULES(GTK, [gtk+-2.0 >= 2.10.0])
AC_SUBST(GTK_LIBS)
AC_SUBST(GTK_CFLAGS)

AC_PATH_XTRA

AC_ARG_VAR([DEFAULT_ATSPI_INTROSPECTION_PATH],
	   [Set the default path for the install ofDBus introspection XML
	    relative to the pkgdatadir.])
if test -z "$DEFAULT_ATSPI_INTROSPECTION_PATH"; then
	  DEFAULT_ATSPI_INTROSPECTION_PATH=dbus
fi

AC_ARG_VAR([GTK_MODULE_DIR],
	   [Where to place the atk-adaptor gtk module])
if test -z "$GTK_MODULE_DIR"; then
	  GTK_MODULE_DIR=gtk-2.0/modules
fi

#libtool option to strip symbols starting with cspi
LIBTOOL_EXPORT_OPTIONS='-export-symbols-regex "^[[^cspi]].*"'
AC_SUBST(LIBTOOL_EXPORT_OPTIONS)

AC_CONFIG_FILES([Makefile
		 pkgconfig/cspi-1.0.pc
		 pkgconfig/cspi-1.0-uninstalled.pc
		 tests/Makefile
		 common/Makefile
		 atk-adaptor/Makefile
		 tests/dummyatk/Makefile
		 tests/data/Makefile
		 tests/pyatspi/Makefile
		 tests/pyatspi/pasytest/Makefile
		 tests/apps/Makefile
		 tests/cspi/Makefile
		 cspi/Makefile
		 pyatspi/Makefile
		])

AC_OUTPUT
