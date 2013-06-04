# 
# Copyright (C) 2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# $Id: Makefile $

# OpenWrt package for Capsulator
# Prepared by Michael Smith, McGill University

include $(TOPDIR)/rules.mk

PKG_NAME_SHORT:=capsulator
PKG_NAME:=$(PKG_NAME_SHORT)

PKG_RELEASE:=1
PKG_VERSION=0.1

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/capsulator/Default
	SECTION:=net
	CATEGORY:=Network
endef

define Package/capsulator/Default/description
	A tunneling software written for Openflow deployment at Stanford.
endef

define Package/capsulator
	$(call Package/capsulator/Default)
	TITLE:=Capsulator tunelling software
	DEPENDS:=+openvswitch-common +libpthread
endef

define Package/capsulator/description
	$(call Package/capsulator/Default/description)
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./capsulator/* $(PKG_BUILD_DIR)/
endef

define Package/capsulator/install
	$(INSTALL_DIR) $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/capsulator $(1)/usr/sbin
endef

$(eval $(call BuildPackage,capsulator))
