# LinuxCNC setup for Stepcraft 420

![alt text](https://github.com/JanezCim/LinuxCNC-Stepcraft420/blob/master/IMG_20180202_191453.jpg)

This is a full setup for a Stepcraft 420 machine with LinuxCNC. It could be any Stepcraft size, but you should change the config accordingly. This setup has been running on my machine since August 2017 without troubles, but I don't guarantee it woking for everyone.

This setup has some custom buttons on the right that I find usefull:
1. **Rapid to Home**: dont press this. This is still a bug
2. **z-probe-offset**: pressing this, the machine will start decend on Z axsis untill it hits the probe. It sets that height to offset of 9.95mm (the size of my aluminium block used as probe). This can be changed in `z_tool_offset_measure.ngc`
3. **z-probe-zero** : same as z-probe-offset, but without offset. Sets the height to 0 (usefull for PCBs)
4. Circle light is red when probe sensor is not triggered and green when it's triggered (for checking for contact)




## Simple setup (just by cloning)
1. Clone this repo to `/home/<YOUR_USERNAME>/linuxcnc/configs`
2. Copy the map  `custom_commands` into `/home/<YOUR_USERNAME>/linuxcnc/`
3. Open  `/home/<YOUR_USERNAME>/linuxcnc/stepcraft420/config/SC420.ini` and under the flag `[RS274NGC]` change **USER_M_PATH** and **SUBROUTINE_PATH** into your valid path to `custom_commands` folder. 
4. From `/home/<YOUR_USERNAME>/linuxcnc/configs/stepcraft420`  copy the launcher `SC420.desktop` to your favourite spot on the computer and launch it.

## Longer setup (by using linuxCNC graphical tools)
If you are setting up the machine from the ground up, there are some pictures added to help you. (But the whole setup is not documented here and you should follow tutorials on youtube) 

## Autoleveler

For accurate milling of PCBs you need to measure the curvature of your copper. I do this with autoleveler. One version that works for me can be found in this repo, but for up to date version you should visit their website:
https://www.autoleveller.co.uk/

Before running Autoleveler 0.7.0 you need Java8:
http://linuxg.net/how-to-install-the-oracle-java-8-on-debian-wheezy-and-debian-jessie-via-repository/

Copy `AutolevellerAE-0.7.0Free.jar` into  `/home/<YOUR_USERNAME>/linuxcnc/AutolevellerAE-0.7.0Free.jar` and make an accecutable with

	sudo chmod +x AutolevellerAE-0.7.0Free.jar









