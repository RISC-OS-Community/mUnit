# µnit

This is a RISC OS port of µnit, which is a small but full-featured unit testing
framework for C.  It has no dependencies (beyond libc), is permissively licensed
(MIT), and is easy to include into any project.

This simple framework allows to run C Unit Tests directly on RISC OS, which
helps to speed up coding process. Hopefully it will be useful to many in the
community.

For more information on the original µnit, see:
[the µnit web site](https://nemequ.github.io/munit).

## Why a Port to RISC OS?
Simple, usual reason: RISC OS has a completely different File System than most modern OSes and deals with C/Headers and paths differently than other modern OSes, so pushing patches specifically for RISC OS to the original project is:

a) most likely of no interest for the original project
b) will cause issues that are just related to how RISC OS deals with files (C files, Header files and paths) which would bring no added value to the original project.

<!--
[![Build status](https://travis-ci.org/nemequ/munit.svg?branch=master)](https://travis-ci.org/nemequ/munit)
[![Windows build status](https://ci.appveyor.com/api/projects/status/db515g5ifcwjohq7/branch/master?svg=true)](https://ci.appveyor.com/project/quixdb/munit/branch/master)
-->

## Features

Features µnit currently includes include:

 * Handy assertion macros which make for nice error messages.
 * Reproducible cross-platform random number generation, including
   support for supplying a seed via CLI.
 * Timing of both wall-clock and CPU time.
 * Parameterized tests.
 * Nested test suites.
 * Flexible CLI.
 * Hiding output of successful tests.

<!--
### Include into your project with meson

In your `subprojects` folder put a `munit.wrap` file containing:

```
[wrap-git]
directory=munit
url=https://github.com/nemequ/munit/
revision=head
```

Then you can use a subproject fallback when you include munit as a
dependency to your project: `dependency('munit', fallback: ['munit', 'munit_dep'])`
-->

### How to build it

#### Building using GCC

This is easy, just make sure your filer has seen where your copy of !GCC is located on your RISC OS system and then double click on the MkGCC file to build everything.

#### Building using DDE

To build with DDE you need to first instal !UnixLib and then also !UnixLib-Dev (you can find both on !Packman).

Th ebuild in DDE is broken at the moment due issues between UnixLib and DDE.

## Documentation

For the original µnit documantetion see: [the µnit web site](https://nemequ.github.io/munit).

Additionally, there is a heavily-commented test file
[example.c](./tests/example.c) in the repository.
