.include <bsd.init.mk>

PACKAGE=	tests

TESTS_SUBDIRS=	detail

ATF=		${SRCTOP}/contrib/atf
.PATH:		${ATF}/atf-c++
.PATH:		${ATF}/atf-c++/detail

CFLAGS+=	-DATF_BUILD_CXX='"c++"'
CFLAGS+=	-DATF_BUILD_CXXFLAGS='"-Wall"'
CFLAGS+=	-DATF_C_TESTS_BASE='"${TESTSBASE}/lib/atf/libatf-c"'
CFLAGS+=	-DATF_INCLUDEDIR='"${INCLUDEDIR}"'
CFLAGS+=	-I${ATF}

${PACKAGE}FILES+=	macros_hpp_test.cpp
${PACKAGE}FILES+=	unused_test.cpp

.for _T in	atf_c++_test \
		build_test \
		check_test \
		macros_test \
		tests_test \
		utils_test
ATF_TESTS_CXX+=	${_T}
SRCS.${_T}=	${_T}.cpp test_helpers.cpp
.endfor

.for _T in	atf_c++_test \
		build_test \
		check_test \
		macros_test
TEST_METADATA.${_T}+=	required_programs="c++"
.endfor

.include <bsd.test.mk>
