# License: BSD-2-Clause
# (c) 2016-2018 Dridi Boukelmoune <dridi.boukelmoune@gmail.com>

ACLOCAL_AMFLAGS = -I m4

DISTCHECK_CONFIGURE_FLAGS = --disable-docs

EXTRA_DIST = \
	$(PACKAGE).spec

dist_doc_DATA = \
	LICENSE \
	README

SUBDIRS = \
	gen \
	inc \
	lib \
	man \
	tst

dist: all

fuzz-recursive: all

include gcov.am
include lcov.am
