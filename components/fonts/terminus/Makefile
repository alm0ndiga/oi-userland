#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"), version 1.0.
# You may only use this file in accordance with the terms of version
# 1.0 of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source.  A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2016 Josef 'Jeff' Sipek <jeffpc@josefsipek.net>
# Copyright 2019 Michal Nowak
#
BUILD_BITS=			32
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		terminus-font
COMPONENT_VERSION=	4.48
COMPONENT_PROJECT_URL=	https://terminus-font.sourceforge.net/
COMPONENT_SUMMARY=	Terminus Font
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=      $(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= \
	sha256:34799c8dd5cec7db8016b4a615820dfb43b395575afbb24fc17ee19c869c94af
COMPONENT_ARCHIVE_URL=	http://sourceforge.net/projects/terminus-font/files/$(COMPONENT_SRC)/$(COMPONENT_ARCHIVE)/download
COMPONENT_FMRI=		system/font/terminus
COMPONENT_LICENSE_FILE=	terminus.license
COMPONENT_LICENSE=	OFL
COMPONENT_CLASSIFICATION=	System/Fonts

CONFIGURE_DEFAULT_DIRS=	no

TEST_TARGET=		$(NO_TESTS)
include $(WS_MAKE_RULES)/common.mk

CONFIGURE_OPTIONS =  --prefix=$(CONFIGURE_PREFIX)
CONFIGURE_OPTIONS += --x11dir=$(CONFIGURE_PREFIX)/share/fonts/X11/terminus

COMPONENT_BUILD_TARGETS = pcf
COMPONENT_INSTALL_TARGETS = install-pcf

COMPONENT_PRE_CONFIGURE_ACTION=$(CLONEY) $(SOURCE_DIR) $(@D)

# Build dependencies
REQUIRED_PACKAGES+= x11/bdftopcf
