include ../../Library/Python.mk

Title=		ItIsDangerous (Python Module)
Name=		itsdangerous
Version=	0.21
Revision=	0
Site=		http://pythonhosted.org/itsdangerous/
Source=		https://pypi.python.org/packages/source/i/itsdangerous/$(Name)-$(Version).tar.gz
License=	BSD

LicenseFile=	$(SourceDir)/PKG-INFO

define test_inner_hook
$(Python) -c 'import itsdangerous'
endef
