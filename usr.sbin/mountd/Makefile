PROG=	mountd
SRCS=	mountd.c getmntopts.c
MAN=	exports.5 netgroup.5 mountd.8

MOUNT=  ${SRCTOP}/sbin/mount
CFLAGS+= -I${MOUNT}
WARNS?= 2

.PATH: ${MOUNT}

LIBADD=	util

.include <bsd.prog.mk>
