# MinerKeeper
MinerKeeper keeps your miner running and notifies you

It is a console application that constantly monitors your miner and restarts the miner in case he crashed or stopped mining due to any internal errors.
MinerKeeper, if you want, can also inform you about the restart of the miner by sending an e-mail message to your e-mail address.

The latest version: v1.0.6 - [download](https://github.com/anmalkov/minerkeeper/releases/download/v1.0.6/MinerKeeper.1.0.6.zip).

Please read the [documentation](https://github.com/anmalkov/minerkeeper/blob/master/help.md) after the download.

### Version history

v1.0.6
* Send a notification with summary report every X hours (all data about GPUs inside)
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

### Links to supported miners:

* Ewbf ZCash (ZEC) cuda miner v0.3.4b - [information](https://github.com/nanopool/ewbf-miner) | [download](https://github.com/nanopool/ewbf-miner/releases/download/v0.3.4b/Zec.miner.0.3.4b.zip)

### Support the project

If you want to support the project you can use the next addresses for donation:
* ZEC t1PtBcUsaE1do2s97Atp89QCJAWbjfCKxym
