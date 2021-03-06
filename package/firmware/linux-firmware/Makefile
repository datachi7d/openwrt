#
# Copyright (C) 2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=linux-firmware
PKG_SOURCE_VERSION:=f8c22c692bdee57a20b092e647464ff6176df3ed
PKG_VERSION:=2014-03-16-$(PKG_SOURCE_VERSION)
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=git://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git
PKG_MIRROR_MD5SUM:=ca4d289ad9380471cae376fc7dd3660a

PKG_MAINTAINER:=Felix Fietkau <nbd@openwrt.org>

include $(INCLUDE_DIR)/package.mk

define Package/r8169-firmware
  SECTION:=firmware
  CATEGORY:=Firmware
  URL:=http://git.kernel.org/cgit/linux/kernel/git/firmware/linux-firmware.git
  TITLE:=RealTek r8169 firmware
endef

define Package/r8169-firmware/install
	$(INSTALL_DIR) $(1)/lib/firmware/rtl_nic
	$(CP) \
		$(PKG_BUILD_DIR)/rtl_nic/* \
		$(1)/lib/firmware/rtl_nic
endef

define Package/r8188eu-firmware
  SECTION:=firmware
  CATEGORY:=Firmware
  URL:=http://git.kernel.org/cgit/linux/kernel/git/firmware/linux-firmware.git
  TITLE:=RealTek r8188eu firmware
endef

define Package/r8188eu-firmware/install
	$(INSTALL_DIR) $(1)/lib/firmware/rtlwifi
	$(CP) \
		$(PKG_BUILD_DIR)/rtlwifi/rtl8188eufw.bin \
		$(1)/lib/firmware/rtlwifi
endef

define Package/ibt-firmware
  SECTION:=firmware
  CATEGORY:=Firmware
  URL:=http://git.kernel.org/cgit/linux/kernel/git/firmware/linux-firmware.git
  TITLE:=Intel bluetooth firmware
endef

define Package/ibt-firmware/install
	$(INSTALL_DIR) $(1)/lib/firmware/intel
	$(CP) \
		$(PKG_BUILD_DIR)/intel/*.bseq \
		$(1)/lib/firmware/intel
endef

define Package/ar3k-firmware
  SECTION:=firmware
  CATEGORY:=Firmware
  URL:=http://git.kernel.org/cgit/linux/kernel/git/firmware/linux-firmware.git
  TITLE:=ath3k firmware
endef

define Package/ar3k-firmware/install
	$(INSTALL_DIR) $(1)/lib/firmware/ar3k
	$(CP) \
		$(PKG_BUILD_DIR)/ar3k/*.dfu \
		$(1)/lib/firmware/ar3k
endef

define Build/Compile

endef

$(eval $(call BuildPackage,ar3k-firmware))
$(eval $(call BuildPackage,ibt-firmware))
$(eval $(call BuildPackage,r8169-firmware))
$(eval $(call BuildPackage,r8188eu-firmware))
