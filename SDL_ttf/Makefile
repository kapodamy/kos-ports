# Port Metadata
PORTNAME =          SDL_ttf
PORTVERSION =       1.2

MAINTAINER =        Donald Haase
LICENSE =           zlib License - http://opensource.org/licenses/Zlib
SHORT_DESC =        SDL TrueType font library

# This port uses the autotools scripts that are included with the distfiles.
PORT_AUTOTOOLS =    1

# Don't attempt to copy the target library, it will be in the inst dir already.
NOCOPY_TARGET =     1

# No dependencies beyond the base system.
DEPENDENCIES =      SDL libbz2 zlib libpng freetype

# What files we need to download, and where from.
GIT_REPOSITORY =    https://github.com/libsdl-org/SDL_ttf.git
GIT_BRANCH =        SDL-1.2

TARGET =            libSDL_ttf.a
#There's a problem here. Standard SDL_ttf will install SDL_ttf.h into the SDL folder. 
#There's no option in the build scripts to copy into a different ports inst/include so 
# instead I'm abusing the fact that INSTALLED_HDRS and HDR_DIRECTORY aren't mutually exclusive.
INSTALLED_HDRS =        SDL_ttf.h
HDR_DIRECTORY =         ../../../include/SDL
HDR_INSTDIR =           SDL


# Autotools setup work.
CONFIGURE_ARGS =    
CONFIGURE_DEFS =    SDL_CFLAGS=-I${KOS_PORTS}/include/SDL SDL_LIBS=-lSDL \
                    FT2_CFLAGS="-I${KOS_PORTS}/include/zlib -I${KOS_PORTS}/include/bzlib \
                    -I${KOS_PORTS}/include/png -I${KOS_PORTS}/include/freetype2" \
                    FT2_LIBS="-lfreetype -lz -lbz2 -lpng -lm"
MAKE_TARGET =       all install


include ${KOS_PORTS}/scripts/kos-ports.mk
