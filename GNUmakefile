#!/bin/make -f

V := 26.10.13
R := 1
VV := jv.${R}.fc44
MOCK_FLAGS := --no-clean
RPM_FLAGS := --force
RPMBUILD := ${HOME}/rpmbuild
RESULT := /var/lib/mock/fedora-44-x86_64/result
DOWNLOAD := https://github.com/pbek/QOwnNotes/releases/download
TXZ := qownnotes-${V}.tar.xz

default :: ${RESULT}/qownnotes-${V}-${VV}.x86_64.rpm

${RESULT}/qownnotes-${V}-${VV}.x86_64.rpm :: ${RPMBUILD}/SOURCES/${TXZ}
	sed -e "s/^Version.*/Version:        $V/" rpm.spec > qownnotes.spec
	rpmbuild -bs qownnotes.spec
	mock ${MOCK_FLAGS} ${RPMBUILD}/SRPMS/qownnotes-${V}-${VV}.src.rpm
	rm -f qownnotes.spec

install :: ${RESULT}/qownnotes-${V}-${VV}.x86_64.rpm
	sudo rpm -Uvh ${RPM_FLAGS} ${RESULT}/qownnotes-${V}-${VV}.x86_64.rpm

${RPMBUILD}/SOURCES/${TXZ} ::
	wget -O ${RPMBUILD}/SOURCES/${TXZ} ${DOWNLOAD}/v${V}/${TXZ}
