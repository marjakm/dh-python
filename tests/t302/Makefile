#!/usr/bin/make -f
include ../common.mk

all: run check

run: clean
	dpkg-buildpackage -b -us -uc

check:
	grep -q "py3compile -p python3-foo /usr/lib/python3-foo"\
		debian/python3-foo/DEBIAN/postinst
	[ "`find debian/python3-foo/usr/lib/python3/dist-packages/foo -name 'bar.cpython-*.so'`" != "" ]

clean:
	./debian/rules clean
	rm -rf lib/Foo.egg-info build
