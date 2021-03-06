AC_PREREQ([2.69])
AC_INIT([igetnonce], [1.0], [tihmstar@gmail.com])

# Prepare for automake.
AM_INIT_AUTOMAKE([foreign])
AC_CONFIG_HEADERS([config.h])

# Check for operating system.
AC_MSG_CHECKING([whether we need platform-specific build settings])
case $host_os in
  darwin* )
        ;;
esac

# Checks for programs.
AC_PROG_CC
CFLAGS+=" -std=c11"
AC_PROG_INSTALL
AC_PROG_LIBTOOL

# Versioning.
CFLAGS+=" -D IGETNONCE_VERSION_COUNT=\\\"$(git rev-list --count HEAD | tr -d '\n')\\\""
CFLAGS+=" -D IGETNONCE_VERSION_SHA=\\\"$(git rev-parse HEAD | tr -d '\n')\\\""

# Checks for libraries.
PKG_CHECK_MODULES(libimobiledevice, libimobiledevice-1.0 >= 1.2.1)
PKG_CHECK_MODULES(libirecovery, libirecovery >= 0.2.0)
PKG_CHECK_MODULES(libusbmuxd, libusbmuxd >= 0.29.1)
PKG_CHECK_MODULES(openssl, openssl >= 0.9.8)

# Checks for header files.
AC_CHECK_HEADERS([getopt.h stdio.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_TYPE_INT32_T
AC_TYPE_INT64_T
AC_TYPE_SIZE_T
AC_TYPE_UINT32_T
AC_TYPE_UINT64_T

# Checks for library functions.
AC_FUNC_ERROR_AT_LINE
AC_FUNC_FSEEKO
AC_FUNC_MALLOC
AC_CHECK_FUNCS([memset strdup strrchr])

AC_OUTPUT([
Makefile
igetnonce/Makefile
])
