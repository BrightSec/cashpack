The cashpack release process
============================

Administrativa:

- Check for ABI changes and the linker version script
- Bump the version number
- Add a changelog entry to the RPM spec
- Check copyright notices of updated files
- Check git-ignored files after a non-VPATH build
- Check generated headers and manual pages

Local checks:

- Build with GCC, Clang, pcc, afl-gcc and Sparse
- Check with scan-build and cppcheck
- Run the test suite with nghttp2 and Go
- Build with gmake and bmake
- Test with bash, dash, ksh, lksh, mksh, yash and zsh
- Build using asan+ubsan, Valgrind and lcov
- Run again with msan and an instrumented nghttp2
- Build an RPM package from a dist archive
- Run rpmlint on both the spec, SRPM and RPM
- Double-check ABI changes with abipkgdiff and readelf

.. cppcheck cheat sheet:
.. --std=c99 --enable=all-except-style-and-information
.. -I/usr/include -Icompiler-include -Irepo-include...

Remote checks:

- Trigger an analysis by Coverity Scan
- Build on aarch64, i686, ppc64le and s390x
- Prepare release notes for release tag
- Await Coverity Scan results

Release:

- Build the dist archive from the commit to tag
- Push annotated tag cashpack-${VERSION}
  - Include dist archive checksum
- Upload dist archive in release page
  - Check sourcehut's checksum matches

Estimated time if nothing goes wrong: 1h.
