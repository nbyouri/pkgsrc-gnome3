# $NetBSD: Makefile,v 1.5 2016/10/19 12:31:25 ryoon Exp $

DISTNAME=	binutils-2.27
PKGNAME=	cross-h8300-elf-${DISTNAME}
CATEGORIES=	cross
MASTER_SITES=	${MASTER_SITE_GNU:=binutils/}
EXTRACT_SUFX=	.tar.bz2

MAINTAINER=	ryoon@NetBSD.org
HOMEPAGE=	# empty
COMMENT=	Cross utility for h8300-elf
LICENSE=	gnu-gpl-v2 AND gnu-gpl-v3 AND gnu-lgpl-v2 AND gnu-lgpl-v3

H8300_PREFIX=	${PREFIX}/cross-h8300-elf

USE_TOOLS+=	gmake makeinfo
GNU_CONFIGURE=	yes

OBJDIR=			../build
CONFIGURE_DIRS=		${OBJDIR}
CONFIGURE_SCRIPT=	${WRKSRC}/configure
GNU_CONFIGURE_PREFIX=	${H8300_PREFIX}

CONFIGURE_ARGS+=	--disable-nls
CONFIGURE_ARGS+=	--target=h8300-elf
INFO_FILES=		yes

pre-configure:
	${RUN} cd ${WRKSRC} && ${MKDIR} ${OBJDIR}
	${CP} ${PKGSRCDIR}/mk/gnu-config/config.guess ${WRKSRC}
	${CP} ${PKGSRCDIR}/mk/gnu-config/config.sub ${WRKSRC}


post-install:
# copy libiberty.a under the different name from compiler
# PATH differs between clang and gcc: (and SunOS 5.11 places at amd64 instead of x86_64)
	for d in amd64/libiberty.a ${MACHINE_ARCH}/libiberty.a libiberty.a; do \
		if [ -f ${DESTDIR}${H8300_PREFIX}/lib/$$d ]; then \
			${MV} ${DESTDIR}${H8300_PREFIX}/lib/$$d \
			      ${DESTDIR}${H8300_PREFIX}/lib/libiberty_binutils.a; \
		break; \
		fi; \
	done

.include "../../mk/bsd.pkg.mk"
