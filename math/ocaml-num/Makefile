# $NetBSD: Makefile,v 1.2 2018/04/13 13:55:34 jaapb Exp $

GITHUB_PROJECT=	num
GITHUB_TAG=	v${PKGVERSION_NOREV}
DISTNAME=	${GITHUB_PROJECT}-1.1
PKGNAME= 	ocaml-${DISTNAME}
PKGREVISION= 	1
CATEGORIES=	math
MASTER_SITES=	${MASTER_SITE_GITHUB:=ocaml/}

MAINTAINER=	jaapb@NetBSD.org
HOMEPAGE=	https://github.com/ocaml/num/
COMMENT=	Library for arbitrary-precision arithmetic
LICENSE=	gnu-lgpl-v2.1

USE_LANGUAGES=	# none
USE_TOOLS+=	gmake

BUILD_TARGET=	all
INSTALLATION_DIRS+=	lib/ocaml/stublibs

OCAML_USE_FINDLIB=	yes
OCAML_FINDLIB_DIRS+=	num-top

.include "../../mk/ocaml.mk"
.include "../../mk/bsd.pkg.mk"
