# $NetBSD: Makefile,v 1.10 2018/03/08 08:51:05 adam Exp $

DISTNAME=	sassc-3.5.0
CATEGORIES=	www devel
MASTER_SITES=	${MASTER_SITE_GITHUB:=sass/}

MAINTAINER=	adam@NetBSD.org
HOMEPAGE=	http://sass-lang.com/libsass/
COMMENT=	Wrapper around libsass
LICENSE=	mit

USE_LANGUAGES=		c c++
USE_LIBTOOL=		yes
USE_TOOLS+=		aclocal autoheader autoconf automake gmake
GNU_CONFIGURE=		yes
MAKE_FILE=		GNUmakefile

pre-configure:
	set -e; cd ${WRKSRC}; libtoolize -c -f; \
	aclocal; autoheader; automake -a --foreign -i; autoconf

.include "../../www/libsass/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
