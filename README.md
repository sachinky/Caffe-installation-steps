Caffe-installation-
===================
Write the following in <b> /etc/environment </b> to set necesarry paths and library paths.

LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-5.5/lib64:/opt/OpenBLAS/lib:/opt/OpenBLAS/lib:/usr/lib64/atlas:/usr/local/lib:/root/protobuf-2.5.0/src/google/protobuf
C_INCLUDE_PATH=$C_INCLUDE_PATH:/opt/OpenBLAS/include:/usr/local/MATLAB/MATLAB_Production_Server/R2013a/extern/include:/caffe/include:/usr/local/cuda-5.5/targets/x86_64_linux/include
CPLUS_INCLUDE_PATH=$CPLUS_INCLUDE_PATH:/opt/OpenBLAS/include:/usr/local/MATLAB/MATLAB_Production_Server/R2013a/extern/include:/caffe/include:/usr/local/cuda-5.5/targets/x86_64_linux/include
LD_INCLUDE_PATH=:/opt/OpenBLAS/include
PATH=$PATH:/usr/local/cuda-5.5/bin:/usr/lib64/qt-3.3/bin:/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin:/root/bin:/usr/local/MATLAB/MATLAB_Production_Server/R2013a/bin

The warning related to conflict between cuda 6.0 and cuda 5.0 was removed


Matlab Wrapper compilation:

Warning!! Warning!! Warning!!

If you get the following error -

/usr/lib/gcc/x86_64-redhat-linux/4.4.7/../../../../lib64/crt1.o: In function `_start': (.text+0x20): undefined reference to `main'

then run the following command:<b>This solution leads to error in caffe make all step </b>
g++ -shared -fPIC matcaffe.cpp -o matcaffe.o


removed cuda 6.0 and cuda 
make all not working in /caffe
