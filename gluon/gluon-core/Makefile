include $(TOPDIR)/rules.mk

PKG_NAME:=gluon-core
PKG_VERSION:=3
PKG_RELEASE:=$(GLUON_VERSION)

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

include $(GLUONDIR)/include/package.mk

define Package/gluon-core
  SECTION:=gluon
  CATEGORY:=Gluon
  TITLE:=Base files of Gluon
  DEPENDS:=+gluon-config +lua-platform-info +luci-lib-core +odhcp6c
endef

define Package/gluon-core/description
	Gluon community wifi mesh firmware framework: core
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/gluon-core/install
	$(CP) ./files/* $(1)/

	$(INSTALL_DIR) $(1)/lib/gluon
	echo "$(GLUON_VERSION)" > $(1)/lib/gluon/gluon-version
endef

define Package/gluon-core/postinst
#!/bin/sh
$(call GluonCheckSite,check_site.lua)
endef

$(eval $(call BuildPackage,gluon-core))
