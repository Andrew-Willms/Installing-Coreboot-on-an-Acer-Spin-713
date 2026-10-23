# Attribution and Purpose

This work is based on [MrChromebox's Firmware Utility Script](https://docs.mrchromebox.tech/) and the accompanying [guide](https://docs.mrchromebox.tech/docs/getting-started.html) and forther work by [expitau](https://gist.github.com/expitau/9a599fb988d146b66c38c5b01693e201). I created this guide to document the process for my future reference and because I thought a more specific and detailed guide might benefit others.

# Hareware Specifics

I performed this process on a set of Acer Spin 713 Chromebooks. Some details, such as keyboard and BIOS layout, may be specific to this model of Chromebook, but the majority of the process should be largely similar on other devices.

# Procedure

## 1. Complete Minimal Device Setup
This is necessary to access a point where your Chromebook can factory reset. Even if the Chromebook displays a screen saying "Welcome to your Chromebook" and appears to already be factory reset, it may still have organization policies that prevent you from accessing developer mode.

1. First, press the "Get started" button in the bottom left.

2. On the next screen, select your wifi network and enter the password.

3. On the next screen, select the "For personal use" option and press the "Next" button in the bottom right.

3. On the next screen, agree to the policy and opt out of the data sharing????

4. You should be presented with a screen saying "Who's using this Chromebook?".

## 2. Factory Reset the Chromebook
As discussed above, factory resetting the Chromebook ensures you have access to developer mode.

1. While on the screen saying "Who's using this Chromebook?", press <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>R</kbd>. You should be presented with a screen saying "Reset this Chromebook".

3. Press the "Powerwash" button in the bottom right and press "Continue" on the dialog that pops up. The Chromebook should reboot to a screen saying "Welcome to your Chromebook".

## 3. Boot into Developer Mode
This will allow you to run commands as root.

1. First, reboot the device in Recovery Mode. To do this, hold <kbd>Esc</kbd> + <kbd>Refresh</kbd> (this is the button in the <kbd>F3</kbd> position) then press and hold the power button until the Chromebook reboors. The Chromebook should reboot and show a screen prompting you to "Please insert a recovery USB stick or SD card".

3. Press <kbd>Ctrl</kbd> + <kbd>D</kbd>. This should result in a screen saying "To turn OS verification OFF, press ENTER".

4. Press <kbd>Enter</kbd>. You should be shown a screen saying "OS verification is OFF". If you are shown a screen saying "Developer mode is disabled on this device by system policy" you likely didn't successfully factory reset the Chromebook.

5. Press <kbd>Ctrl</kbd> + <kbd>D</kbd> and the device should reboot into developer mode.

## 4. Restore Internet Access
Because you just reset your Chromebook, it no longer has access to the internet. You need to give it access to the internet again before you run the necessary commands in the terminal.

1. First, press the "Get started" button in the bottom left.

2. On the next screen, select your wifi network and enter the password.

## 5. Terminal Commands
This is where you execute the commands to update the firmware.

1. In the previous step your Chromebook should have rebooted and should be showing the "Welcome to your Chromebook" screen. On this screen (this will also likely work from any version of the log in screan), press + <kbd>Ctrl</kbd> + <kbd>ALt</kbd> + <kbd>Search</kbd> (presumably in lew of a <kbd>Fn</kbd> key) + <kbd>Browser Forward</kbd> (the key in the <kbd>F2</kbd> position). This should open a full screen terminal with the most recent line reading "localhost login:".

2. Type `chronos` and press <kbd>Enter</kbd>.

3. Type `curl -LO mrchromebox.tech/firmware-util.sh` and press enter.