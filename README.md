# spectool2

For my [awesome RHEL 6/7 repository](https://www.getpagespeed.com/redhat), I needed a tool to deal with updating some tags and information within the `.spec` files.
I found *none* that work on the command line.

This is my attempt at hiding the ugly regexes for editing .spec files by extending the standard `spectool` with "write" capabilities.

BEWARE! I have no Perl experience and things may be super ugly if you look inside :) But it works for me :D
