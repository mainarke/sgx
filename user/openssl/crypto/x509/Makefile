#
# OpenSSL/crypto/x509/Makefile
#

DIR=	x509
TOP=	../..
CC=	cc
INCLUDES= -I.. -I$(TOP) -I../../include
CFLAG=-g
MAKEFILE=	Makefile
AR=		ar r

CFLAGS= $(INCLUDES) $(CFLAG)

GENERAL=Makefile README
TEST=
APPS=

LIB=$(TOP)/libcrypto.a
LIBSRC=	x509_def.c x509_d2.c x509_r2x.c x509_cmp.c \
	x509_obj.c x509_req.c x509spki.c x509_vfy.c \
	x509_set.c x509cset.c x509rset.c x509_err.c \
	x509name.c x509_v3.c x509_ext.c x509_att.c \
	x509type.c x509_lu.c x_all.c x509_txt.c \
	x509_trs.c by_file.c by_dir.c x509_vpm.c
LIBOBJ= x509_def.o x509_d2.o x509_r2x.o x509_cmp.o \
	x509_obj.o x509_req.o x509spki.o x509_vfy.o \
	x509_set.o x509cset.o x509rset.o x509_err.o \
	x509name.o x509_v3.o x509_ext.o x509_att.o \
	x509type.o x509_lu.o x_all.o x509_txt.o \
	x509_trs.o by_file.o by_dir.o x509_vpm.o

SRC= $(LIBSRC)

EXHEADER= x509.h x509_vfy.h
HEADER=	$(EXHEADER) vpm_int.h

ALL=    $(GENERAL) $(SRC) $(HEADER)

top:
	(cd ../..; $(MAKE) DIRS=crypto SDIRS=$(DIR) sub_all)

all:	lib

lib:	$(LIBOBJ)
	$(AR) $(LIB) $(LIBOBJ)
	$(RANLIB) $(LIB) || echo Never mind.
	@touch lib

files:
	$(PERL) $(TOP)/util/files.pl Makefile >> $(TOP)/MINFO

links:
	@$(PERL) $(TOP)/util/mklink.pl ../../include/openssl $(EXHEADER)
	@$(PERL) $(TOP)/util/mklink.pl ../../test $(TEST)
	@$(PERL) $(TOP)/util/mklink.pl ../../apps $(APPS)

install:
	@[ -n "$(INSTALLTOP)" ] # should be set by top Makefile...
	@headerlist="$(EXHEADER)"; for i in $$headerlist ; \
	do  \
	(cp $$i $(INSTALL_PREFIX)$(INSTALLTOP)/include/openssl/$$i; \
	chmod 644 $(INSTALL_PREFIX)$(INSTALLTOP)/include/openssl/$$i ); \
	done;

tags:
	ctags $(SRC)

tests:

lint:
	lint -DLINT $(INCLUDES) $(SRC)>fluff

depend:
	@[ -n "$(MAKEDEPEND)" ] # should be set by upper Makefile...
	$(MAKEDEPEND) -- $(CFLAG) $(INCLUDES) $(DEPFLAG) -- $(PROGS) $(LIBSRC)

dclean:
	$(PERL) -pe 'if (/^# DO NOT DELETE THIS LINE/) {print; exit(0);}' $(MAKEFILE) >Makefile.new
	mv -f Makefile.new $(MAKEFILE)

clean:
	rm -f *.o *.obj lib tags core .pure .nfs* *.old *.bak fluff

# DO NOT DELETE THIS LINE -- make depend depends on it.

by_dir.o: ../../e_os.h ../../include/openssl/../sgx.h
by_dir.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
by_dir.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
by_dir.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
by_dir.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
by_dir.o: ../../include/openssl/err.h ../../include/openssl/evp.h
by_dir.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
by_dir.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
by_dir.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
by_dir.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
by_dir.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
by_dir.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
by_dir.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h by_dir.c
by_file.o: ../../e_os.h ../../include/openssl/../sgx.h
by_file.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
by_file.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
by_file.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
by_file.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
by_file.o: ../../include/openssl/err.h ../../include/openssl/evp.h
by_file.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
by_file.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
by_file.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
by_file.o: ../../include/openssl/pem.h ../../include/openssl/pem2.h
by_file.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
by_file.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
by_file.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
by_file.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h by_file.c
x509_att.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_att.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_att.o: ../../include/openssl/buffer.h ../../include/openssl/conf.h
x509_att.o: ../../include/openssl/crypto.h ../../include/openssl/e_os2.h
x509_att.o: ../../include/openssl/ec.h ../../include/openssl/ecdh.h
x509_att.o: ../../include/openssl/ecdsa.h ../../include/openssl/err.h
x509_att.o: ../../include/openssl/evp.h ../../include/openssl/lhash.h
x509_att.o: ../../include/openssl/obj_mac.h ../../include/openssl/objects.h
x509_att.o: ../../include/openssl/opensslconf.h
x509_att.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_att.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_att.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_att.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_att.o: ../../include/openssl/x509_vfy.h ../../include/openssl/x509v3.h
x509_att.o: ../cryptlib.h ../sgx.h x509_att.c
x509_cmp.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_cmp.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_cmp.o: ../../include/openssl/buffer.h ../../include/openssl/conf.h
x509_cmp.o: ../../include/openssl/crypto.h ../../include/openssl/e_os2.h
x509_cmp.o: ../../include/openssl/ec.h ../../include/openssl/ecdh.h
x509_cmp.o: ../../include/openssl/ecdsa.h ../../include/openssl/err.h
x509_cmp.o: ../../include/openssl/evp.h ../../include/openssl/lhash.h
x509_cmp.o: ../../include/openssl/obj_mac.h ../../include/openssl/objects.h
x509_cmp.o: ../../include/openssl/opensslconf.h
x509_cmp.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_cmp.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_cmp.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_cmp.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_cmp.o: ../../include/openssl/x509_vfy.h ../../include/openssl/x509v3.h
x509_cmp.o: ../cryptlib.h ../sgx.h x509_cmp.c
x509_d2.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_d2.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_d2.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
x509_d2.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
x509_d2.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
x509_d2.o: ../../include/openssl/err.h ../../include/openssl/evp.h
x509_d2.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
x509_d2.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
x509_d2.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_d2.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_d2.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_d2.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_d2.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h x509_d2.c
x509_def.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_def.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_def.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
x509_def.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
x509_def.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
x509_def.o: ../../include/openssl/err.h ../../include/openssl/evp.h
x509_def.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
x509_def.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
x509_def.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_def.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_def.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_def.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_def.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h x509_def.c
x509_err.o: ../../include/openssl/../sgx.h ../../include/openssl/asn1.h
x509_err.o: ../../include/openssl/bio.h ../../include/openssl/buffer.h
x509_err.o: ../../include/openssl/crypto.h ../../include/openssl/e_os2.h
x509_err.o: ../../include/openssl/ec.h ../../include/openssl/ecdh.h
x509_err.o: ../../include/openssl/ecdsa.h ../../include/openssl/err.h
x509_err.o: ../../include/openssl/evp.h ../../include/openssl/lhash.h
x509_err.o: ../../include/openssl/obj_mac.h ../../include/openssl/objects.h
x509_err.o: ../../include/openssl/opensslconf.h
x509_err.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_err.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_err.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_err.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_err.o: ../../include/openssl/x509_vfy.h x509_err.c
x509_ext.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_ext.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_ext.o: ../../include/openssl/buffer.h ../../include/openssl/conf.h
x509_ext.o: ../../include/openssl/crypto.h ../../include/openssl/e_os2.h
x509_ext.o: ../../include/openssl/ec.h ../../include/openssl/ecdh.h
x509_ext.o: ../../include/openssl/ecdsa.h ../../include/openssl/err.h
x509_ext.o: ../../include/openssl/evp.h ../../include/openssl/lhash.h
x509_ext.o: ../../include/openssl/obj_mac.h ../../include/openssl/objects.h
x509_ext.o: ../../include/openssl/opensslconf.h
x509_ext.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_ext.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_ext.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_ext.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_ext.o: ../../include/openssl/x509_vfy.h ../../include/openssl/x509v3.h
x509_ext.o: ../cryptlib.h ../sgx.h x509_ext.c
x509_lu.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_lu.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_lu.o: ../../include/openssl/buffer.h ../../include/openssl/conf.h
x509_lu.o: ../../include/openssl/crypto.h ../../include/openssl/e_os2.h
x509_lu.o: ../../include/openssl/ec.h ../../include/openssl/ecdh.h
x509_lu.o: ../../include/openssl/ecdsa.h ../../include/openssl/err.h
x509_lu.o: ../../include/openssl/evp.h ../../include/openssl/lhash.h
x509_lu.o: ../../include/openssl/obj_mac.h ../../include/openssl/objects.h
x509_lu.o: ../../include/openssl/opensslconf.h ../../include/openssl/opensslv.h
x509_lu.o: ../../include/openssl/ossl_typ.h ../../include/openssl/pkcs7.h
x509_lu.o: ../../include/openssl/safestack.h ../../include/openssl/sha.h
x509_lu.o: ../../include/openssl/stack.h ../../include/openssl/symhacks.h
x509_lu.o: ../../include/openssl/x509.h ../../include/openssl/x509_vfy.h
x509_lu.o: ../../include/openssl/x509v3.h ../cryptlib.h ../sgx.h x509_lu.c
x509_obj.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_obj.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_obj.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
x509_obj.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
x509_obj.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
x509_obj.o: ../../include/openssl/err.h ../../include/openssl/evp.h
x509_obj.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
x509_obj.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
x509_obj.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_obj.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_obj.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_obj.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_obj.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h x509_obj.c
x509_r2x.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_r2x.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_r2x.o: ../../include/openssl/bn.h ../../include/openssl/buffer.h
x509_r2x.o: ../../include/openssl/crypto.h ../../include/openssl/e_os2.h
x509_r2x.o: ../../include/openssl/ec.h ../../include/openssl/ecdh.h
x509_r2x.o: ../../include/openssl/ecdsa.h ../../include/openssl/err.h
x509_r2x.o: ../../include/openssl/evp.h ../../include/openssl/lhash.h
x509_r2x.o: ../../include/openssl/obj_mac.h ../../include/openssl/objects.h
x509_r2x.o: ../../include/openssl/opensslconf.h
x509_r2x.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_r2x.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_r2x.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_r2x.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_r2x.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h x509_r2x.c
x509_req.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_req.o: ../../include/openssl/asn1.h ../../include/openssl/asn1t.h
x509_req.o: ../../include/openssl/bio.h ../../include/openssl/bn.h
x509_req.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
x509_req.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
x509_req.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
x509_req.o: ../../include/openssl/err.h ../../include/openssl/evp.h
x509_req.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
x509_req.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
x509_req.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_req.o: ../../include/openssl/pem.h ../../include/openssl/pem2.h
x509_req.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_req.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_req.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_req.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h x509_req.c
x509_set.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_set.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_set.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
x509_set.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
x509_set.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
x509_set.o: ../../include/openssl/err.h ../../include/openssl/evp.h
x509_set.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
x509_set.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
x509_set.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_set.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_set.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_set.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_set.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h x509_set.c
x509_trs.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_trs.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_trs.o: ../../include/openssl/buffer.h ../../include/openssl/conf.h
x509_trs.o: ../../include/openssl/crypto.h ../../include/openssl/e_os2.h
x509_trs.o: ../../include/openssl/ec.h ../../include/openssl/ecdh.h
x509_trs.o: ../../include/openssl/ecdsa.h ../../include/openssl/err.h
x509_trs.o: ../../include/openssl/evp.h ../../include/openssl/lhash.h
x509_trs.o: ../../include/openssl/obj_mac.h ../../include/openssl/objects.h
x509_trs.o: ../../include/openssl/opensslconf.h
x509_trs.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_trs.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_trs.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_trs.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_trs.o: ../../include/openssl/x509_vfy.h ../../include/openssl/x509v3.h
x509_trs.o: ../cryptlib.h ../sgx.h x509_trs.c
x509_txt.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_txt.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_txt.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
x509_txt.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
x509_txt.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
x509_txt.o: ../../include/openssl/err.h ../../include/openssl/evp.h
x509_txt.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
x509_txt.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
x509_txt.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_txt.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_txt.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_txt.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_txt.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h x509_txt.c
x509_v3.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_v3.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_v3.o: ../../include/openssl/buffer.h ../../include/openssl/conf.h
x509_v3.o: ../../include/openssl/crypto.h ../../include/openssl/e_os2.h
x509_v3.o: ../../include/openssl/ec.h ../../include/openssl/ecdh.h
x509_v3.o: ../../include/openssl/ecdsa.h ../../include/openssl/err.h
x509_v3.o: ../../include/openssl/evp.h ../../include/openssl/lhash.h
x509_v3.o: ../../include/openssl/obj_mac.h ../../include/openssl/objects.h
x509_v3.o: ../../include/openssl/opensslconf.h ../../include/openssl/opensslv.h
x509_v3.o: ../../include/openssl/ossl_typ.h ../../include/openssl/pkcs7.h
x509_v3.o: ../../include/openssl/safestack.h ../../include/openssl/sha.h
x509_v3.o: ../../include/openssl/stack.h ../../include/openssl/symhacks.h
x509_v3.o: ../../include/openssl/x509.h ../../include/openssl/x509_vfy.h
x509_v3.o: ../../include/openssl/x509v3.h ../cryptlib.h ../sgx.h x509_v3.c
x509_vfy.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_vfy.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_vfy.o: ../../include/openssl/buffer.h ../../include/openssl/conf.h
x509_vfy.o: ../../include/openssl/crypto.h ../../include/openssl/e_os2.h
x509_vfy.o: ../../include/openssl/ec.h ../../include/openssl/ecdh.h
x509_vfy.o: ../../include/openssl/ecdsa.h ../../include/openssl/err.h
x509_vfy.o: ../../include/openssl/evp.h ../../include/openssl/lhash.h
x509_vfy.o: ../../include/openssl/obj_mac.h ../../include/openssl/objects.h
x509_vfy.o: ../../include/openssl/opensslconf.h
x509_vfy.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_vfy.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_vfy.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_vfy.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_vfy.o: ../../include/openssl/x509_vfy.h ../../include/openssl/x509v3.h
x509_vfy.o: ../cryptlib.h ../sgx.h vpm_int.h x509_vfy.c
x509_vpm.o: ../../e_os.h ../../include/openssl/../sgx.h
x509_vpm.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509_vpm.o: ../../include/openssl/buffer.h ../../include/openssl/conf.h
x509_vpm.o: ../../include/openssl/crypto.h ../../include/openssl/e_os2.h
x509_vpm.o: ../../include/openssl/ec.h ../../include/openssl/ecdh.h
x509_vpm.o: ../../include/openssl/ecdsa.h ../../include/openssl/err.h
x509_vpm.o: ../../include/openssl/evp.h ../../include/openssl/lhash.h
x509_vpm.o: ../../include/openssl/obj_mac.h ../../include/openssl/objects.h
x509_vpm.o: ../../include/openssl/opensslconf.h
x509_vpm.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509_vpm.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509_vpm.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509_vpm.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509_vpm.o: ../../include/openssl/x509_vfy.h ../../include/openssl/x509v3.h
x509_vpm.o: ../cryptlib.h ../sgx.h vpm_int.h x509_vpm.c
x509cset.o: ../../e_os.h ../../include/openssl/../sgx.h
x509cset.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509cset.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
x509cset.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
x509cset.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
x509cset.o: ../../include/openssl/err.h ../../include/openssl/evp.h
x509cset.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
x509cset.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
x509cset.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509cset.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509cset.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509cset.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509cset.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h x509cset.c
x509name.o: ../../e_os.h ../../include/openssl/../sgx.h
x509name.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509name.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
x509name.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
x509name.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
x509name.o: ../../include/openssl/err.h ../../include/openssl/evp.h
x509name.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
x509name.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
x509name.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509name.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509name.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509name.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509name.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h x509name.c
x509rset.o: ../../e_os.h ../../include/openssl/../sgx.h
x509rset.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509rset.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
x509rset.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
x509rset.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
x509rset.o: ../../include/openssl/err.h ../../include/openssl/evp.h
x509rset.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
x509rset.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
x509rset.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509rset.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509rset.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509rset.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509rset.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h x509rset.c
x509spki.o: ../../e_os.h ../../include/openssl/../sgx.h
x509spki.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509spki.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
x509spki.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
x509spki.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
x509spki.o: ../../include/openssl/err.h ../../include/openssl/evp.h
x509spki.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
x509spki.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
x509spki.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509spki.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509spki.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509spki.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509spki.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h x509spki.c
x509type.o: ../../e_os.h ../../include/openssl/../sgx.h
x509type.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x509type.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
x509type.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
x509type.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
x509type.o: ../../include/openssl/err.h ../../include/openssl/evp.h
x509type.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
x509type.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
x509type.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
x509type.o: ../../include/openssl/pkcs7.h ../../include/openssl/safestack.h
x509type.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x509type.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x509type.o: ../../include/openssl/x509_vfy.h ../cryptlib.h ../sgx.h x509type.c
x_all.o: ../../e_os.h ../../include/openssl/../sgx.h
x_all.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
x_all.o: ../../include/openssl/buffer.h ../../include/openssl/conf.h
x_all.o: ../../include/openssl/crypto.h ../../include/openssl/dsa.h
x_all.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
x_all.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
x_all.o: ../../include/openssl/err.h ../../include/openssl/evp.h
x_all.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
x_all.o: ../../include/openssl/objects.h ../../include/openssl/ocsp.h
x_all.o: ../../include/openssl/opensslconf.h ../../include/openssl/opensslv.h
x_all.o: ../../include/openssl/ossl_typ.h ../../include/openssl/pkcs7.h
x_all.o: ../../include/openssl/rsa.h ../../include/openssl/safestack.h
x_all.o: ../../include/openssl/sha.h ../../include/openssl/stack.h
x_all.o: ../../include/openssl/symhacks.h ../../include/openssl/x509.h
x_all.o: ../../include/openssl/x509_vfy.h ../../include/openssl/x509v3.h
x_all.o: ../cryptlib.h ../sgx.h x_all.c
