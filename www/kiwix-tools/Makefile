PORTNAME=	kiwix-tools
DISTVERSION=	3.7.0
CATEGORIES=	www

MAINTAINER=	olce.freebsd.ports@certner.fr
COMMENT=	Command-line Kiwix tools
WWW=		https://www.kiwix.org/

LICENSE=	GPLv3+
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libkiwix.so:devel/libkiwix \
		libzim.so:devel/libzim

USES=		compiler:c++17-lang meson pkgconfig
USE_GITHUB=	yes
GH_ACCOUNT=	kiwix
USE_RC_SUBR=	kiwix_serve

CXXFLAGS_gcc=	-Wno-error=maybe-uninitialized
CXXFLAGS+=	${CXXFLAGS_${CHOSEN_COMPILER_TYPE}}

post-install:
	${MKDIR} ${STAGEDIR}${PREFIX}/share/kiwix
	${INSTALL_DATA} files/library.xml ${STAGEDIR}${PREFIX}/share/kiwix

.include <bsd.port.mk>
