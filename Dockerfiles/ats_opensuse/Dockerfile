# Base image.
FROM opensuse/tumbleweed

RUN zypper update && \
    zypper install -y \
      # CMake is used as the build system generator for ATS.
      cmake \
      # GCC is a dependency for compiling psutils, an AuTest dependency.
      gcc \
      # This environment uses G++ as the compiler for ATS.
      gcc-c++ \
      # HWLOC is a highly recommended dependency for ATS.
      hwloc-devel \
      # This environment provides Jemalloc as an alternative allocator for ATS.
      jemalloc-devel \
      # CMake may use pkgconf to locate dependencies.
      pkgconf \
      # Brotli is a dependency of ATS.
      libbrotli-devel \
      # The capabilities library is a dependency of ATS.
      libcap-devel \
      libexpat-devel \
      # OpenSSL is a dependency of ATS.
      libopenssl-devel \
      libunwind-devel \
      ncurses-devel-static \
      # Netcat is required as a client for some AuTests.
      netcat-openbsd \
      # This environment uses Ninja as the build system for ATS.
      ninja \
      # PCRE is a dependency of ATS.
      pcre-devel-static \
      # PCRE2 is a dependency of ATS.
      pcre2-devel-static \
      # Python3 is required to run the AuTests for ATS.
      python311-devel \
      # This environment uses pipx to set up a venv with autest.
      python311-pipx \
      # LZMA is a dependency of ATS.
      xz-devel \
      # zlib is a dependency of ATS.
      zlib-devel && \
  pipx install autest && \
  pipx upgrade autest

CMD /bin/bash
