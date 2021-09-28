if WANT_JANSSON
JANSSON_INCLUDES= -I$(top_srcdir)/compat/jansson
else
JANSSON_INCLUDES=
endif

ACLOCAL_AMFLAGS = -I m4
EXTRA_DIST	= example-cfg.json nomacro.pl
SUBDIRS		= compat

bin_PROGRAMS	= minerd
minerd_SOURCES	= elist.h miner.h compat.h \
	cpu-miner.c util.c \
	sha2.c sha2-arm.S sha2-x86.S sha2-x64.S \
	scrypt.c scrypt-arm.S scrypt-x86.S scrypt-x64.S \
	blake.c bmw.c groestl.c jh.c keccak.c skein.c \
	aes_helper.c cubehash.c shavite.c simd.c echo.c luffa.c\
	quark.c gost.c Xcoin.c

## Uncomment on MSYS2 Windows build only:
# minerd_LDFLAGS = $(PTHREAD_FLAGS) -Wl,-Bstatic -static-libgcc
# minerd_DEFS    = -DCURL_STATICLIB -DWIN32 -DWIN32_LEAN_AND_MEAN
##

minerd_LDADD    = @LIBCURL@ @JANSSON_LIBS@ @PTHREAD_LIBS@ @WS2_LIBS@
minerd_CPPFLAGS = $(PTHREAD_FLAGS) -fno-strict-aliasing $(JANSSON_INCLUDES) -fPIC @LIBCURL_CPPFLAGS@
