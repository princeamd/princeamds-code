ACLOCAL_AMFLAGS = -I m4
MAINTAINERCLEANFILES = Makefile.in aclocal.m4 config.guess config.h.in \
		       config.sub configure depcomp install-sh ltmain.sh \
		       missing module.desktop config.rpath mkinstalldirs

SUBDIRS = src data

if HAVE_PO

SUBDIRS += po

endif

EDJE_FLAGS = -v \
	   -id $(top_srcdir)/images \
	   -fd $(top_srcdir)/fonts

# data files for the module
filesdir =  $(datadir)

files_DATA = module.desktop \
	     e-module-remote.edj

EXTRA_DIST = $(files_DATA) \
	     images/module_icon.png \
	     e-module-remote.edc \
	     fonts/VeraBd.ttf

e-module-remote.edj: Makefile e-module-remote.edc images/module_icon.png

%.edj:  %.edc
	$(EDJE_CC) $(EDJE_FLAGS) $< $@

clean-local:
	 rm -rf *.edj module.desktop *~
uninstall:
	 rm -rf $(DESTDIR)$(datadir)

