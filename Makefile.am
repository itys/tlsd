AM_CFLAGS = -Wall -Wextra -Werror -pedantic

bin_PROGRAMS = tlsd fp2alias std2fifo

tlsd_SOURCES = tlsd.c
tlsd_CFLAGS = $(LIBGNUTLS_CFLAGS) $(AM_CFLAGS)
tlsd_LDADD = $(LIBGNUTLS_LIBS)

fp2alias_SOURCES = fp2alias.c
fp2alias_CFLAGS = $(AM_CFLAGS)

std2fifo_SOURCES = std2fifo.c
std2fifo_CFLAGS = $(AM_CFLAGS)

# tests

TESTS = tests/authenticate.sh

TESTS_ENVIRONMENT = \
	builddir="$(builddir)" \
	testdir="$(top_srcdir)/tests/"

EXTRA_DIST = $(TESTS) \
	tests/wait-for-initialization.sed \
	tests/test-key-1.pem \
	tests/test-cert-1.pem \
	tests/test-key-2.pem \
	tests/test-cert-2.pem

# docs
info_TEXINFOS = tlsd.texi
dist_man_MANS = tlsd.1 fp2alias.1 std2fifo.1
EXTRA_DIST += examples
