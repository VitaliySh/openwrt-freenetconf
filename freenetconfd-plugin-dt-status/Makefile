#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=freenetconfd-plugin-dt-status
PKG_VERSION:=2015-12-13
PKG_RELEASE=$(PKG_SOURCE_VERSION)

PKG_LICENSE:=Apache-2.0
PKG_MAINTAINER:=Mislav Novakovic <mislav.novakovic@sartura.hr>

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/freenetconf/freenetconfd-plugin-dt-status.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=f5dde60052fd4516991e8ed41fad6ab41b29c927
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/freenetconfd-plugin-dt-status
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=freenetconfd firmware uprade plugin
  URL:=https://github.com/freenetconf/freenetconfd-plugin-dt-status
  DEPENDS:=+freenetconfd +libblobmsg-json +uci
endef

define Package/freenetconfd-plugin-dt-status/install
	$(INSTALL_DIR) $(1)/usr/lib/freenetconfd
	$(CP) \
		$(PKG_BUILD_DIR)/lib/*.so \
		$(1)/usr/lib/freenetconfd/

	$(INSTALL_DIR) $(1)/etc/yang
	$(INSTALL_CONF) \
		$(PKG_BUILD_DIR)/yang/*.yang \
		$(1)/etc/yang/
endef

$(eval $(call BuildPackage,freenetconfd-plugin-dt-status))
