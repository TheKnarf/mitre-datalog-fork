# MITRE Datalog fork

Original project here: http://datalog.sourceforge.net/

## Abstract

This package contains a lightweight deductive database system.
Queries and database updates are expressed using Datalog--a
declarative logic language in which each formula is a function-free
Horn clause, and every variable in the goal of a clause must appear in
the body of the clause.  The use of Datalog syntax and an
implementation based on tabling intermediate results, ensures that all
queries terminate.

The components in this package are designed to be small, and usable on
memory constrained devices.  The package includes an interactive
interpreter for Datalog, and a library that can be used to embed the
interpreter into C programs.

## Installation

Build requires CMake and Lua:

```
mkdir build
cd build
cmake ..
make
```

## Documentation

This package is documented using Texinfo and a manual page.  The NEWS
file contains a history of user-visible changes.  The ChangeLog
records changes to the package.

## Test suit

The source distribution contains examples of Datalog programs used for
testing that are not installed.  Examples from the Texinfo manual are
also included.

## Authors

John D. Ramsdell
The MITRE Corporation
