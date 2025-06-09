Google Authenticator(2FA)

```
git https://github.com/google/google-authenticator-libpam

unzip google-authenticator-libpam-master.zip

cd /google-...zip
```

```bash
[root@localhost google-authenticator-libpam-master]# ./bootstrap.sh 

./bootstrap.sh: line 15: exec: autoreconf: not found

[root@localhost google-authenticator-libpam-master]# yum -y install autoconf


[root@localhost google-authenticator-libpam-master]# ./bootstrap.sh 
Can't exec "aclocal": No such file or directory at /usr/share/autoconf/Autom4te/FileUtis.pm line 326.
autoreconf: failed to run aclocal: No such file or directory

[root@localhost google-authenticator-libpam-master]# yum -y install libtool

[root@localhost google-authenticator-libpam-master]# ./configure 
checking whether make supports nested variables... yes
......
configure: error: Unable to find the PAM library or the PAM header files

[root@localhost google-authenticator-libpam-master]# yum -y install pam-devel   

[root@localhost google-authenticator-libpam-master]# ./configure 
checking whether make supports nested variables... yes
checking for gcc... gcc
checking whether the C compiler works... yes
checking for C compiler default output file name... a.out
checking for suffix of executables... 
......
  google-authenticator version 1.10
  Prefix.........: /usr/local
  Debug Build....: 
  C Compiler.....: gcc -g -O2 -Wall 
  Linker.........: /usr/bin/ld -m elf_x86_64

[root@localhost google-authenticator-libpam-master]# make
make  all-am
make[1]: Entering directory '/root/google-authenticator-libpam-master'
  CC       src/google-authenticator.o
  CC       src/util.o
  CC       src/base32.o
  CC       src/hmac.o
  CC       src/sha1.o
  CCLD     google-authenticator
  CC       src/base32_prog.o
  CCLD     base32
  CC       src/pam_google_authenticator_la-pam_google_authenticator.lo
  CC       src/pam_google_authenticator_la-util.lo
  CC       src/pam_google_authenticator_la-base32.lo
  CC       src/pam_google_authenticator_la-hmac.lo
  CC       src/pam_google_authenticator_la-sha1.lo
  CCLD     pam_google_authenticator.la
make[1]: Leaving directory '/root/google-authenticator-libpam-master'

[root@localhost google-authenticator-libpam-master]# make install
make[1]: Entering directory '/root/google-authenticator-libpam-master'
......
make[1]: Leaving directory '/root/google-authenticator-libpam-master'

[root@localhost google-authenticator-libpam-master]# google-authenticator
```

```bash
Failed to use libqrencode to show QR code visually for scanning.
# install qrencode （无效）
```
