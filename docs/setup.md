# Installation

These instructions are adapted from the `INSTALL` file at the root of the repository. Consult `INSTALL` for the complete, platform-specific notes.

## Quick install

Most users on most platforms can install Git with:

```bash
make
make install
```

This builds Git from source and installs it under `$HOME` by default.

## System-wide install

To install under `/usr` (system-wide):

```bash
make prefix=/usr all
sudo make prefix=/usr install
```

## Autoconf-based build

A `./configure` workflow is also supported:

```bash
make configure
./configure --prefix=/usr
make
sudo make install
```

The `configure` step is generated from `configure.ac`; it accepts the usual autoconf flags such as `--with-zlib=PATH`, `--with-openssl=PATH`, and `--with-curl=PATH`.

## Profile-feedback build

For maximum performance, a profile-feedback build is available:

```bash
make prefix=/usr PROFILE=BUILD all
make prefix=/usr PROFILE=BUILD install
```

This builds Git twice — once instrumented to gather profiling data, then again using that data to produce an optimized binary.

## Where to go next

For platform-specific dependencies (zlib, OpenSSL, curl, expat, etc.) and unusual build environments, see the full `INSTALL` file in the repository root.
