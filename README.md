# QWebEngine Module from Qt 5.13.0rc with Proprietary codecs support
We try to Snap package Qt app built using QWebEngine module from Qt 5.13.0rc with proprietary codec support. (which is not yet released in market)

# How to snap the app

 1. extract appdir.zip 
 2. run `snapcraft prime`
 3. once snapcraft prime is done run `snap try`
 4. run `webengine` to test the app

# What works
QWebEngine works fine as expected.

# Current issues

 1. File Dialog (QFileDialog class) is not working. (Not opening any dialog when app is packaged in snap confine). It works fine without confinements. You can check it by running appdir/usr/bin/simplebrowser clicking File->Open or Webpage's context menu "Save page" action.  
**This issues has been reported by many snapcrafters before [^1] [^2]**

# Debug snap package
while running the `webengine` run the following in another terminal to watch apparmor denials.

    sudo snappy-debug.security scanlog

# What is inside appdir ?
appdir contains application containing qt app simplebrowser (from examples of qwebenginewidgets).
I configured it using various tools to run according to provided libraries and other required stuffs by qt.
So all i did is dumped it into snap package with some other required libraries using snapcraft with `desktop-gtk3` desktop-helper.

# Use of the project
The project can help so many people who want try build Apps on Latest Qt framework in market . i.e, Qt 5.13.0.rc which is not even released yet. 
WebEngine module was chosen because i want see it efficient than Electron and NodeWebkit in all aspects,(Memory consumption to rich Qt APIs)
Developers can build better apps with with Qt and Webengine which is based on Chromium. so its like Chromium + Qt .  

[^1]: [# QFileDialog - not rendered (Ubuntu, PyCharm installed using snap)](https://github.com/ubuntu/snapcraft-desktop-helpers/issues/167)
[^2]: [# File open/save dialogs show $SNAP_USER_DATA instead of $HOME when selecting the home shortcut](https://bugreports.qt.io/browse/PYSIDE-912)

