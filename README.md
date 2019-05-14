# spectool2

For my [awesome RHEL 6/7 repository](https://www.getpagespeed.com/redhat), I needed a tool to deal with updating some tags and information within the `.spec` files.
I found *none* that work on the command line.

This is my attempt at hiding the ugly regexes for editing .spec files by extending the standard `spectool` with "write" capabilities.

BEWARE! I have no Perl experience and things may be super ugly if you look inside :) But it works for me :D

## Synopsis

### Edit Version

    spectool2 --edit-version 4.3.2.1 some.spec # results in Version: 4.3.2.1

### Get a global value

    spectool2 --get-global --name upstream_version some.spec

### Edit a tag

    spectool2 --edit-tag Vendor --value GetPageSpeed some.spec
    
Note: the tag must already exist for this to work.

### Also

The standard `spectool` function (listing source files and fetching them) is there. The only major change, is that listing a single source file will give you just that, its resource.

So `spectool2 --source 0 some.spec` will give you `some.tar.gz` and not `Source0: some.tar.gz` to assist with scripting.

## Installation in CentOS / RHEL 7

    yum install https://extras.getpagespeed.com/release-el7-latest.rpm
    yum install spectool2
    
