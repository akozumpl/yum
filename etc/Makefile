YUMETC=$(DESTDIR)/etc/yum

all:
	echo "Nothing to do"

clean:
	rm -f *.pyc *.pyo *~

install:
	mkdir -p $(DESTDIR)/etc/yum/
	mkdir -p $(DESTDIR)/etc/yum/protected.d
	mkdir -p $(DESTDIR)/etc/yum/repos.d
	mkdir -p $(DESTDIR)/etc/yum/vars

	install -m 644 yum.conf $(YUMETC)/yum.conf

	install -m 644 version-groups.conf $(YUMETC)/version-groups.conf

	mkdir -p $(DESTDIR)/etc/logrotate.d
	install -m 644 yum.logrotate $(DESTDIR)/etc/logrotate.d/yum

	mkdir -p $(DESTDIR)/etc/rc.d/init.d
	install -m 755 yum-updatesd.init $(DESTDIR)/etc/rc.d/init.d/yum-updatesd

	mkdir -p $(DESTDIR)/etc/dbus-1/system.d/
	install -m 755 yum-updatesd-dbus.conf $(DESTDIR)/etc/dbus-1/system.d/yum-updatesd.conf
	install -m 644 yum-updatesd.conf $(YUMETC)
	mkdir -p $(DESTDIR)/etc/bash_completion.d
	install -m 644 yum.bash $(DESTDIR)/etc/bash_completion.d
	install -m 644 yum-cron.conf $(YUMETC)
