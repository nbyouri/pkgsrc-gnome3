# $NetBSD: Makefile,v 1.9 2018/04/29 21:32:00 adam Exp $

DISTNAME=	megatools-1.9.95
PKGREVISION=	7
CATEGORIES=	filesystems security
MASTER_SITES=	https://megatools.megous.com/builds/

MAINTAINER=	root@zta.lk
HOMEPAGE=	https://megatools.megous.com/
COMMENT=	Command line client for Mega.co.nz
LICENSE=	gnu-gpl-v2

DEPENDS+=	glib-networking>=2.36.2:../../net/glib-networking

GNU_CONFIGURE=	yes
USE_LIBTOOL=	yes
USE_TOOLS+=	pkg-config gmake

PKGCONFIG_OVERRIDE+=	libmega.pc.in

.include "../../devel/glib2/buildlink3.mk"
.include "../../www/curl/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
