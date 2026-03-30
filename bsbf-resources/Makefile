# SPDX-License-Identifier: AGPL-3.0-or-later
# Copyright (C) 2025-2026 Chester A. Unal <chester.a.unal@arinc9.com>

include $(TOPDIR)/rules.mk

PKG_NAME:=bsbf-resources
PKG_RELEASE:=1

PKG_LICENSE:=AGPL-3.0-or-later
PKG_MAINTAINER:=Chester A. Unal <chester.a.unal@arinc9.com>

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/bondingshouldbefree/bsbf-resources.git
PKG_SOURCE_DATE:=2026-03-24
PKG_SOURCE_VERSION:=1a7df5e453dc1f870906997ce0c62e84ea6e8d44
PKG_MIRROR_HASH:=skip

include $(INCLUDE_DIR)/package.mk

define Package/bsbf-client-web
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-client-web
  URL:=https://github.com/bondingshouldbefree/
  DEPENDS:=+curl +uhttpd
endef

define Package/bsbf-mptcp
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-mptcp
  URL:=https://github.com/bondingshouldbefree/
  DEPENDS:=+fping +ip-full
endef

define Package/bsbf-netspeed
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-netspeed
  URL:=https://github.com/bondingshouldbefree/
endef

define Package/bsbf-plpmtu
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-plpmtu
  URL:=https://github.com/bondingshouldbefree/
  DEPENDS:=+fping +plp-mtu-discovery
endef

define Package/bsbf-quectel-usbnet
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-quectel-usbnet
  URL:=https://github.com/bondingshouldbefree/
endef

define Package/bsbf-rate-limiting
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-rate-limiting
  URL:=https://github.com/bondingshouldbefree/
endef

define Package/bsbf-route
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-route
  URL:=https://github.com/bondingshouldbefree/
  DEPENDS:=+fping
endef

define Package/bsbf-tcp-in-udp
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-tcp-in-udp
  URL:=https://github.com/bondingshouldbefree/
  DEPENDS:=+ethtool +tc-full +tcp-in-udp
endef

define Build/Compile
endef

define Package/bsbf-client-web/install
	$(INSTALL_DIR) $(1)/www/bsbf-client-web
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/resources-client/bsbf-client-web/index.html $(1)/www/bsbf-client-web
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/resources-client/bsbf-client-web/index.js $(1)/www/bsbf-client-web
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/resources-client/bsbf-client-web/styles.css $(1)/www/bsbf-client-web

	$(INSTALL_DIR) $(1)/www/cgi-bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-client-web/cgi-bin/bsbf-bonding-conf $(1)/www/cgi-bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-client-web/cgi-bin/bsbf-force-backup $(1)/www/cgi-bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-client-web/cgi-bin/bsbf-iface-ip $(1)/www/cgi-bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-client-web/cgi-bin/bsbf-interfaces $(1)/www/cgi-bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-client-web/cgi-bin/bsbf-priority $(1)/www/cgi-bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-client-web/cgi-bin/bsbf-stats $(1)/www/cgi-bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-client-web/cgi-bin/bsbf-tc-class $(1)/www/cgi-bin
endef

define Package/bsbf-mptcp/install
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) ./files/etc/config/bsbf-mptcp $(1)/etc/config

	$(INSTALL_DIR) $(1)/etc/hotplug.d/iface
	$(INSTALL_BIN) ./files/etc/hotplug.d/iface/99-bsbf-mptcp $(1)/etc/hotplug.d/iface

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/bsbf-mptcp $(1)/etc/init.d

	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-mptcp $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-mptcp-helper $(1)/usr/sbin
endef

define Package/bsbf-netspeed/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-netspeed $(1)/usr/sbin
endef

define Package/bsbf-plpmtu/install
	$(INSTALL_DIR) $(1)/etc/hotplug.d/iface
	$(INSTALL_BIN) ./files/etc/hotplug.d/iface/99-bsbf-plpmtu $(1)/etc/hotplug.d/iface

	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-shared/bsbf-plpmtu $(1)/usr/sbin
endef

define Package/bsbf-quectel-usbnet/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/bsbf-quectel-usbnet $(1)/etc/init.d

	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-quectel-usbnet $(1)/usr/sbin
endef

define Package/bsbf-rate-limiting/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-rate-limiting $(1)/usr/sbin
endef

define Package/bsbf-route/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/bsbf-route $(1)/etc/init.d

	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-route $(1)/usr/sbin
endef

define Package/bsbf-tcp-in-udp/install
	$(INSTALL_DIR) $(1)/etc/hotplug.d/iface
	$(INSTALL_BIN) ./files/etc/hotplug.d/iface/99-bsbf-tcp-in-udp $(1)/etc/hotplug.d/iface

	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-tcp-in-udp $(1)/usr/sbin
endef

$(eval $(call BuildPackage,bsbf-client-web))
$(eval $(call BuildPackage,bsbf-mptcp))
$(eval $(call BuildPackage,bsbf-netspeed))
$(eval $(call BuildPackage,bsbf-plpmtu))
$(eval $(call BuildPackage,bsbf-quectel-usbnet))
$(eval $(call BuildPackage,bsbf-rate-limiting))
$(eval $(call BuildPackage,bsbf-route))
$(eval $(call BuildPackage,bsbf-tcp-in-udp))
