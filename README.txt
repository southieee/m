============================
NiceHash QuickMiner v0.3.0.2
============================

Instructions:
1. Start NiceHashQuickMiner.exe.
2. You will be asked for your NiceHash mining address. Provide it.
3. Set autostart with Windows.
4. Use OCTune to adjust overclocks and fan speeds (do not use Afterburner, it is not needed).
5. Enjoy carefree mining! 

serviceLocation 0 = eu
serviceLocation 1 = usa
Change serviceLocation, BTC, workerName, launchCommandLine.
consoleLogLevel, fileLogLevel (for NiceHashQuickMiner); use following numbers:
0-6 which means:
0: log everything (TRACE)
1: log debug (DEBUG)
2: standard (INFO)
3: warnings (WARNING)
4: errors (ERROR)
5: fatal (FATAL)
6: no logging (disabled)

Please, enable full file logging ("fileLogLevel":0) and submit 
log files when error is found.

Updating from previous version? Make sure to full uninstall it first - 
remove Windows autostart in old version before you enable autostart in new one.

From version 0.2.0.0, CPU Mining with integrated XMRig is possible on modern CPUs
with AVX2. CPU Mining can be activated from the tray menu (or via Rig Manager). 
You can provide extra launch parameters for XMRig (config nhqm.conf), for example:

	"CPUMinerELP":"--cpu-max-threads-hint 50 --print-time 15"

First parameter above tells CPU miner to use only 50% of resources, second one prints
speed to console every 15 seconds. Parameters for lowest CPU priority, donation level 0%
and other important parameters are already provided by the Excavator.

There are 3 options what NiceHashQuickMiner should do when device fails or when
device has too high speed.

	"whenDeviceSpeedTooHigh":2,
	"whenDeviceSpeedZero":1,

1 = no action
2 = restart Excavator
3 = restart rig

Usually, when device has too high speed, issue can be resolved by restarting Excavator.
If device has speed 0 (errored out), it means that there was some instability (either too
high OC or issue with risers). In that case, it is most likely better to restart the rig
(set to value 3).

From version 0.3.0.0, NiceHashQuickMiner has auto updater. You will be notified when new
version is available for download. You can participate in testing RC versions (release
candidate) which have new features faster; enable this by setting:

	"bUpdateRCVersion":true