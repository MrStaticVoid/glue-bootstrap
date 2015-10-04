AC_INIT([glue-bootstrap], [1])
AC_CONFIG_SRCDIR([src/glue-bootstrap])
AM_INIT_AUTOMAKE

# See: https://fedoraproject.org/wiki/User:Johannbg/QA/Systemd/Daemon#Installing_Systemd_Service_Files
PKG_PROG_PKG_CONFIG
AC_ARG_WITH([systemdsystemunitdir],
	AS_HELP_STRING([--with-systemdsystemunitdir=DIR], [Directory for systemd service files]),
	[], [with_systemdsystemunitdir=$($PKG_CONFIG --variable=systemdsystemunitdir systemd)])
AC_SUBST([systemdsystemunitdir], [$with_systemdsystemunitdir])
AM_CONDITIONAL(HAVE_SYSTEMD, [test -n "$with_systemdsystemunitdir"])

AC_OUTPUT(Makefile src/Makefile)
