SUBDIRS = src

# See: https://fedoraproject.org/wiki/User:Johannbg/QA/Systemd/Daemon#Installing_Systemd_Service_Files
# See: http://www.gnu.org/software/automake/manual/html_node/Scripts.html
EXTRA_DIST = glue-bootstrap.service.in
DISTCHECK_CONFIGURE_FLAGS = \
	--with-systemdsystemunitdir=$$dc_install_base/$(systemdsystemunitdir)

if HAVE_SYSTEMD
systemdsystemunit_DATA = glue-bootstrap.service
CLEANFILES = $(systemdsystemunit_DATA)
endif

glue-bootstrap.service: glue-bootstrap.service.in Makefile
	sed -e 's,[@]sbindir[@],$(sbindir),g' $(srcdir)/glue-bootstrap.service.in > glue-bootstrap.service
