SUBDIRS = po src data help

# Temporary fix for JHBuild, see https://bugzilla.gnome.org/show_bug.cgi?id=641652
ACLOCAL_AMFLAGS = ${ACLOCAL_FLAGS}

DISTCLEANFILES = \
	Makefile.in \
	aclocal.m4 \
	config.h.in \
	configure \
	depcomp \
	install-sh \
	missing \
	mkinstalldirs \
	omf.make \
	xmldocs.make

EXTRA_DIST = \
	autogen.sh

dist-hook:
	@if test -d "$(srcdir)/.git"; \
	then \
		echo Creating ChangeLog && \
		( cd "$(top_srcdir)" && \
		  echo '# Generated by Makefile. Do not edit.'; echo; \
		  $(top_srcdir)/missing --run git log --stat ) > ChangeLog.tmp \
		&& mv -f ChangeLog.tmp $(distdir)/ChangeLog \
		|| ( rm -f ChangeLog.tmp ; \
		     echo Failed to generate ChangeLog >&2 ); \
	else \
		echo A git clone is required to generate a ChangeLog >&2; \
	fi
