#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#

#
# Copyright (c) 2011, 2012, Oracle and/or its affiliates. All rights reserved.
#

BUILD_BITS=			64
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		pwgen
COMPONENT_VERSION=	2.08
COMPONENT_PROJECT_URL=	https://sourceforge.net/projects/pwgen/
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	\
	sha256:dab03dd30ad5a58e578c5581241a6e87e184a18eb2c3b2e0fffa8a9cf105c97b
COMPONENT_ARCHIVE_URL=	$(COMPONENT_PROJECT_URL)files/pwgen/$(COMPONENT_VERSION)/$(COMPONENT_ARCHIVE)	
COMPONENT_BUGDB=	utility/pwgen

TEST_TARGET=		$(NO_TESTS)
include $(WS_MAKE_RULES)/common.mk

# IPS Package versions contain sequences of non-negative (for now) integers,
# separated by dots.  Leading zeroes are not allowed, due to ordering
# ambiguity, so IPS team has to massage "06" into "6" and thus IPS version
# of pwgen is actually 2.6 and not 2.06.  IPS_COMPONENT_VERSION is by default
# set to $(COMPONENT_VERSION) but in this case it has to be set specifically
# to "2.6" to comply with the convention described above.
#
IPS_COMPONENT_VERSION=	2.8

# configure in pwgen is generated by autoconf 2.13, which does not accept the
# variables like CC, CXX, etc.  The solution is to generate a new configure
# using modern autoconf available on the build system (version 2.63 in the
# time of creating this makefile).
#
COMPONENT_PREP_ACTION=	(cd $(@D) ; autoconf) 

# This is to get rid of gcc specific -Wxxx options in pwgen makefile
#
COMPONENT_BUILD_ARGS = WALL_OPTS=

# Auto-generated dependencies
REQUIRED_PACKAGES += system/library
