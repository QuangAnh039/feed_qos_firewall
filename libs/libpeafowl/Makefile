include $(TOPDIR)/rules.mk

PKG_NAME:=libpeafowl


PKG_VERSION:=gen_1.1.4_v0.1.0
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=gen_1.1.4_v0.1.0
PKG_SOURCE_URL:=https://$(SAH_GIT_USER):$(SAH_GIT_TOKEN)@$(SAH_GIT)/$(SAH_GIT_GROUP)/libpeafowl.git
PKG_MIRROR_HASH:=skip
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=COPYING

CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

CMAKE_SOURCE_DIR:=peafowl-1.1.4

CMAKE_OPTIONS += -DCMAKE_BUILD_TYPE=RelWithDebInfo
CMAKE_OPTIONS += -DCMAKE_C_FLAGS="-DPFWL_DEFAULT_EXPECTED_FLOWS=256"
CMAKE_OPTIONS += -DCMAKE_CXX_FLAGS="-DPFWL_DEFAULT_EXPECTED_FLOWS=256"

define Package/libpeafowl
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=libpeafowl
	DEPENDS+= +libopenssl
	DEPENDS+= +libstdcpp
	DEPENDS+= +libpcap
	URL:=https://gitlab.com/soft.at.home/network/lib_peafowl
	PROVIDES:= libpeafowl
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libpeafowl.so $(1)/usr/lib/libpeafowl.so
endef

$(eval $(call BuildPackage,libpeafowl))
