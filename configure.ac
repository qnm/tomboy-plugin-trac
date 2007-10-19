AC_INIT(README)
AC_CANONICAL_SYSTEM

AM_INIT_AUTOMAKE(tomboy-plugin-trac, 0.0.1)

AM_MAINTAINER_MODE

AC_PATH_PROG(MONO, mono, no)
if test "x$MONO" = "xno"; then
	AC_MSG_ERROR([Cannot find "mono" runtime in your PATH])
fi

AC_PATH_PROG(MCS, gmcs, no)
if test "x$MCS" = "xno"; then
	AC_MSG_ERROR([Cannot find "mcs" compiler in your PATH])
fi

PKG_CHECK_MODULES(TOMBOY, tomboy-plugins)
AC_SUBST(TOMBOY_LIBS)

PLUGINDIR=`$PKG_CONFIG --variable=pluginsdir tomboy-plugins`
AC_SUBST(PLUGINDIR)

AC_OUTPUT([
	Makefile
	src/Makefile
])
