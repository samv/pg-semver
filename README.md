semver 0.2.0
============

This library contains a single PostgreSQL extension, a data type called
"semver". It's an implementation of the version number format specified by the
[Samantic Versioning Specification](http://semver.org/). Currently it's
implemented as a data domain, but may be converted to a native type
implemented in C in the future. Either way, functionality should remain the
same.

To build semver, just do this:

    make
    make installcheck
    make install

If you encounter an error such as:

    "Makefile", line 8: Need an operator

You need to use GNU make, which may well be installed on your system as
`gmake`:

    gmake
    gmake install
    gmake installcheck

If you encounter an error such as:

    make: pg_config: Command not found

Be sure that you have `pg_config` installed and in your path. If you used a
package management system such as RPM to install PostgreSQL, be sure that the
`-devel` package is also installed. If necessary tell the build process where
to find it:

    env PG_CONFIG=/path/to/pg_config make && make installcheck && make install

If you encounter an error such as:

    ERROR:  must be owner of database regression

You need to run the test suite using a super user, such as the default
"postgres" super user:

    make installcheck PGUSER=postgres

Dependencies
------------
The `semver` data type has no dependencies other than PostgreSQL and PL/pgSQL.

Copyright and License
---------------------

Copyright (c) 2010-2011 David E. Wheeler and Sam Vilain.

This module is free software; you can redistribute it and/or modify it under
the [PostgreSQL License](http://www.opensource.org/licenses/postgresql).

Permission to use, copy, modify, and distribute this software and its
documentation for any purpose, without fee, and without a written agreement is
hereby granted, provided that the above copyright notice and this paragraph
and the following two paragraphs appear in all copies.

In no event shall David E. Wheeler or Sam Vilain be liable to any party for
direct, indirect, special, incidental, or consequential damages, including
lost profits, arising out of the use of this software and its documentation,
even if David E. Wheeler or Sam Vilain has been advised of the possibility of
such damage.

David E. Wheeler and Sam Vilain specifically disclaim any warranties,
including, but not limited to, the implied warranties of merchantability and
fitness for a particular purpose. The software provided hereunder is on an "as
is" basis, and David E. Wheeler and Sam Vilain have no obligations to provide
maintenance, support, updates, enhancements, or modifications.
