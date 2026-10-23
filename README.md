# QOwnNotes RPM build

![Version](https://img.shields.io/github/v/release/sciurius/QOwnNotes-scripts)
![GitHub issues](https://img.shields.io/github/issues/sciurius/QOwnNotes-scripts)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
![Language JavaScript](https://img.shields.io/badge/Language-JavaScript-blue)
![Language QML](https://img.shields.io/badge/Language-QML-blue)

This repo contains the rpm spec file needed to build a QOwnNotes RPM,
and some patches.

* [Official QOwnNotes repository](https://github.com/pbek/QOwnNotes)
* [QOwnNotes script repository](https://github.com/qownnotes/scripts)

Note that the `GNUmakefile` allows dynamic substitution of the actual
version number, so there's no need to check in a new spec for every
version update.

## Upgrade procedure

Assume Patrizio releases QOwnNotes `26.11.1`, and that your mock build
folder is `~/rpmbuild`. Just execute

    make install V=26.11.1

See the `GNUmakefile` for details.


