# Changelog

### 2024-10-15 (Meanwhile 2024-1o)
* fixed: Endstops should work again as expected! (Thanks Unus!)
* fixed: Link to show how to configure your messaging bot (Telegram)
* You can now configure your shield (green or black) just by selecting it in the "settings" section. Default is Green. No reason to think in pins...
* The root filesystem will expand itself without user intervention,no matter what happens...
* Added: You can now see in the header part of the interface wich version and branch of the meanwhile openscan you are running (side to the power/restart buttons)
* Added the possibility to change the order of the axis that moves first, the rotor or the turntable. This can help eliminate vibrations in the moment of taking the photo without adding more delays (magic sleeps).
* Added the possibility to delete the aborted (unterminated) scan sessions automatically. (But behaviour is to keep the aborted sessions by default)
* Added a visual help in form of a test chart (thanks uk_25) in the preview photo position in case no camera (arducam) has been detected. I hope this helps to troubleshot better what is going on
* Addded an "export configuration" option in updates and Info section. The "import configuration" is not ready yet :)
* Added statistics: When you scan, some statistics about your configuration and results (ok/bad) will be stored. 

### 2024-09-14 (Meanwhile 2024-11s)
* fixed: shutdown and reboot button in the UI
* Added Swagger UI to help build, design and document the API
* Fixed the FKMSGate
* New update mechanism: Releases have their own version with their own stable, beta and meanwhile flavours.

### 2024-02-26 (Meanwhile 2024-23f)
* Fixed: Without telegram configured it was impossible to finish a scan (hanged on finish). But who in their sanity would not use telegram if available right?
* After a reboot/shutdown, if you forgot to close that tab it will not trigger a disaster when you are scanning in the future

### 2024-02-23 (Meanwhile 2024-23f)

This is the beginning of a fork. After several attempts to add a feature and get silence as response I have decided to create my own OpenScan fork.
* added: When doing a focus stack session you can store the contents inside the zip with all the photos sorted in their own folder. Some focus stacking applications will benefit from this. 
* added: [You can now get alerts on Telegram](Telegram.md) when the session starts and the session ends
* fixed: The "delete all files" operation no longer prevents the refresh of the file list

### 2022-05-19 documentation
* changed: overall structure --> the OpenScan2 repository will serve as a central hub for all informations concerning OpenScan (i.e. firmware, hardware, tutorials ...)

### 2022-05-11 beta
* added: changelog and version (finally ;)
* added: create an update using the node-red-backend inject node ("create beta" and "prepare image creation" in "update" tab)
* fixed: Error handling in flask (when no preview is taken)
* fixed: Error when upload failed + node red restarted (multiple instances of curl)
* fixed: When closing the browser session/missing the popup after the routine, the data set got lost (if this happens, just restart the device and it will be moved to the right location)
### 2022-04-26 beta 
* added: donation button ;)
* fixed: the wonderful camera position algorithm was faulty and a bit inefficient
* fixed: downscaling the preview image caused the preview to disappear (when crop value was to high)
* fixed: delay_before and delay_after are now properly applied, so that you can set a delay before/after taking a photo
* fixed: updates might crash the selected camera --> it is now necessary to re-select the camera after certain updates
### 2022-04-21 beta
* added: timer (ETA) until a routine is done
* added: showing progress, while files are being split (before uploading to OpenScanCloud)
* added: infotexts (FINALLY :)
* added: several stats/device information
* fixed: combining two sets did not delete the smaller set
### 2022-04-20 beta & main
* !fixed: pi cameras (v1.3, v2.1 and HQ) finally work and can be simply selected in the settings menu
* !fixed: Raspberry Pi 3B+ and 4 work! (the main limiting factor now is the RAM, where at least 1GB RAM is needed)
* fixed: live preview sometimes did not work. This has been a network speed issue and has been solved by downscaling the image (resolution can be set)
* fixed: it is now possible to delete individual sets.
* fixed: it is now possible to use all LEDs.
* added: Turntable mode (disable the second axis)
* added: Pause scan. You can pause and un-pause the scan by simply pressing the button
* added: second scan pass. When one scan is done, you can immediately run a second pass. This is especially useful, if you want to re-orient the object
* added: auto-timeout. Turn off the ringlight (todo: and motors) after 300 seconds (value can be set)
* added: diskspace warning. When free diskspace drops below a given threshold (4GB by default), a warning message will appear
* changed: new background image, minor design changes
* changed: log file can be easily generated and downloaded by clicking a button (update&info tab)