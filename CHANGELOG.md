Change Log
==========

All notable changes to this project will be documented in this file.

[Unreleased](https://github.com/FreddieChopin/bleeding-edge-toolchain/compare/190223...HEAD)
--------------------------------------------------------------------------------------------

### Changed

- Updated gcc to version 9.0.1-RC-20190426.
- Updated isl to version 0.21.
- Updated libiconv to version 1.16.
- Updated python to version 2.7.16.

[190223](https://github.com/FreddieChopin/bleeding-edge-toolchain/compare/180726...190223) - 2019-02-23
-------------------------------------------------------------------------------------------------------

### Changed

- Updated gcc to version 8.3.0.
- Updated binutils to version 2.32.
- Updated newlib to version 3.1.0.
- Updated gdb to version 8.2.1.
- Updated expat to version 2.2.6.
- Updated isl to version 0.20.
- Updated mpfr to version 4.0.2.
- Use [`--enable-newlib-global-stdio-streams`](https://sourceware.org/ml/newlib/2017/msg00516.html) option for both
newlib and newlib-nano.
- Download expat from github, as sourceforge is not reliable.
- Download zlib from project's website, as sourceforge is not reliable.
- Compress Linux package using single thread only - this is slower, but produces smaller file. The default can be
overriden with `XZ_OPT` environment variable: `XZ_OPT="-9e -T 0 -v" ./build-bleeding-edge-toolchain.sh ...`.
- Make all files in Linux package read-only.
- Compress Linux package without timestamps.

[180726](https://github.com/FreddieChopin/bleeding-edge-toolchain/compare/180502...180726) - 2018-07-26
-------------------------------------------------------------------------------------------------------

### Changed

- Updated gcc to version 8.2.0.
- Updated binutils to version 2.31.1.
- Updated python to version 2.7.15.
- Updated newlib to version 3.0.0.20180720.

[180502](https://github.com/FreddieChopin/bleeding-edge-toolchain/compare/180127...180502) - 2018-05-02
-------------------------------------------------------------------------------------------------------

### Added

- Support for building gcc snapshots (including release candidates).

### Changed

- Updated gcc to version 8.1.0.
- Updated binutils to version 2.30.
- Updated gdb to version 8.1.
- Updated newlib to version 3.0.0.20180226.
- Updated isl to version 0.19.
- Updated mpfr to version 4.0.1.

[180127](https://github.com/FreddieChopin/bleeding-edge-toolchain/compare/170901...180127) - 2018-01-27
-------------------------------------------------------------------------------------------------------

### Added

- `--skip-documentation` option, which will disable building html/pdf documentation in the subprojects.

### Changed

- Use HTTP for all downloads, since FTP may cause problems in some network configurations.
- Updated gcc to version 7.3.0.
- Updated newlib to version 3.0.0 (+ patches).
- Updated binutils to version 2.29.1.
- Updated gdb to version 8.0.1.
- Updated expat to version 2.2.5.
- Updated mpc to version 1.1.0.
- Updated mpfr to version 4.0.0.
- Updated python to version 2.7.14.

### Fixed

- Always try to resume downloads. This fixes the problem which occured when the file is downloaded only partially.
- For native build, compile libraries (especially gmp) and other components for exactly the same host as detected by
gcc's `config.guess`.

[170901](https://github.com/FreddieChopin/bleeding-edge-toolchain/compare/170503...170901) - 2017-09-01
-------------------------------------------------------------------------------------------------------

### Changed

- Updated gcc to version 7.2.0.
- Updated newlib to version 2.5.0.20170818.
- Updated binutils to version 2.29.
- Updated gdb to version 8.0.
- Updated expat to version 2.2.4.
- Use *trusty* for Travis CI, as new gdb requires more recent version of gcc.

[170503](https://github.com/FreddieChopin/bleeding-edge-toolchain/compare/170314...170503) - 2017-05-03
-------------------------------------------------------------------------------------------------------

### Changed

- Updated gcc to version 7.1.0.
- Updated newlib to version 2.5.0.20170421.
- Updated isl to version 0.18.
- Download isl from project's website, as gcc's ftp doesn't have the most recent version.
- Explicitly disabled guile support in gdb, as recent versions of these projects are incompatible (see
[bug 21104](https://sourceware.org/bugzilla/show_bug.cgi?id=21104)).

### Fixed

- Fixed Windows builds of GCC snapshots, which failed because GCC's version (e.g. *7.0.1*) doesn't match snapshot
version (e.g. *7-20170409*).

### Removed

- Big-endian version of multilib for *ARMv7-R* targets, as now multilib configuration is part of the mainline GCC.

[170314](https://github.com/FreddieChopin/bleeding-edge-toolchain/compare/170107...170314) - 2017-03-14
-------------------------------------------------------------------------------------------------------

### Added

- `--keep-build-folders` option, which will disable removal of unneeded build folders.
- `--skip-nano-libraries` option, which will skip building of "nano" libraries, making the build much shorter.

### Changed

- Build folders are deleted as soon as they are not needed anymore.
- Download isl from gcc's ftp, as it is more reliable.
- Updated newlib to version 2.5.0.20170228.
- Updated binutils to version 2.28.
- Updated gdb to version 7.12.1.
- Updated libiconv to version 1.15.
- Updated zlib to version 1.2.11.
- Allow overriding `XZ_OPT` when calling the script.
- Both newlib and newlib-nano are built with the new `--enable-newlib-retargetable-locking` option.

### Fixed

- Fixed missing `newlib.h` when using `nano.specs`.
- Fixed download location for zlib.

[170107](https://github.com/FreddieChopin/bleeding-edge-toolchain/compare/161029...170107) - 2017-01-07
-------------------------------------------------------------------------------------------------------

### Added

- Support for "nano" variant of libraries.
- Big-endian version of multilib for *ARMv7-R* targets (by Jiri Dobry).
- Re-enabled PDF documentation for all components.

### Changed

- More detailed info about requirements to build the toolchain in README.md.
- Updated gcc to version 6.3.0.
- Updated newlib to version 2.5.0.
- Updated gmp to version 6.1.2.
- Updated isl to version 0.16.1.
- Updated python to version 2.7.13.
- Updated zlib to version 1.2.10.
- Download zlib from sourceforge, as zlib's official website seems to host only the most recent version.

### Fixed

- Removed duplicate content in gcc multilib patch (by Jiri Dobry).
- Fixed brackets in gcc multilib patch, which restores libraries for *ARMv7-R* targets (by Jiri Dobry).
- Fixed missing libstdc++ "pretty printers" in Windows packages.

161029 - 2016-10-29
-------------------

First release
