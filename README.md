# MinerKeeper
MinerKeeper keeps your miner running and notifies you

It is a console application that constantly monitors your miner and restarts the miner in case he crashed or stopped mining due to any internal errors.
MinerKeeper, if you want, can also inform you about the restart of the miner, generate the summary report about your rig and send the notifications to your e-mail address or to your Telegram Messenger.

The latest version: v1.0.6 - [download](https://github.com/anmalkov/minerkeeper/releases/download/v1.0.6/MinerKeeper.1.0.6.zip).

Please read the [documentation](https://github.com/anmalkov/minerkeeper/blob/master/help.md) after the download.

[[русская версия]](https://github.com/anmalkov/minerkeeper/blob/master/README_ru.md)

## Main features

* Restart a miner in case of a crash or if it stopped mining due to any internal errors
* Automatically restart a miner every X hours
* Adjustable time interval for monitoring of a miner
* Configurable delay before the restart of a miner, to allow the GPUs to be correctly restarted
* Sending a summary report of your farm every X hours
* Sending all of the notifications to the e-mail address and/or to Telegram Messenger
* Full Russification of the interface and for all of the notifications

## Version history

v1.0.6
* Send a notification with a summary report about your rig every X hours (including all data about GPUs)
* Improved notifications

v1.0.5
* Add Russian language
* Improved notifications

v1.0.4
* Send notifications to Telegram
* Send notification when MinerKeeper starts

v1.0.3
* It is possible to specify a delay that MinerKeeper will apply before restart a miner
* *apiUrl* can contain only the host name now, e.g. 192.168.0.1:42000 (without '/getstat' at the end)

v1.0.2
* Added the ability to automatically restart a miner every X hours
* Added the rigName property into the configuration

v1.0.1
* Added monitoring for Ewbf ZCash (ZEC) cuda miner
* Send an email message in case of restart of the miner

## Links to supported miners:

* Ewbf ZCash (ZEC) cuda miner v0.3.4b - [information](https://github.com/nanopool/ewbf-miner) | [download](https://github.com/nanopool/ewbf-miner/releases/download/v0.3.4b/Zec.miner.0.3.4b.zip)

## Support the project

If you want to support the project you can use the next addresses for donation:
* ZEC t1PtBcUsaE1do2s97Atp89QCJAWbjfCKxym
