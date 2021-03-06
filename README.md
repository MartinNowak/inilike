# Inilike

Inilike is D library for parsing **.ini**-like files used in Unix systems in various places (.desktop files, icon themes, mimeapps.list, mimeinfo.cache, trashcan files on freedesktop, etc.)

[![Build Status](https://travis-ci.org/MyLittleRobo/inilike.svg?branch=master)](https://travis-ci.org/MyLittleRobo/inilike)

Note: the original purpose of this library is to serve as dependency for my other projects, e.g. [desktopfile](https://github.com/MyLittleRobo/desktopfile) and [icontheme](https://github.com/MyLittleRobo/icontheme). It may be not suitable to save configuration files using this library. You have been warned.

## Generating documentation

Ddoc:

    dub build --build=docs
    
Ddox:

    dub build --build=ddox

## Running tests

    dub test

## Format

Unix configuration files don't have any strict standard on format. Still some specifications use the format which I call **ini-like** because it's very similiar to **INI** used in MS Windows with small differences:

1. Comments start with '#', not ';'. So ';' symbol can be presented in keys.
2. Comments are always placed on their own line. Key-value can't be mixed with comment on the same line.

## Localized values lookup. 

The localized value is the value associated with the localized key. Localized keys look like this:

    keyname[locale]

where **locale** is the [POSIX locale](http://en.wikipedia.org/wiki/Locale) with the charset part dropped.

Inilike library has support for lookup of localized values, using the algorithm described in [Desktop Entry Specification](http://standards.freedesktop.org/desktop-entry-spec/latest/ar01s04.html).

