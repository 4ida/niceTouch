# niceTouch
Easily calibrate multiple touch and non touch screens on a single linux system.

<b>NOTE: Xorg only, not wayland</b>, thus for now don't expect your pinephones to work nicely with touchscreen capable lapdocks :c<br>
Wayland doesn't seem to have a way to calibrate and fixup touch stuff?

Ideally Linux should associate touchscreen with specific display, kinda like windows already does, no hassle if you flip (rotate) screen, or change
which is main display, how displays are placed etc.. (same reason why I can't put Linux on kinda old Windows 8 Intel Atom based tablet, its bc default rotation is phone-like vertical, and tablet has one port for data and charging, battery isn't super good, can't use it much, either charge it or use it with wired keyboard/mouse/etc)

## Use

For best results, read [how to use it](docs/howToUseIt.md).

* First run it with the least number of sccreen/touchpanels connected. - Preferably, one connected pair.
* Now connect your next screen/touchpannel pair and run it again.
  * Repeat until all your displays are connected.

Every time you connect a screen that doesn't have a corresponding touchpanel, you will need to wait at least 10 seconds before proceeding to the next step.

Eg

    $ nt
    Calibrate: touchPanel 9 to screen eDP-1

Then I plug in an HDMI/USB touch screen, and run it again.

    $ nt
    Calibrate: touchPanel 14 to screen HDMI-1
    Calibrate: touchPanel 9 to screen eDP-1

Soon, I want to have this running as a service listening to DBUS so that it will automatically calibrate all touch screens as soon as something changes. See [TODOs](docs/todos.md).

## Install

Most people

    sudo pip install niceTouch

Developers

    sudo python ./setup installl


### Pre-requisites
* Python 3
* xorg: xrandr, xinput

## Contributions/Progress

See [TODOs](docs/todos.md) for stuff that needs doing and what I'm focussing on.

Feel free to

* Create [issues](https://github.com/ksandom/niceTouch/issues) to report bugs or suggestions.
* [Pull requests](https://github.com/ksandom/niceTouch/pulls)
  * Fix bugs
  * Add features
