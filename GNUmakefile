#!/bin/make -f

V := 26.10.5
R := 1
VV := jv.${R}.fc44
MOCK_FLAGS := --no-clean
RPM_FLAGS := --force
RPMBUILD := ${HOME}/rpmbuild
RESULT := /var/lib/mock/fedora-44-x86_64/result

rpm ::
	sed -e "s/^Version.*/Version:        $V/" rpm.spec > qownnotes.spec
	rpmbuild -bs qownnotes.spec
	mock ${MOCK_FLAGS} ${RPMBUILD}/SRPMS/qownnotes-${V}-${VV}.src.rpm
	rm -f qownnotes.spec

install :: rpm
	sudo rpm -Uvh ${RPM_FLAGS} ${RESULT}/qownnotes-${V}-${VV}.x86_64.rpm
