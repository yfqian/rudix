include ../../Library/Rudix.mk

Title=		Ack!
Name=		ack
Version=	2.14
Revision=	0
Site=		http://beyondgrep.com/
Source=		http://beyondgrep.com/ack-$(Version)-single-file
License=	Artistic License

ReadMeFile=	README
LicenseFile=	LICENSE

define retrieve_inner_hook
$(fetch) $(Source)
endef

define prep_inner_hook
endef

define check_inner_hook
perl $(Source) --version | grep $(Version)
endef

define install_inner_hook
install -d $(DestDir)$(BinDir)
install -m 755 $(shell basename $(Source)) $(DestDir)$(BinDir)/ack
endef

define test_inner_hook
$(BinDir)/ack --version | grep $(Version)
endef
