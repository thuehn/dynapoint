include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-dynapoint
PKG_VERSION:=0.1
PKG_RELEASE:=1

PKG_MAINTAINER:=Tobias Ilte <tobias.ilte@campus.tu-berlin.de>
PKG_LICENSE:=GPL-3.0+
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk

define Package/luci-app-dynapoint
	SECTION:=luci
	CATEGORY:=LuCI
	DEPENDS:=+lua +luci-base +dynapoint
	MAINTAINER:=Tobias Ilte <tobias.ilte@campus.tu-berlin.de>
	TITLE:=LuCI Support for DynaPoint
	PKGARCH:=all
	MENU:=1
endef

define Package/luci-app-dynapoint/description
Makes access point ssids dependable on certain network conditions.
endef

define Build/Compile
endef

define Package/luci-app-dynapoint/install
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./files/uci-defaults/40_luci-dynapoint $(1)/etc/uci-defaults/40_luci-dynapoint
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/model/cbi/dynapoint
	$(INSTALL_DATA) ./files/cbi/dynapoint.lua $(1)/usr/lib/lua/luci/model/cbi/dynapoint/dynapoint.lua
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/controller
	$(INSTALL_DATA) ./files/controller/dynapoint.lua $(1)/usr/lib/lua/luci/controller/dynapoint.lua	
endef

$(eval $(call BuildPackage,luci-app-dynapoint))