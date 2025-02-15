include $(TOPDIR)/rules.mk

PKG_NAME:=restic
PKG_VERSION:=0.13.1
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/restic/restic/tar.gz/v${PKG_VERSION}?
PKG_HASH:=8430f80dc17b98fd78aca6f7d635bf12a486687677e15989a891ff4f6d8490a9

PKG_LICENSE:=BSD-2-Clause
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Tom Stöveken <tom@naaa.de>

PKG_BUILD_DEPENDS:=golang/host
PKG_BUILD_PARALLEL:=1
PKG_USE_MIPS16:=0

GO_PKG:=github.com/restic/restic/
GO_PKG_BUILD_PKG:=github.com/restic/restic/cmd/restic/
GO_PKG_LDFLAGS_X:=main.version=$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include ../../lang/golang/golang-package.mk

define Package/restic
  TITLE:=restic backup program
  URL:=http://github.com/restic/restic
  DEPENDS:=$(GO_ARCH_DEPENDS)
  SECTION:=utils
  CATEGORY:=Utilities
endef

define Package/restic/description
restic is a backup program that is fast, efficient and secure. It supports the
three major operating systems (Linux, macOS, Windows) and a few smaller ones
(FreeBSD, OpenBSD).
endef

$(eval $(call GoBinPackage,restic))
$(eval $(call BuildPackage,restic))
