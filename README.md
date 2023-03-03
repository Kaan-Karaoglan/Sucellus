# Sucellus
Fire Detection in Python 

Bu projenin yazıldığı IDE ANACONDA SPYDER olup SPYDER'ın
ileri versiyonlarında sorun çıkartabildiğinden dolayı
ANACONDA kullanan birinin öncelikle şu işlemleri yapması gerekir

Step 1 — Create New Conda Environment

Tensorflow didn’t work with Python 3.6 for me, but I was able to get all packages working with 3.5.3. Luckily Anaconda has a really cool feature called ‘environments’ that allows more than version of Python to be installed in a different environments, each with different packages installed as you see fit. So you could have one environment for the sole purpose of these tutorials if you wanted, and it won’t mess up your default Python install. This allows us to keep 3.6 as the default Python, whilst installing an older version, as well, for use with tensorflow.

To create the new environment called ‘py35’ open up the Windows command prompt and type:

conda create -n py35 python=3.5 anaconda

Call the environment whatever you want

Note: This automatically installs python 3.5 in the new environment.

Step 2 — Install Spyder in the New Environment

We can now start adding stuff to this environment. To do this, first activate the environment by typing the following into the command prompt:

activate py35

The command prompt should now change to have a (py35) at the beginning of each line. This indicates that we're working in the new py35 environment.

We can’t actually use the version of Spyder that is already installed with the default Python. Running this version of Spyder will automatically use the default version of Python.

So we need to install Spyder within the new environment:

conda install spyder

Step 3 — Install the Packages

Once spyder has been installed we can install the relevant packages. Again we need to be in the relevant environment, so type:

activate py35

if needs be. Then type:

conda install theano

conda install tensorflow

conda install keras

Hopefully this should complete without errors.

If you’re having trouble getting tensorflow to work try:

pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/windows/cpu/tensorflow-1.1.0-cp35-cp35m-win_amd64.whl
https://www.tensorflow.org/install/install_windows

Also note that, when importing theano in Spyder, I got a message in the IPython console saying that I should install m2w64-toolchain to greatly improve performance. For me, this stopped theano from working and uninstalling m2w64-toolchain didn’t fix the issue. I had to create a new environment and reinstall everything from scratch. Others may have better luck with m2w64-toolchain, but I had problems with it. I’d recommend cloning your environment and installing this on the cloned environment to test it first.

If you want the fancy GPU version of tensorflow, just type:

pip install --upgrade https://storage.googleapis.com/tensorflow/windows/gpu/tensorflow_gpu-0.12.1-cp35-cp35m-win_amd64.whl
as from the site:

https://www.tensorflow.org/versions/r0.12/get_started/os_setup

I actually had trouble getting this GPU version of tensorflow to work, but this method matches what I’ve seen online. One tip I can give regarding the gpu version is that I had better luck when I used pip install for all the above packages, rather than conda install . Things got a little complicated though, as to get the gpu version working I needed to install cuDNN from https://developer.nvidia.com and configure it correctly. So I just stuck with the cpu version for now.

Step 4 — Run Spyder from the Environment

In order to make sure that we’re using Spyder with the relevant version of Python (version 3.5.3, with the packages installed in the last step), type:

activate py35

if you’re not already in the environment, and then type:

spyder

to launch Spyder using Python 3.5.

In the IPython console, you should see Python 3.5.3 in the top line.

Step 5 — Test the Packages

As a cursory check that the packages are working, you can try running the following from within ann.py in Spyder:

import theano
import tensorflow
import keras
If the IPython console doesn’t spit out any error messages you’re probably good.

Note1: The downside of this method is that, everytime you want to use Spyder, in order to make sure it’s working with the correct version of Python (3.5 rather than the default 3.6 installation) you would have to open up a command prompt and run:

activate py35

followed by:

spyder

to launch Spyder.

There’s probably a way to get Spyder to link to the correct environment from within Spyder’s user interface, but after tinkering about I decided the above method was easier.

I think being able to organise different Python installs into different environments more than makes up for having to do some stuff in the command prompt.

Note 2: Because a new environment is created some of the packages will need installing:

activate py35

pip install matplotlib

pip install pandas

pip install sklearn

Best of Luck!

Note: This is not my own, this is accumulated from multiple resource, specially from Udemy course discussion on installation. It’s difficult to access discussion of paid courses so I thought of putting it here.

Thanks,

Pushkar Mandot https://medium.com/@pushkarmandot/installing-tensorflow-theano-and-keras-in-spyder-84de7eb0f0df

Bu işlemlerden sonra ekstra olarak kurduğumuz environmenta matplotlib ve pandas ı tekrardan 

activate py35

pip install pandas

pip install matplotlib 

yaparak ekleyip

Son olarak kurduğumuz yeni environmentı açarak çalıştırıyoruz
