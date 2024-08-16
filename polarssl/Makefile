# Port Metadata
PORTNAME =          polarssl
PORTVERSION =       1.3.9

MAINTAINER =        Damian Parrino <bucanero@users.noreply.github.com>
LICENSE =           GPL2
SHORT_DESC =        A Secure Socket Layer library.

# This port uses the autotools scripts that are included with the distfiles.
PORT_BUILD =        cmake

# What files we need to download, and where from.
DOWNLOAD_SITE  =    https://src.fedoraproject.org/repo/pkgs/polarssl/polarssl-1.3.9-gpl.tgz/48af7d1f0d5de512cbd6dacf5407884c
DOWNLOAD_FILES =    polarssl-1.3.9-gpl.tgz

TARGET =            libpolarssl.a

# This is required because the built-in cmake doesn't support custom install
# of headers. It does support custom installation of the lib itself via
# -DINSTALL_STATIC=ON and -DLIB_INSTALL_DIR=${KOS_PORTS}/${PORTNAME}/inst/lib
# But that forces the attempt to install the headers locally.
HDR_DIRECTORY =     include/polarssl

# If the header installation issue above is fixed then install_static can be changed
# Build_demos is reliant on a built-in library sokol that doesn't have a DC port
CMAKE_ARGS =        -DCMAKE_BUILD_TYPE=Release -DENABLE_TESTING=FALSE -DENABLE_PROGRAMS=FALSE

# Add a pre-build target to adjust the source code
PREBUILD = polarssl_prebuild
polarssl_prebuild:
	sed -i '84s/.*/defined(_arch_dreamcast)/' build/${PORTNAME}-${PORTVERSION}/library/net.c
	sed -i '28s/.*/set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wno-error=incompatible-pointer-types")/' build/${PORTNAME}-${PORTVERSION}/CMakeLists.txt

# Add a pre-install target to get the built library where we expect it.
# This, copied from opus, might be solvable by
# adding an equivalent to HDR_DIRECTORY for lib
PREINSTALL = polarssl_preinstall
polarssl_preinstall:
	cp build/${PORTNAME}-${PORTVERSION}/library/${TARGET} build/${PORTNAME}-${PORTVERSION}

include ${KOS_PORTS}/scripts/kos-ports.mk
