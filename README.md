Kivy Raspberry Pi Installer
---

In this git repository is a script that enables the easy installation of the kivy framework on the Raspberry Pi.

The script is adapted from the instructions at http://kivy.org/docs/installation/installation-rpi.html and https://github.com/mrichardson23/rpi-kivy-screen

## Pre Installation

Ensure that you firstly do

    chmod +x install_kivy_rpi
  
Then, to kick the script off, simply type

    ./install_kivy_rpi
  
## Post Installation

If you want the script to work with the new Raspberry Pi touch display, you will need to edit the config file for Kivy and add the touchscreen as a HID.

This is very simple

     nano ~/.kivy/config.ini

Then, find the `[input]` section, remove the existing lines and replace them with these

    mouse = mouse
    mtdev_%(name)s = probesysfs,provider=mtdev
    hid_%(name)s = probesysfs,provider=hidinput
