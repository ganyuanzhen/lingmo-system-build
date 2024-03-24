# avoid dpkg-dev dependency; fish out the version with sed
VERSION := $(shell sed 's/.*(\(.*\)).*/\1/; q' debian/changelog)

all:

clean:

DSDIR=$(DESTDIR)/usr/share/lingmo-debootstrap
install:
	mkdir -p $(DSDIR)/scripts
	mkdir -p $(DESTDIR)/usr/sbin

	cp -a scripts/* $(DSDIR)/scripts/
	install -m 0644 functions $(DSDIR)/

	sed 's/@VERSION@/$(VERSION)/g' lingmo-debootstrap >$(DESTDIR)/usr/sbin/lingmo-debootstrap
	chmod 0755 $(DESTDIR)/usr/sbin/lingmo-debootstrap
