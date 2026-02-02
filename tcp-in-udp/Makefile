# SPDX-License-Identifier: AGPL-3.0-or-later
# Copyright (C) 2025-2026 Chester A. Unal <chester.a.unal@arinc9.com>

include $(TOPDIR)/rules.mk

PKG_NAME:=tcp-in-udp
PKG_VERSION:=1

PKG_LICENSE:=AGPL-3.0-or-later
PKG_MAINTAINER:=Chester A. Unal <chester.a.unal@arinc9.com>

include $(INCLUDE_DIR)/package.mk

define Package/tcp-in-udp
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Lightweight TCP in UDP tunnel using eBPF
endef

define Build/Compile
endef

define Package/tcp-in-udp/install
	$(INSTALL_DIR) $(1)/usr/lib/bpf
	$(INSTALL_DATA) ./files/usr/lib/bpf/tcp_in_udp_tc_le.o $(1)/usr/lib/bpf/tcp_in_udp_tc.o
endef

$(eval $(call BuildPackage,tcp-in-udp))
