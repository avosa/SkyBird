## About SkyBird App
SkyBird is a game application still in process of developing using Kivy, a python framework that when fully done can be deployed on both Android and iOS gadgets.


Buildozer is a tool that automates the entire build process. It downloads and sets up all the prequisites for python-for-android, including the android SDK and NDK, then builds an apk that can be automatically pushed to the device.

Buildozer currently works only in Linux, and is an alpha release, but it already works well and can significantly simplify the apk build.

You can get its repo on [Github:](https://github.com/kivy/buildozer)

```text
$ git clone https://github.com/kivy/buildozer.git

$ cd buildozer

$ sudo python setup.py install if using python 2 and sudo python3 setup.py install for python3
```
This will install buildozer in your system. Afterwards, navigate to your project directory and run:

```text
$ buildozer init
```

This creates a buildozer.spec file controlling your build configuration. You should edit it appropriately with your app name etc. You can set variables to control most or all of the parameters passed to python-for-android.

Install buildozer’s [dependencies.](https://buildozer.readthedocs.io/en/latest/installation.html#targeting-android)

Finally, plug in your android device and run:
```text
$ buildozer android debug deploy run
```
to build, push and automatically run the apk on your device.


For iOs you need to install some dependencies, like Cython, autotools, etc. I encourage you to use Homebrew to install those dependencies:
```text
$ brew install autoconf automake libtool pkg-config

$ brew link libtool

$ sudo easy_install pip

$ sudo pip install Cython==0.29.10
```
For more detail, see [IOS Prerequisites.](https://kivy.org/doc/stable/guide/packaging-ios-prerequisites.html#packaging-ios-prerequisites) Just ensure that everything is ok before starting the second step!

#### Compile the distribution
Open a terminal on iOS, and type:
```text
$ git clone git://github.com/kivy/kivy-ios
$ cd kivy-ios
$ ./toolchain.py build kivy
```
More information can be found on [Kivy Official Website](https://kivy.org/doc/stable/guide/packaging-ios.html)
