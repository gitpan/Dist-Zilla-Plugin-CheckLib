# NAME

Dist::Zilla::Plugin::CheckLib - Require that our distribution has a particular library available

# VERSION

version 0.001

# SYNOPSIS

In your `dist.ini`:

    [CheckLib]
    lib = jpeg
    header = jpeglib.h

# DESCRIPTION

This is a [Dist::Zilla](https://metacpan.org/pod/Dist::Zilla) plugin that modifies the `Makefile.PL` or
`Build.PL` in your distribution to contain a [Devel::CheckLib](https://metacpan.org/pod/Devel::CheckLib) call, that
asserts that a particular library and/or header is available.  If it is not
available, the program exits with a status of zero, which on a
[CPAN Testers](https://metacpan.org/pod/cpantesters.org) machine will result in a NA result.

# CONFIGURATION OPTIONS

All options are as documented in [Devel::CheckLib](https://metacpan.org/pod/Devel::CheckLib):

## `lib`

A string with the name of a single library name. Can be used more than once.
Depending on the compiler found, library names will be fed to the compiler
either as `-l` arguments or as `.lib` file names. (e.g. `-ljpeg` or
`jpeg.lib`)

## `libpath`

Additional path to search for libraries. Can be used more than once.

## `LIBS`

A [ExtUtils::MakeMaker](https://metacpan.org/pod/ExtUtils::MakeMaker)-style space-separated list of libraries (each preceded by `-l`) and directories (preceded by `-L`).

## `debug`

If true, emit information during processing that can be used for debugging.

## `header`

The name of a single header file name. Can be used more than once.

## `incpath`

An additional path to search for headers. Can be used more than once.

## `INC`

A [ExtUtils::MakeMaker](https://metacpan.org/pod/ExtUtils::MakeMaker)-style space-separated list of incpaths, each preceded by `-I`.

# SUPPORT

Bugs may be submitted through [the RT bug tracker](https://rt.cpan.org/Public/Dist/Display.html?Name=Dist-Zilla-Plugin-CheckLib)
(or [bug-Dist-Zilla-Plugin-CheckLib@rt.cpan.org](mailto:bug-Dist-Zilla-Plugin-CheckLib@rt.cpan.org)).
I am also usually active on irc, as 'ether' at `irc.perl.org`.

# SEE ALSO

- [Devel::CheckLib](https://metacpan.org/pod/Devel::CheckLib)
- [Devel::AssertOS](https://metacpan.org/pod/Devel::AssertOS) and [Dist::Zilla::Plugin::AssertOS](https://metacpan.org/pod/Dist::Zilla::Plugin::AssertOS)
- [Devel::CheckBin](https://metacpan.org/pod/Devel::CheckBin) and [Dist::Zilla::Plugin::CheckBin](https://metacpan.org/pod/Dist::Zilla::Plugin::CheckBin)

# AUTHOR

Karen Etheridge <ether@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2014 by Karen Etheridge.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
