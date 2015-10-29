#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=freenetconfd-plugin-dt-sip
PKG_VERSION:=2015-10-29
PKG_RELEASE=$(PKG_SOURCE_VERSION)

PKG_LICENSE:=Apache-2.0
PKG_MAINTAINER:=Mislav Novakovic <mislav.novakovic@sartura.hr>

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/freenetconf/freenetconfd-plugin-dt-sip.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=8b86edb4a9ddaa9598e6f942c59f85f61e785d8a
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/freenetconfd-plugin-dt-sip
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=freenetconfd dt sip plugin
  URL:=https://github.com/freenetconf/freenetconfd-plugin-dt-sip
  DEPENDS:=+freenetconfd +libblobmsg-json +uci
endef

define Package/freenetconfd-plugin-dt-sip/install
	$(INSTALL_DIR) $(1)/usr/lib/freenetconfd
	$(CP) \
		$(PKG_BUILD_DIR)/lib/*.so \
		$(1)/usr/lib/freenetconfd/

	$(INSTALL_DIR) $(1)/etc/yang
	$(INSTALL_CONF) \
		$(PKG_BUILD_DIR)/yang/*.yang \
		$(1)/etc/yang/
endef

$(eval $(call BuildPackage,freenetconfd-plugin-dt-sip))
