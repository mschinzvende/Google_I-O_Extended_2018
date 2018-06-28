# Google_I-O_Extended_2018
Object Recognition in video using TensorFlow &amp; OpenCv

This tutorial will focus on how you can detect various objects in a video stream, either live or pre-recorded, using the TensorFlow Object Detection Library.
In order to recognise vaious objects in a video, we will make use of pre-trainned models available in the <a href="https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md">TensorFlow Model Zoo</a>

In-order to succssefully run this tutorial, you need to have the following in place:

1. Ubuntu 16.04 LTS
2. TensorFlow
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

Verify that tensorflow has been successfully installed

<code> python3</code><br>
<code>>>import tensorflow as tf</code><br>

If you don't get an import error, it means that TensorFlow has been successfully installed. If you get the <code>Illegal instruction</code> error, try downgrading your TensorFlow to version 1.5.

<code> pip3 unistall tensorflow</code><br>
<code> pip3 install tensorflow==1.5</code>

If this does not work, you need to <a href="https://www.tensorflow.org/install/install_sources">build TensorFlow from source</a>.

The next step is to install the OpenCv library (OpenCv 3.3). I prefer building OpenCv from source because the pip installation presented some troubles when working with TensorFlow. To build OpenCv from source, you do the following:








