AC_PREREQ([2.63])
AC_CONFIG_MACRO_DIR([.autotools_cache/m4])
AC_CONFIG_AUX_DIR([.autotools_cache])
m4_include([.autotools_cache/m4/common.m4])

#TODO change the name skeleton by your project name
#should mach the specfile name
define([BXIMODULE], clustdock)

AC_PACKAGE([BXIMODULE])
AC_INIT(BXIMODULE, [BXIMODULE_VERSION(BXIMODULE)])
REPLACE_BRIEF(BXIMODULE)
INIT_BXIPRODUCT(BXIMODULE, [systemd])

################################## C compiler and dependencies #########################################################
#BXI_CHECK_C_COMPILER
#AC_PROG_LIBTOOL
#
#
#AX_PROG_FLEX([], [AC_MSG_ERROR([flex is required])])
#CHECK_FLEX([2.5.37],[flex="true"],[flex="false"
#            AC_MSG_WARN([flex version is not the required on 2.5.37.Continue with default template and removing Werror.])
#])
#
#AM_CONDITIONAL([BXIFLEX_UNCOMPATIBLE],[test x"$flex" = xfalse])
#
#AC_CHECK_LIB([m], [floor], [],
#             [AC_MSG_ERROR([Could not find math library])])
#
#AC_CHECK_LIB([pthread], [pthread_create], [],
#             [AC_MSG_ERROR([Could not find pthread library])])
#AC_CHECK_LIB([rt], [clock_gettime], [],
#             [AC_MSG_ERROR([Could not find rt library])])
##
#PKG_CHECK_MODULES([ZMQ], [libzmq >= 3.0.0], [],
#                  [
#                   AC_CHECK_LIB([zmq], [zmq_msg_init], [], [AC_MSG_ERROR([Could not find zmq library])])
#                  ])
#
#LDFLAGS="$LDFLAGS $ZMQ_LIBS "
#
################################# Internal dependencies ###########################
### Checks for libraries.
#CHECK_C_BXIBASE
#
#
#FLAGS_BXITEST
## Checks for library functions.
#AC_FUNC_ERROR_AT_LINE
#AC_FUNC_STRERROR_R
#AC_CHECK_FUNCS([gethostname memset mkdir pow strdup strtol])

################################## END C PART #########################################################

DEFAULT_BXIOPTION

AC_ARG_ENABLE([server], [AS_HELP_STRING([--enable-server], [enable debugging, default: yes])])
AM_CONDITIONAL([CD_SERVER],test x"$enable_server" != "xno")



################################## PYTHON Interpreter and dependencies #########################################################
INIT_BXIPYTHON

#PC_PYTHON_CHECK_MODULE_REAL([python-daemon], daemon, [], [AC_MSG_ERROR(Module not found)])
#PC_PYTHON_CHECK_MODULE([cffi], [], [AC_MSG_ERROR(Module not found)])
PC_PYTHON_CHECK_MODULE([zmq], [], [AC_MSG_ERROR(Module not found)])
PC_PYTHON_CHECK_MODULE([msgpack], [], [AC_MSG_ERROR(Module not found)])
PC_PYTHON_CHECK_MODULE([ClusterShell], [], [AC_MSG_ERROR(Module not found)])
PC_PYTHON_CHECK_MODULE([signalfd], [], [AC_MSG_ERROR(Module not found)])
PC_PYTHON_CHECK_MODULE([libvirt], [], [AC_MSG_WARN(Module not found, this is required for running)])
PC_PYTHON_CHECK_MODULE([ipaddr], [], [AC_MSG_WARN(Module not found, this is required for running)])
PC_PYTHON_CHECK_MODULE([lxml], [], [AC_MSG_WARN(Module not found, this is required for running)])
###################################### End PYTHON PART ############################################################


SUBPACKAGES="doc server"
AC_SUBST([SUBPACKAGES])
AC_BXIEXTRA_DIST=""
AC_SUBST([AC_BXIEXTRA_DIST])
#TODO add the pc.in file
AC_CONFIG_FILES([Makefile packaged/Makefile packaged/doc/Makefile tests/Makefile packaged/lib/Makefile])
AC_OUTPUT

DISPLAY_CONF(BXIMODULE)
