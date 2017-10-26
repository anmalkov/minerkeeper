# Requirements

Microsoft .NET Framework 4.6.1 should be installed on the PC - [download](https://www.microsoft.com/en-us/download/details.aspx?id=49981).

The miner should be run with API enabled option:
* For **Ewbf ZCash (ZEC) cuda miner** include *"--api"* option to your *.bat file

# Installation

* Download the [latest version](https://github.com/anmalkov/minerkeeper/releases/download/v2.0.0/MinerKeeper.2.0.0.zip) of the MinerKeeper on GitHub
* Extract the content of the archive to any folder on your drive (e.g. C:\MinerKeeper)
* Open that folder in the windows explorer
* Open config.json file for editing in your favorite text editor (or Notepad if you want)
* Set the configuration option (see the next chapter)
* Run MinerKeeper.exe - it will run your miner automatically

# Configuration

You can find all of the configuration options inside the *config.json* file.

## Root section options

Option | Description
-------|------------
user | Configuration options for the user of MinerKeeper
rigName | The name of your rig.<br/>This name will be used as a unique identifier of your rig and it will be added to the notifications to identify to what rig a notification belongs
miners | The array of the miner's configuration options
monitorMinerIntervalInSeconds | The interval in seconds that MinerKeeper uses to check the miner health<br/>You can use any interval, but it makes no sense to use an interval that is below the refresh interval of the selected miner (e.g. 30 seconds for Ewbf miner)
restartMinerEachHours | The amount of hours to automatically restart a miner (e.g. 24 - restart miner once a day)<br />If it equals to 0 (zero) - no automatic restart will be applied
delayBetweenStopAndStartInSeconds | The delay in seconds that MinerKeeper will use for restart a miner to allow cards to reset
language | The language for MinerKeeper and for all notifications<br />Supported languages:<br />"english" - please use [MinerKeeperBot](https://t.me/MinerKeeperBot) for Telegram messages<br />"russian" - please use [MinerKeeperRuBot](https://t.me/MinerKeeperRuBot) for Telegram messages
sendSummaryNotificationEveryHours | The amount of hours to send a summary report about your rig (e.g. 24 - send a report once a day)<br />If it equals to 0 (zero) - no report will be sent
telegram | Configuration options for Telegram notifications 
email | Configuration options for email notifications

## User section options

Option | Description
-------|------------
email | Your private email address<br />If you want to use the functionality within the Free subscription only, please left it blank
key | Your access key for MinerKeeper (if you don't have the key, please look at *Obtain your access key* section below)<br />If you want to use the functionality within the Free subscription only, please left it blank

## Miner section options

Option | Description
-------|------------
miner | The name of the miner that you want to monitor<br />Possible values:<br/>"**ewbf**" - to monitor Ewbf ZCash (ZEC) cuda miner<br/>"**claymore**" - to monitor Claymore's Dual Ethereum+Decred AMD+NVIDIA GPU Miner
pathToMiner | The path to miner's \*.bat file.<br />For example: "D:\\\Coins\\\Ewbf\\\start.bat"
apiUrl | The ULR to miner API host, if blank then MinerKeeper will use the default URL address for selected miner (e.g. '127.0.0.1:42000' for Ewbf ZCash (ZEC) cuda miner)
durationOfDataCollectionForAlertsInMinutes | The duration that will be used to collect the data of the miner for getting the average values for alerts
minimumTotalHashrateForAlert | If the average hashrate will be lower than this value the notification will be sent<br />If it equals to 0 (zero) - no check for the hashrate will be performed
restartMinerOnMinimumTotalHashrate | If equals to true the miner will be restarted if the average hashrate will be lower than  _minimumTotalHashrateForAlert_<br />Possible values: _true_ or _false_
maximumGpuTemperatureForAlert | If the temperature on any GPU will be higher than this value the notification will be sent<br />If it equals to 0 (zero) - no check for the temperature will be performed

## Telegram section options

Option | Description
-------|------------
sendNotifications | If equals "true" the MinerKeeper will send the notifications to Telegram 
chatId | Chat ID that will be used for telegram messages (see *Use Telegram for notifications* section below)

## Email section options

Option | Description
-------|------------
sendNotifications | If equals "true" the MinerKeeper will send the notifications to your email address 
smtp | Configuration options for SMTP server that MinerKeeper will use to send the email messages

## SMTP section options

Option | Description
-------|------------
host | The host address of SMTP server.<br />For example: "smtp.gmail.com"
port | The port number of SMTP server.<br />For example: 587
enableSsl | If equals "true" the MinerKeeper will use SSL connection to SMTP server
username | The username to access the SMTP server<br />For example: "yourGmailAccount@gmail.com"
password | The password to access the SMTP server
fromEmalAddress | The email address that MinerKeeper will use to send the email messages from
toEmalAddress | The email address that MinerKeeper will use to send the email messages to

# Subscriptions

There are three subscriptions for MinerKeeper - Free, Medium and Full.<br />
The Free subscription is a default subscritpion and is completely free for use.<br />
The Medium and Full subscription should be activated by a request using:
* an email message to minerkeeper@outlook.com
* a telegram message to [@anmalkov](https://t.me/anmalkov)

Features | Free | Medium | Full
---------|------|--------|-----
All of the local features | V | V | V
Notification that a rig is offline |  | V | V
Remote management of a rig |  | V | V

# Obtain your access key

You should have an access key only if you want to use the features from Medium or Full subscriptions.
If you are going to use only the features within the Free subscription, then the access key is not needed.

### Getting the access key for the first time

If you run MinerKeeper for the first time and you don't have an access key, please follow the next steps:
* Enter your private email address into '*user*' -> '*email*' in config.json file
* The key should be empty in '*user*' -> '*key*' in config.json file
* Run MinerKeeper.exe
* It will prompt: '*If you use MinerKeeper for the first time, please, press 'Y' and the new user key will be generated, or press any other button to exit*'
* Press '*Y*' on the keyboard
* The new access key will be generated for you and automatically added to the config.json file

**Please use the same email address and access key on the all of your rigs.**

### Restore the access key value

If you lost your access key you have two options to restore it.
* Use command '*/getkey*' (just type it) for the **MinerKeeperBot** to get your access key value
* Send the request email from your private email address to minerkeeper@outlook.com

# Use Telegram for notifications

* Install [Telegram Messenger](https://telegram.org/) on your smart device or laptop
* Add the [MinerKeeperBot](https://t.me/MinerKeeperBot) bot to receive the notifications in English or the [MinerKeeperRuBot](https://t.me/MinerKeeperRuBot) bot to receive the notifications in Russian, to your Telegram (just start chat). This bot will send you the notifications from MinerKeeper, that installed on your rig, and it will send your commands to MinerKeeper
* Use command '*/start*' (just type it) for the **MinerKeeperBot** to get your unique chat ID
* Put this number in '*telegram*' -> '*chatId*' in config.json file
* Change the value of '*telegram*' -> '*sendNotifications*' in config.json file to *true*
* Run MinerKeeper.exe - you should receive a notification that MinerKeeper has been started 

### Support the project

If you want to support the project you can use the next addresses for donation:
* ZEC t1PtBcUsaE1do2s97Atp89QCJAWbjfCKxym
* ETH 0x65FEB65A56E10D3a1a87C5D4e1ad345534489842
