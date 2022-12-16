Caffe-installation-steps
===================

removed cuda 6.0 and cuda 
Need protobuf, boost and caffe folders in your home folder.


How to use cuda ?
http://courses.cs.tau.ac.il/Caffe_workshop/Bootcamp/

Write the following in <b> /etc/environment </b> to set necesarry paths and library paths.

LD_LIBRARY_PATH=:/usr/local/cuda-5.5/lib64:/opt/OpenBLAS/lib:/opt/OpenBLAS/lib:/usr/lib64/atlas:/usr/local/lib:$HOME/protobuf-2.5.0/src/google/protobuf:$HOME/boost_1_55_0/stage/lib:/opt/rh/python27/root/usr/lib64/:/opt/rh/python27/root/usr/lib64/python2.7/config/:/usr/local/cuda-5.5/targets/x86_64-linux/lib/:/usr/local/lib

C_INCLUDE_PATH=:/opt/OpenBLAS/include:/usr/local/MATLAB/MATLAB_Production_Server/R2013a/extern/include:$HOME/caffe/include:/usr/local/cuda-5.5/targets/x86_64-linux/include:$HOME/boost_1_55_0:/opt/rh/python27/root/usr/include:/opt/rh/python27/root/usr/local/include/:/opt/rh/python27/root/usr/include/python2.7/


CPLUS_INCLUDE_PATH=:/opt/OpenBLAS/include:/usr/local/MATLAB/MATLAB_Production_Server/R2013a/extern/include:$HOME/caffe/include:/usr/local/cuda-5.5/targets/x86_64-linux/include:$HOME/boost_1_55_0:/opt/rh/python27/root/usr/include:/opt/rh/python27/root/usr/local/include/:/opt/rh/python27/root/usr/include/python2.7/

<br>

LD_INCLUDE_PATH=:/opt/OpenBLAS/include

<br>

PATH=$PATH:/usr/local/cuda-5.5/bin:/usr/lib64/qt-3.3/bin:/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin:/root/bin:/usr/local/MATLAB/MATLAB_Production_Server/R2013a/bin

The warning related to conflict between cuda 6.0 and cuda 5.5 was removed


Matlab Wrapper compilation:
The follow problem was because I was compiling inside matlab folder where matcaffe.cpp was present. You have to compile in Caffe folder.
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

To compile python wrapper, run the following command in caffe folder<br> 
LDFLAGS="-L/opt/rh/python27/root/usr/lib64" make pycaffe

<br>

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


<b>Feature Extraction:</b><br>

https://github.com/BVLC/caffe/issues/700  <br>
https://github.com/BVLC/caffe/issues/20  <br>
https://github.com/BVLC/caffe/issues/11 <br>


https://translate.google.com/translate?sl=zh-CN&tl=en&js=y&prev=_t&hl=en&ie=UTF-8&u=bean.logdown.com%2Fposts%2F211192-caffe-use-caffe-to-extract-features-of-each-layer&edit-text=   <br>

" Unable to import argparse "  is shown in python 2.6, use python 2.7 to get rid of this. <br> 


