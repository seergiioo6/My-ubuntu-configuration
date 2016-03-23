Screencasting
=============

Requirements
------------

* Install ffmpeg

 sudo apt-get install ffmpeg

Installation
------------

* Copy screencast & stopcast to /usr/bin

Configuration
-------------

* Goto Keyboard Shortcuts
* Add new Shortcut:
 * Record Screencast Ctrl+Alt+R (screencast)
 * Stop Screencast Shift+Ctrl+Alt+R (stopcast)

Guide
-----

* To start Recording press Ctrl+Alt+R. (A popup will ask verification to record before any action)
* To stop Recording press Shift+Ctrl+Alt+R. (A popup will notify upon a succesful stop of recording)

The Videos are recorded at ~/Videos/ directory with a timestamp suffix under the name screencast-$DATE.mkv

The current dimensions are 1600x876 (The recording is not capturing the top bar, thus the missing 14 pixels)
