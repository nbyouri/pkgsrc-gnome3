# $NetBSD: Makefile,v 1.52 2018/04/14 07:34:15 adam Exp $

DISTNAME=	apr-util-1.6.1
PKGREVISION=	2
CATEGORIES=	devel
MASTER_SITES=	${MASTER_SITE_APACHE:=apr/}
EXTRACT_SUFX=	.tar.bz2

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	http://apr.apache.org/
COMMENT=	Apache Portable Runtime utilities
LICENSE=	apache-2.0

USE_LIBTOOL=		yes
USE_TOOLS+=		pkg-config
GNU_CONFIGURE=		yes
CONFIGURE_ARGS+=	--with-apr=${BUILDLINK_PREFIX.apr}/bin/apr-1-config
CONFIGURE_ARGS+=	--with-expat=${BUILDLINK_PREFIX.expat}
CONFIGURE_ARGS+=	--without-gdbm
CONFIGURE_ARGS+=	--without-odbc
CONFIGURE_ARGS+=	--without-sqlite2
PKGCONFIG_OVERRIDE+=	apr-util.pc.in

# just a list of exported symbols for a library that also starts with shebang
CHECK_INTERPRETER_SKIP=	lib/aprutil.exp

MAKE_ENV+=	WRAPPER_DIR=${WRAPPER_DIR}

.include "../../mk/bsd.prefs.mk"
.include "options.mk"

.include "../../converters/libiconv/buildlink3.mk"
BUILDLINK_API_DEPENDS.apr+=	apr>=1.5.0
.include "../../devel/apr/buildlink3.mk"
.include "../../textproc/expat/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
