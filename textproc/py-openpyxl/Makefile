# $NetBSD: Makefile,v 1.10 2018/05/02 10:53:26 markd Exp $

DISTNAME=	openpyxl-2.5.3
PKGNAME=	${PYPKGPREFIX}-${DISTNAME}
PKGREVISION=	1
CATEGORIES=	textproc python
MASTER_SITES=	${MASTER_SITE_PYPI:=o/openpyxl/}

MAINTAINER=	kamelderouiche@yahoo.com
HOMEPAGE=	http://openpyxl.readthedocs.io/
COMMENT=	Python library to read/write Excel 2007 xlsx/xlsm files
LICENSE=	mit

DEPENDS+=	${PYPKGPREFIX}-cElementTree-[0-9]*:../../textproc/py-cElementTree
DEPENDS+=	${PYPKGPREFIX}-jdcal-[0-9]*:../../time/py-jdcal
DEPENDS+=	${PYPKGPREFIX}-lxml-[0-9]*:../../textproc/py-lxml

USE_LANGUAGES=	# none

SUBST_CLASSES+=		requires
SUBST_STAGE.requires=	post-install
SUBST_FILES.requires=	${DESTDIR}${PREFIX}/${PYSITELIB}/${EGG_INFODIR}/requires.txt
SUBST_SED.requires=	-e '/et_xmlfile/d'

post-extract:
	${RM} ${WRKSRC}/openpyxl.egg-info/.DS_Store

.include "../../lang/python/egg.mk"
.include "../../mk/bsd.pkg.mk"
