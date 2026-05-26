#
# Copyright (C) 2016-2017 LEDE project
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libressl
PKG_VERSION:=4.3.2
PKG_HASH:=edf01aee24c65d69e6a9efcb9d44bcda682ff9d4f3bbbd95e794e1dfa90847b5

PKG_CPE_ID:=cpe:/a:openbsd:libressl

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://mirror.ox.ac.uk/pub/OpenBSD/LibreSSL \
	https://ftp.jaist.ac.jp/pub/OpenBSD/LibreSSL \
	https://ftp.openbsd.org/pub/OpenBSD/LibreSSL

HOST_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/host-build.mk

HOSTCC := $(HOSTCC_NOCACHE)

HOST_CFLAGS += $(HOST_FPIC)

HOST_CONFIGURE_ARGS += \
	--enable-static \
	--disable-shared \
	--disable-asm \
	--with-pic \
	--disable-tests

define Host/Uninstall
	-$(call Host/Compile/Default,uninstall)
endef

$(eval $(call HostBuild))
