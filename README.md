Caffe-installation-
===================

removed cuda 6.0 and cuda 


How to use cuda ?
http://courses.cs.tau.ac.il/Caffe_workshop/Bootcamp/

Write the following in <b> /etc/environment </b> to set necesarry paths and library paths.

LD_LIBRARY_PATH=:/usr/local/cuda-5.5/lib64:/opt/OpenBLAS/lib:/opt/OpenBLAS/lib:/usr/lib64/atlas:/usr/local/lib:/root/protobuf-2.5.0/src/google/protobuf
C_INCLUDE_PATH=:/opt/OpenBLAS/include:/usr/local/MATLAB/MATLAB_Production_Server/R2013a/extern/include:/caffe/include:/usr/local/cuda-5.5/targets/x86_64-linux/include
CPLUS_INCLUDE_PATH=:/opt/OpenBLAS/include:/usr/local/MATLAB/MATLAB_Production_Server/R2013a/extern/include:/caffe/include:/usr/local/cuda-5.5/targets/x86_64-linux/include
<br>
LD_INCLUDE_PATH=:/opt/OpenBLAS/include
<br>
PATH=$PATH:/usr/local/cuda-5.5/bin:/usr/lib64/qt-3.3/bin:/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin:/root/bin:/usr/local/MATLAB/MATLAB_Production_Server/R2013a/bin

The warning related to conflict between cuda 6.0 and cuda 5.5 was removed


Matlab Wrapper compilation:

Warning!! Warning!! Warning!!

If you get the following error -

/usr/lib/gcc/x86_64-redhat-linux/4.4.7/../../../../lib64/crt1.o: In function `_start': (.text+0x20): undefined reference to `main'

then run the following command:<b>This solution leads to error in caffe make all step </b><br>
 
<br>
g++ -shared -fPIC matcaffe.cpp -o matcaffe 
This gives segmentation fault

<br>
Now go to caffe folder and then
<br>
CPLUS_INCLUDE_PATH=

but while running 
<br>
make runtest -j16


installed python 2.7  at /usr/src/Python-2.7.5
http://tecadmin.net/install-python-2-7-on-centos-rhel/


Help seeked <br>
https://github.com/BVLC/caffe/issues/972

Devtools 2 installed 
gcc 4.8.1 installed 
http://linux.web.cern.ch/linux/devtoolset/#install

/opt/rh/devtoolset-2/root/usr/bin/gcc --version
run following command to use gcc4.8  <br>
<b>scl enable devtoolset-2 bash</b>

