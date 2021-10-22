
include $(TOPDIR)/rules.mk

PKG_NAME:=xc3sprog
PKG_REV:=795
PKG_VERSION:=$(PKG_REV)
PKG_RELEASE:=1

PKG_SOURCE=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=https://svn.code.sf.net/p/xc3sprog/code/trunk/
HASH:=SKIP
PKG_HASH:=7678fcad24b4b33533d069abc15d0df108fc330150e9bbd94234155c8c157f6e
PKG_MIRROR_HASH:=4b73fd227f5a29d9fbdf90973663433976bca32cccff4768cb5f9367f968a4a7

PKG_SOURCE_PROTO:=svn
PKG_SOURCE_VERSION:=$(PKG_REV)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/xc3sprog
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=xc3sporg
	DEPENDS:=+libusb-compat +libftdi1 +libstdcpp
endef

define Package/xc3sprog/description
xc3sprog is a suite of utilities for programming Xilinx FPGAs, CPLDs, and EEPROMs with the Xilinx Parallel Cable and other JTAG adapters under Linux
endef

define Package/xc3sprog/install

	$(INSTALL_DIR)	$(1)/usr/bin
	$(INSTALL_DIR)	$(1)/usr/lib
	$(INSTALL_BIN)	$(PKG_INSTALL_DIR)/usr/bin/*			$(1)/usr/bin
	$(CP)			$(FILES_DIR)/*							$(1)/usr/bin
	$(CP)			$(STAGING_DIR)/usr/lib/libftdi1.so.2	$(1)/usr/lib

endef

$(eval $(call BuildPackage,xc3sprog))
