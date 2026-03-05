include $(TOPDIR)/rules.mk

PKG_NAME:=rak-cellular-utilities
PKG_VERSION:=1.0.0
PKG_RELEASE:=1

PKG_MAINTAINER:=Alexis DEVLEESCHAUWER <alexis@devleeschauwer.fr>

include $(INCLUDE_DIR)/package.mk

define Package/rak-cellular-utilities
	SECTION:=RAK
	CATEGORY:=RAK
	TITLE:=RAK Cellular Utilities.
	DEPENDS:=+socat
endef

define Package/rak-cellular-utilities/description
	Package containing non-offcial cellular modem utilities and tools for RAK.
endef

define Build/Compile
    # No build, but section required
endef

define Package/rak-cellular-utilities/install
	# BIN
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) ./files/bin/atinyout $(1)/usr/bin

	$(INSTALL_DIR) $(1)/usr/libexec/rpcd
	$(INSTALL_BIN) ./files/rcpd/modem.qmi $(1)/usr/libexec/rpcd

	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./files/uci-defaults/99-rak-cellular-rpcd $(1)/etc/uci-defaults/
endef

$(eval $(call BuildPackage,rak-cellular-utilities))
