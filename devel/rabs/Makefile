PORTNAME=	rabs
DISTVERSIONPREFIX=	v
DISTVERSION=	2.30.7
CATEGORIES=	devel

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Generic imperative build system
WWW=		https://github.com/wrapl/rabs

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

ONLY_FOR_ARCHS=		amd64 i386
ONLY_FOR_ARCHS_REASON=	invokes x86 assembly: Error: unrecognized opcode: 'int3'

LIB_DEPENDS=	libgc-threaded.so:devel/boehm-gc-threaded

USES=		compiler:c11 gmake localbase:ldflags
USE_GITHUB=	yes
GH_ACCOUNT=	wrapl
GH_TUPLE=	wrapl:minilang:3723bd4:wrapl_minilang/minilang \
		rajamukherji:radb:c245a08:rajamukherji_radb/radb

MAKE_ARGS=	PREFIX=${PREFIX}
BINARY_ALIAS=	make=${GMAKE}

PLIST_FILES=	bin/rabs

post-install:
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/rabs

.include <bsd.port.mk>
