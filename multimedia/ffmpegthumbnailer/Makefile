# $NetBSD: Makefile,v 1.23 2018/04/28 19:28:20 wiz Exp $

DISTNAME=	ffmpegthumbnailer-2.2.0
CATEGORIES=	multimedia
MASTER_SITES=	${MASTER_SITE_GITHUB:=dirkvdb/}
GITHUB_RELEASE=	${PKGVERSION_NOREV}
EXTRACT_SUFX=	.tar.bz2
EXTRACT_USING=	bsdtar

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://github.com/dirkvdb/ffmpegthumbnailer
COMMENT=	Lightweight video thumbnailer that can be used by file managers
LICENSE=	gnu-gpl-v2

USE_CMAKE=	yes
USE_LANGUAGES=	c c++
USE_LIBTOOL=	yes
USE_TOOLS+=	pkg-config

PKGCONFIG_OVERRIDE+=	libffmpegthumbnailer.pc.in

CMAKE_ARG_PATH=	..
CMAKE_ARGS+=	-DCMAKE_BUILD_TYPE=Release
CMAKE_ARGS+=	-DENABLE_GIO=ON
CMAKE_ARGS+=	-DENABLE_THUMBNAILER=ON
CONFIGURE_DIRS=	build

pre-configure:
	${MKDIR} ${WRKSRC}/build

.include "../../mk/jpeg.buildlink3.mk"
.include "../../graphics/png/buildlink3.mk"
.include "../../multimedia/ffmpeg3/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
