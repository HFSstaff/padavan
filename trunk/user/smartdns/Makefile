include $(ROOTDIR)/rules.mk

PKG_NAME:=smartdns
PKG_VERSION:=1.2025.46.1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/pymumu/smartdns.git
PKG_SOURCE_VERSION:=b525170bfd627607ee5ac81f97ae0f1f4f087d6b
PKG_MIRROR_HASH:=1af77addf52a0eb9a128d289cabc743606aacbf4c8f6eddf4532421d37213a87

include $(INCLUDE_DIR)/package.mk

MAKE_PATH:=src
MAKE_FLAGS += NO_GIT_VER=1 VER=$(PKG_VERSION)

$(eval $(call BuildPackage,smartdns))

romfs:
	$(INSTALL_DIR) $(ROMFSDIR)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/smartdns $(ROMFSDIR)/usr/bin/smartdns
	$(INSTALL_BIN) ./smartdns.sh $(ROMFSDIR)/usr/bin/smartdns.sh
	$(INSTALL_DIR) $(ROMFSDIR)/etc_ro
	$(INSTALL_DATA) ./conf/*.conf $(ROMFSDIR)/etc_ro/
	$(INSTALL_BIN) ./update-china-list.sh $(ROMFSDIR)/usr/bin/update-china-list.sh
