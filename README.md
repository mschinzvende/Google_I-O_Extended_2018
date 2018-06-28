# Google_I-O_Extended_2018
Object Recognition in video using TensorFlow &amp; OpenCv

This tutorial will focus on how you can detect various objects in a video stream, either live or pre-recorded, using the TensorFlow Object Detection Library.
In order to recognise vaious objects in a video, we will make use of pre-trainned models available in the <a href="https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md">TensorFlow Model Zoo</a>

In-order to succssefully run this tutorial, you need to have the following in place:

1. Ubuntu 16.04 LTS
2. TensorFlow - CPU Version
3. OpenCv
4. Python3.x

These requirements constitute the prefered environment to run the tutorial. You can be able to run the tutorial using any other versions of the software, different from what is outlined.

The goal of this tutorial is to show you how you can use the TensorFlow framework in a real life situation. Hopefully you will be able to grasp one or two concepts then you build from there.

Let us begin

After installing your linux environment (Ubuntu 16.04 LTS), Open the terminal (CTRL+ALT+T) and run the following commands as the root user.

<code>sudo -i</code>

Running the comands as root, execute the following:

<code>apt-get update</code><br>
<code>apt-get dist-upgrade</code>

Make sure the correct python3 packages are installed

<code> apt-get install python3</code><br>
<code> apt-get install python3-pip</code>

Install TensorFlow
<code>pi3 install tensorflow</code>

To install Tensorflow on a GPU or another OS, refer to the <a href="https://www.tensorflow.org/install/">official installation guide</a>

Verify that tensorflow has been successfully installed

<code> python3</code><br>
<code>>>import tensorflow as tf</code><br>

If you don't get an import error, it means that TensorFlow has been successfully installed. If you get the <code>Illegal instruction</code> error, try downgrading your TensorFlow to version 1.5.

<code> pip3 unistall tensorflow</code><br>
<code> pip3 install tensorflow==1.5</code>

If this does not work, you need to <a href="https://www.tensorflow.org/install/install_sources">build TensorFlow from source</a>.

The next step is to install the OpenCv library (OpenCv 3.3). I prefer building OpenCv from source because the pip installation presented some troubles when working with TensorFlow. To build OpenCv from source, you run the following:


<code> apt-get install --assume-yes build-essential cmake git </code><br>
<code> apt-get install --assume-yes pkg-config unzip ffmpeg qtbase5-dev python-dev python3-dev python-numpy python3-numpy</code><br>
<code> apt-get install --assume-yes libopencv-dev libgtk-3-dev libdc1394-22 libdc1394-22-dev libjpeg-dev libpng12-dev libtiff5-dev libjasper-dev</code><br>
<code> apt-get install --assume-yes libavcodec-dev libavformat-dev libswscale-dev libxine2-dev libgstreamer0.10-dev libgstreamer-plugins-base0.10-dev </code><br>
<code> apt-get install --assume-yes libv4l-dev libtbb-dev libfaac-dev libmp3lame-dev libopencore-amrnb-dev libopencore-amrwb-dev libtheora-dev </code><br>
<code> apt-get install --assume-yes libvorbis-dev libxvidcore-dev v4l-utils vtk6 </code><br>
<code> apt-get install --assume-yes liblapacke-dev libopenblas-dev libgdal-dev checkinstall </code><br>

To install OpenCv for GPU Support you need to install the NVIDIA Cuda Toolkit with CUDNN library, see <a href="https://github.com/BVLC/caffe/wiki/Ubuntu-16.04-Installation-Guide#the-gpu-support-prerequisites"> the guide </a>

Download the latest source archive for OpenCV 3.3 from <a href="https://github.com/opencv/opencv/archive/3.3.0.zip">here</a> or run the following command:

<code> wget https://github.com/opencv/opencv/archive/3.3.0.zip </code><br>

After the download has unpack the zip file finished run:

<code> unzip 3.3.0.zip </code><br>
enter the unpacked directory:
<code> cd opencv-3.3.0 </code><br>

Inside the unpacked directory execute:
<code> mkdir build </code><br>
<code> cd build <code><br>

<code> cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D FORCE_VTK=ON -D WITH_TBB=ON -D WITH_V4L=ON -D WITH_QT=ON -D WITH_OPENGL=ON -D WITH_CUBLAS=ON -D CUDA_NVCC_FLAGS="-D_FORCE_INLINES" -D WITH_GDAL=ON -D WITH_XINE=ON -D BUILD_EXAMPLES=ON .. </code><br>

<code> make -j $(($(nproc) + 1)) </code><br>

You have completed the build proceedure. To install OpenCv execute:<br>

<code> make install </code><br>
<code> /bin/bash -c 'echo "/usr/local/lib" > /etc/ld.so.conf.d/opencv.conf' </code><br>
then
<code> ldconfig </code><br>
then
<code> apt-get update </code><br>

You have installed the OpenCv library. Now reboot your system.









