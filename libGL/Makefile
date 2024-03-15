# Port Metadata
PORTNAME =          libGL
PORTVERSION =       1.0.0

MAINTAINER =        Luke Benstead <kazade@gmail.com>
LICENSE =           2-clause BSD (see LICENSE in the source distribution)
SHORT_DESC =        GLdc, an OpenGL (tm) like graphics library for KOS

# No dependencies beyond the base system.
DEPENDENCIES =

# What files we need to download, and where from.
GIT_REPOSITORIES =  git://git.code.sf.net/p/cadcdev/libgl \
                    https://github.com/KallistiOS/libkgl.git

TARGET =            libGL.a
INSTALLED_HDRS =    include/GL/gl.h include/GL/glext.h include/GL/glkos.h include/GL/glu.h
HDR_COMDIR =        GL

# KOS Distributed extras (to be copied into the build tree)
KOS_DISTFILES =     KOSMakefile.mk

include ${KOS_PORTS}/scripts/kos-ports.mk
