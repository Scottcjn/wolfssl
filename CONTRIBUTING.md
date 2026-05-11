# Contributing to wolfSSL

Thank you for helping improve wolfSSL. Contributions are most useful when they
are focused, reproducible, and easy to review.

## Before You Start

- Open a focused issue or pull request for one change at a time.
- Describe the platform, compiler, and configuration that motivated the change.
- Check the existing documentation and nearby source files before adding new
  patterns or options.
- Avoid committing generated files or local build artifacts unless they are
  required for the change.

## Development Setup

For a checkout from git, bootstrap the Autotools files before configuring:

```sh
./autogen.sh
./configure
make
make check
```

Release archives already include the generated configuration files, so they can
usually start at `./configure`.

For a CMake build, use a separate build directory:

```sh
mkdir build
cd build
cmake ..
cmake --build .
```

See `INSTALL` and `cmake/README.md` for additional build options and platform
notes.

## Coding Guidelines

- Follow the style of the files you edit, including naming, indentation, and
  error-handling patterns.
- Keep portability in mind across embedded, desktop, and cross-compiled builds.
- Add or update tests, examples, and documentation when behavior changes.
- Keep public API changes small and document any new configuration options.
- Prefer targeted changes over broad rewrites or unrelated formatting cleanup.

## Pull Request Checklist

Before opening a pull request:

- Branch from the latest `master`.
- Run `git diff --check`.
- Run the relevant Autotools, CMake, example, or platform-specific checks for
  the files you changed.
- Note any checks you could not run and why.
- Update `INSTALL`, `README.md`, or `cmake/README.md` when adding or changing a
  documented build option.

Clear context and focused validation help reviewers reproduce the change and
merge it with confidence.
