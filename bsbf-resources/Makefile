# SPDX-License-Identifier: AGPL-3.0-or-later
# Copyright (C) 2025-2026 Chester A. Unal <chester.a.unal@arinc9.com>

include $(TOPDIR)/rules.mk

PKG_NAME:=bsbf-resources
PKG_VERSION:=1

PKG_LICENSE:=AGPL-3.0-or-later

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/bondingshouldbefree/bsbf-resources.git
PKG_SOURCE_VERSION:=HEAD

include $(INCLUDE_DIR)/package.mk

define Package/bsbf-mptcp
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-mptcp
  DEPENDS:=+fping +ip-full
endef

define Package/bsbf-netspeed
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-netspeed
endef

define Package/bsbf-quectel-usbnet
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-quectel-usbnet
endef

define Package/bsbf-route
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-route
  DEPENDS:=+fping
endef

define Package/bsbf-tcp-in-udp
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-tcp-in-udp
  DEPENDS:=+ethtool +tc-full
endef

define Package/bsbf-tlt-sw-link
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-tlt-sw-link
endef

define Package/bsbf-usb-netdev-autodhcp
  SECTION:=net
  CATEGORY:=Network
  TITLE:=bsbf-usb-netdev-autodhcp
endef

define Build/Compile
endef

define Package/bsbf-mptcp/install
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) ./files/etc/config/bsbf-mptcp $(1)/etc/config

	$(INSTALL_DIR) $(1)/etc/hotplug.d/iface
	$(INSTALL_BIN) ./files/etc/hotplug.d/iface/99-bsbf-mptcp $(1)/etc/hotplug.d/iface

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/bsbf-mptcp $(1)/etc/init.d

	$(INSTALL_DIR) $(1)/usr/local/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-mptcp $(1)/usr/local/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-mptcp-helper $(1)/usr/local/sbin
endef

define Package/bsbf-netspeed/install
	$(INSTALL_DIR) $(1)/usr/local/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-netspeed $(1)/usr/local/sbin
endef

define Package/bsbf-quectel-usbnet/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/bsbf-quectel-usbnet $(1)/etc/init.d

	$(INSTALL_DIR) $(1)/usr/local/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-quectel-usbnet $(1)/usr/local/sbin
endef

define Package/bsbf-route/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/bsbf-route $(1)/etc/init.d

	$(INSTALL_DIR) $(1)/usr/local/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-route $(1)/usr/local/sbin
endef

define Package/bsbf-tcp-in-udp/install
	$(INSTALL_DIR) $(1)/etc/hotplug.d/iface
	$(INSTALL_BIN) ./files/etc/hotplug.d/iface/99-bsbf-tcp-in-udp $(1)/etc/hotplug.d/iface

	$(INSTALL_DIR) $(1)/usr/lib/bpf
	$(INSTALL_DATA) ./files/usr/lib/bpf/tcp_in_udp_tc_le.o $(1)/usr/lib/bpf/tcp_in_udp_tc.o

	$(INSTALL_DIR) $(1)/usr/local/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/resources-client/bsbf-tcp-in-udp $(1)/usr/local/sbin
endef

define Package/bsbf-tlt-sw-link/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/bsbf-tlt-sw-link $(1)/etc/init.d

	$(INSTALL_DIR) $(1)/usr/local/sbin
	$(INSTALL_BIN) ./files/usr/local/sbin/bsbf-tlt-sw-link $(1)/usr/local/sbin
endef

define Package/bsbf-usb-netdev-autodhcp/install
	$(INSTALL_DIR) $(1)/etc/hotplug.d/net
	$(INSTALL_BIN) ./files/etc/hotplug.d/net/99-bsbf-usb-netdev-autodhcp $(1)/etc/hotplug.d/net
endef

$(eval $(call BuildPackage,bsbf-mptcp))
$(eval $(call BuildPackage,bsbf-netspeed))
$(eval $(call BuildPackage,bsbf-quectel-usbnet))
$(eval $(call BuildPackage,bsbf-route))
$(eval $(call BuildPackage,bsbf-tcp-in-udp))
$(eval $(call BuildPackage,bsbf-tlt-sw-link))
$(eval $(call BuildPackage,bsbf-usb-netdev-autodhcp))
