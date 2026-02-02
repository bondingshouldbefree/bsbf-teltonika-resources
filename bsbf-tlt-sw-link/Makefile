# SPDX-License-Identifier: AGPL-3.0-or-later
# Copyright (C) 2026 Chester A. Unal <chester.a.unal@arinc9.com>

include $(TOPDIR)/rules.mk

PKG_NAME:=bsbf-tlt-sw-link
PKG_VERSION:=1

PKG_LICENSE:=AGPL-3.0-or-later
PKG_MAINTAINER:=Chester A. Unal <chester.a.unal@arinc9.com>

include $(INCLUDE_DIR)/package.mk

define Package/bsbf-tlt-sw-link
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-tlt-sw-link
endef

define Build/Compile
endef

define Package/bsbf-tlt-sw-link/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/bsbf-tlt-sw-link $(1)/etc/init.d

	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) ./files/usr/sbin/bsbf-tlt-sw-link $(1)/usr/sbin
endef

$(eval $(call BuildPackage,bsbf-tlt-sw-link))
