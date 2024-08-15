# Port Metadata
PORTNAME =          libADX
PORTVERSION =       1.0.0

MAINTAINER =        SiZiOUS <sizious@gmail.com>
LICENSE =           BSD 2-Clause License
SHORT_DESC =        A library for decoding ADX audio files.

KOS_MAKEFILE =      Makefile

# What files we need to download, and where from.
GIT_REPOSITORY =    https://github.com/sega-dreamcast/libADX.git
TARGET =            libADX.a
INSTALLED_HDRS =    libadx.h snddrv.h
HDR_INSTDIR =       adx

# Add a pre-install target to get the built library where we expect it.
PREINSTALL = libadx_preinstall

include ${KOS_PORTS}/scripts/kos-ports.mk

libadx_preinstall:
	-rm -rf $(KOS_BASE)/addons/include/$(HDR_INSTDIR)
	mv $(KOS_BASE)/addons/lib/$(KOS_ARCH)/$(TARGET) build/${PORTNAME}-${PORTVERSION}			
	cp build/${PORTNAME}-${PORTVERSION}/src/*.h build/${PORTNAME}-${PORTVERSION}
