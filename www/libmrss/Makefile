# $NetBSD: Makefile,v 1.12 2018/04/29 21:31:24 adam Exp $
#

DISTNAME=	libmrss-0.19.2
PKGREVISION=	11
CATEGORIES=	www
MASTER_SITES=	http://www.autistici.org/bakunin/libmrss/

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://www.autistici.org/bakunin/libmrss/
COMMENT=	C library for parsing, writing and creating RSS files or streams
LICENSE=	gnu-lgpl-v2.1

GNU_CONFIGURE=	yes
USE_LIBTOOL=	yes
USE_TOOLS+=	pkg-config
USE_LANGUAGES=	c c++

PKGCONFIG_OVERRIDE+=	mrss.pc.in

.include "../../textproc/libnxml/buildlink3.mk"
.include "../../www/curl/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
