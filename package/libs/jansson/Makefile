#
# Copyright (C) 2011-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=jansson
PKG_VERSION:=2.14.1
PKG_RELEASE:=0

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/akheron/$(PKG_NAME)/releases/download/v$(PKG_VERSION)
PKG_HASH:=2521cd51a9641d7a4e457f7215a4cd5bb176f690bc11715ddeec483e85d9e2b3

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE
PKG_CPE_ID:=cpe:/a:jansson_project:jansson

PKG_BUILD_FLAGS:=lto

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

CMAKE_INSTALL:=1
CMAKE_OPTIONS += \
	-DJANSSON_BUILD_DOCS:BOOL=OFF \
	-DJANSSON_BUILD_SHARED_LIBS:BOOL=ON \
	-DJANSSON_EXAMPLES:BOOL=OFF \
	-DJANSSON_WITHOUT_TESTS:BOOL=ON

define Package/jansson
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Jansson library
  URL:=http://www.digip.org/jansson/
  ABI_VERSION:=4
endef

define Package/jansson/description
  Jansson is a C library for encoding, decoding and manipulating JSON data
endef

define Package/jansson/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libjansson*so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,jansson))
