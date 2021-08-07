CROSS ?=
CFLAGS		+=	-O3 -lbz2
CC = $(CROSS)gcc
PREFIX		?=	/usr/local
INSTALL_PROGRAM	?=	${INSTALL} -c -s -m 555
INSTALL_MAN	?=	${INSTALL} -c -m 444

all:		bsdiff bspatch
bsdiff:		bsdiff.c
	gcc bsdiff.c -O3 -lbz2 -DBSDIFF_EXECUTABLE -o bsdiff
bspatch:	bspatch.c
ifeq ($(CROSS),)
	gcc bspatch.c -O3 -lbz2 -DBSPATCH_EXECUTABLE -o bspatch
else
	$(CC) bspatch-1.c -O3 -DBSPATCH_EXECUTABLE -I . -L . lib/$(CROSS)/libbz2.a -o bspatch-1
	mkdir -p bin/$(CROSS)
	mv bspatch-1  bin/$(CROSS)/bspatch
endif
clean:
	rm bsdiff bspatch -f

install:
	${INSTALL_PROGRAM} bsdiff bspatch ${PREFIX}/bin
	.ifndef WITHOUT_MAN
	${INSTALL_MAN} bsdiff.1 bspatch.1 ${PREFIX}/man/man1
	.endif
