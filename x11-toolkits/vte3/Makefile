# Created by: Joe Marcus Clarke <marcus@FreeBSD.org>
# $FreeBSD$

PORTNAME=	vte
PORTVERSION=	0.48.2
CATEGORIES=	x11-toolkits gnome
MASTER_SITES=	GNOME
PKGNAMESUFFIX=	3
DIST_SUBDIR=	gnome3

MAINTAINER=	gnome@FreeBSD.org
COMMENT=	Terminal widget with improved accessibility and I18N support

LICENSE=	LGPL21

BUILD_DEPENDS= vapigen:lang/vala \
		bash:shells/bash \
		gperf:devel/gperf
LIB_DEPENDS=	libgnutls.so:security/gnutls \
		libpcre2-8.so:devel/pcre2

PORTSCOUT=	limitw:1,even

USES=		bison compiler:c++0x gettext gmake gnome libtool localbase \
		pathfix pkgconfig tar:xz
USE_LDCONFIG=	yes
GNU_CONFIGURE=	yes
USE_GNOME=	cairo gdkpixbuf2 gtk30 intltool referencehack \
		introspection:build
CONFIGURE_ARGS=	--enable-introspection \
		--disable-static \
		--disable-Bsymbolic
INSTALL_TARGET=	install-strip

PLIST_SUB=	VERSION=2.91

post-patch:
	@${REINPLACE_CMD} -e 's|-Wno-unused-but-set-variable||g' \
		${WRKSRC}/src/Makefile.in

.include <bsd.port.mk>
