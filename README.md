# QWebEngine Module from Qt 5.13.0rc with Proprietary codecs support
We try to Snap package Qt app built using QWebEngine module from Qt 5.13.0rc with proprietary codec support. (which is not yet released in market)

# Preview
![enter image description here](https://pbs.twimg.com/media/D8dvylyUEAE_pJa.jpg:large)

# How to snap the app

 1. extract appdir.zip 
 2. run `snapcraft prime`
 3. once snapcraft prime is done run `snap try`
 4. run `webengine` to test the app

# What works
QWebEngine works fine as expected.

# Current issues

 1. File Dialog (QFileDialog class) is not working. (Not opening any dialog when app is packaged in snap confine). It works fine without confinements. You can check it by running appdir/usr/bin/simplebrowser clicking File->Open or Webpage's context menu "Save page" action.

**This issues has been reported by many snapcrafters before  <sup id="a1">[1](#f1)</sup>  <sup id="a2">[2](#f2)</sup>**

# Debug snap package
while running the `webengine` run the following in another terminal to watch apparmor denials.

    sudo snappy-debug.security scanlog

# What is inside appdir ?
appdir contains deployed qt app simplebrowser (from examples of qwebenginewidgets).
I configured and managed to deploy it using various tools to run according to provided libraries and other required stuffs by qt.
So all i did is dumped it into snap package with some other required libraries using snapcraft with `desktop-gtk3` desktop-helper.

# Use of the project
The project can help so many people who want try build Apps on Latest Qt framework in market . i.e, Qt 5.13.0.rc which is not even released yet (Release candidate going to release soon). 
WebEngine module was chosen because it efficient than Electron, NodeWebkit (nwjs) and other chrommium based frameworks in all aspects,(Memory consumption to support for rich Qt APIs)
Developers can build better apps with Qt and Webengine which is based on Chromium.

 

<b id="f1">1</b> [# QFileDialog - not rendered (Ubuntu, PyCharm installed using snap)](https://github.com/ubuntu/snapcraft-desktop-helpers/issues/167) [↩](#a1)

<b id="f2">2</b> [# File open/save dialogs show $SNAP_USER_DATA instead of $HOME when selecting the home shortcut](https://bugreports.qt.io/browse/PYSIDE-912) [↩](#a2)

# Other Refrences
 1. [Firefox snapcraft.yaml](https://github.com/mozilla/gecko-dev/blob/master/taskcluster/docker/firefox-snap/snapcraft.yaml.in)
 2. [Chromium snapcraft.yaml](https://git.launchpad.net/~chromium-team/chromium-browser/+git/snap-from-source/tree/snapcraft.yaml?h=stable)

