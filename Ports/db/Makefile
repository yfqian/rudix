include ../../Library/Rudix.mk

Title=		Berkeley DB
Name=		db
Version=	6.1.26
Revision=	0
Site=		http://www.oracle.com/technetwork/products/berkeleydb/
Source=		http://download.oracle.com/berkeley-db/$(Name)-$(Version).tar.gz
License=	AGPLv3

ReadMeFile=	$(SourceDir)/README
LicenseFile=	$(SourceDir)/LICENSE

ifeq ($(RUDIX_BUILD_STATIC_LIBS),yes)
ConfigureExtra += --disable-shared --enable-static
else ifeq ($(RUDIX_BUILD_STATIC_LIBS),no)
ConfigureExtra += --enable-shared --disable-static
endif

define build_inner_hook
cd $(SourceDir)/build_unix && \
env CFLAGS="$(CFLAGS)" LDFLAGS="$(LDFLAGS)" \
	../dist/$(configure) $(ConfigureExtra)	\
		--prefix=$(Prefix)	\
		--docdir=$(DocDir)/db	\
		--enable-compat185 --enable-dump185 \
		--enable-dbm \
		--enable-cxx ; $(make)
endef

define install_post_hook
cd $(SourceDir)/build_unix && \
make DESTDIR=$(PortDir)/$(InstallDir) \
	docdir=$(DocDir)/db install
chmod +w $(InstallDir)/$(BinDir)/*
endef

define test_inner_hook
$(BinDir)/db_verify -V
endef
