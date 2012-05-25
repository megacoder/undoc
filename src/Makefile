TARGETS=all check clean clobber distclean install uninstall
TARGET=all

PREFIX=${DESTDIR}/opt
BINDIR=${PREFIX}/bin
SUBDIRS=

INSTALL=install

.PHONY: ${TARGETS} ${SUBDIRS}

all::	undoc

${TARGETS}::

clobber distclean:: clean

check::	undoc
	./undoc ${ARGS}

install:: undoc
	${INSTALL} -D undoc ${BINDIR}/undoc

uninstall::
	${RM} ${BINDIR}/undoc

ifneq	(,${SUBDIRS})
${TARGETS}::
	${MAKE} TARGET=$@ ${SUBDIRS}
${SUBDIRS}::
	${MAKE} -C $@ ${TARGET}
endif
