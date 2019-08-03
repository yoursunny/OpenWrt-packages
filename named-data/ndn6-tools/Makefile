include $(TOPDIR)/rules.mk

PKG_NAME:=ndn6-tools
PKG_VERSION:=0.0.20190803
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/yoursunny/ndn6-tools.git
PKG_SOURCE_VERSION:=f155042e1b701e8b97207574ccd252f47c06f859

include $(INCLUDE_DIR)/package.mk

MAKE_VARS+=PKG_CONFIG_PATH="$(STAGING_DIR)/usr/lib/pkgconfig"

define Package/ndn6-file-server
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=Named Data Networking
	TITLE:=ndn6-file-server
	DEPENDS:=+libndn-cxx
endef

define Package/ndn6-file-server/description
	serve file from filesystem
endef

define Package/ndn6-file-server/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/file-server $(1)/usr/bin/ndn6-file-server
endef

define Package/ndn6-register-prefix-cmd
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=Named Data Networking
	TITLE:=ndn6-register-prefix-cmd
	DEPENDS:=+libndn-cxx
endef

define Package/ndn6-register-prefix-cmd/description
	prepare a prefix registration command
endef

define Package/ndn6-register-prefix-cmd/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/register-prefix-cmd $(1)/usr/bin/ndn6-register-prefix-cmd
endef

define Package/ndn6-serve-certs
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=Named Data Networking
	TITLE:=ndn6-serve-certs
	DEPENDS:=+libndn-cxx
endef

define Package/ndn6-serve-certs/description
	serve certificates
endef

define Package/ndn6-serve-certs/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/serve-certs $(1)/usr/bin/ndn6-serve-certs
endef

$(eval $(call BuildPackage,ndn6-file-server))
$(eval $(call BuildPackage,ndn6-register-prefix-cmd))
$(eval $(call BuildPackage,ndn6-serve-certs))