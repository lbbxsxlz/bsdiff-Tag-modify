CFLAGS		+=	-O3 -lbz2

PREFIX		?=	/usr/local
INSTALL_PROGRAM	?=	${INSTALL} -c -s -m 555
INSTALL_MAN	?=	${INSTALL} -c -m 444

all:		bsdiff bspatch
bsdiff:		bsdiff.c
	cc bsdiff.c -O3 -lbz2 -o bsdiff
bspatch:	bspatch.c
	cc bspatch.c -O3 -lbz2 -o bspatch

clean:
	rm bsdiff bspatch -f

install:
	${INSTALL_PROGRAM} bsdiff bspatch ${PREFIX}/bin
	.ifndef WITHOUT_MAN
	${INSTALL_MAN} bsdiff.1 bspatch.1 ${PREFIX}/man/man1
	.endif
