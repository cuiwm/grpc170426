# grpc170426
fork 20170426
third_party/boringssl/crypto/asn1/../internal.h:121:22: error: stdalign.h: No such file or directory

grpc#make 
error: third_party/boringssl/crypto/asn1/../internal.h:121:22: error: stdalign.h: No such file or directory


https://www.gnu.org/software/gnulib/manual/html_node/stdalign_002eh.html

解决办法 CC=/opt/gcc-4.9.2/rtf/bin/gcc make -j32

引起的原因:  参考 cygwin遇到的错误, 推测是gcc版本的问题, grpc和borringssl(cmake)选择的版本不一致??? 有空再研究吧
choe: boringssl是用cmake编译的,   我的env : gcc 4.47  gcc4.92 gcc 7.10 3个版本, 

The error is because your gcc-core package and gcc-g++ are not of the same version. Either downgrade one of them to solve the problem or update both the libraries. Updating both the libraries is the recommended way.
