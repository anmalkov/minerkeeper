# Requirements

Microsoft .NET Framework 4.6.1 should be installed on the PC - [download](https://www.microsoft.com/en-us/download/details.aspx?id=49981).

The miner should be run with API enabled option:
* For **Ewbf ZCash (ZEC) cuda miner** include *"--api"* option to your *.bat file

# Installation

* Download the [latest version](https://github.com/anmalkov/minerkeeper/releases/download/v1.0.4/MinerKeeper.1.0.4.zip) of the MinerKeeper on GitHub
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
rigName | The name of your rig.<br/>This name will be added to the notifications, to be able to identify to what rig a notification belongs
miner | The name of the miner that you want to monitor<br />Possible values:<br/>"ewbf" - to monitor Ewbf ZCash (ZEC) cuda miner
pathToMiner | The path to miner's \*.bat file.<br />For example: "D:\\\Coins\\\Ewbf\\\start.bat"
monitorMinerIntervalInSeconds | The interval in seconds that MinerKeeper uses to check the miner health<br/>You can use any interval, but it makes no sense to use an interval that is below the refresh interval of the selected miner (e.g. 30 seconds for Ewbf miner)
restartMinerEachHours | The amount of hours to automatically restart a miner (e.g. 24 - restart miner once a day)<br />If it equals to 0 (zero) - no automatic restart will be applied
delayBetweenStopAndStartInSeconds | The delay in seconds that MinerKeeper will use for restart a miner to allow cards to reset
apiUrl | The ULR to miner API host, if blank then MinerKeeper will use the default URL address for selected miner (e.g. '127.0.0.1:42000' for Ewbf ZCash (ZEC) cuda miner)
telegram | Configuration options for Telegram notifications 
email | Configuration options for email notifications

## Telegram section options

Option | Description
-------|------------
sendNotifications | If equals "true" the MinerKeeper will send the notifications to Telegram 
chatId | Chat ID that will be used for telegram messages (see *Use Telegram for notifications* sectio below)

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

# Use Telegram for notifications

* Add a bot to Telegram (just start chat): https://t.me/MinerKeeperBot, this bot will send you notifications from MinerKeeper installed on your rig
* Use command '*/start*' for the **MinerKeeperBot** to get your unique chat ID
* Put this number in '*telegram*' -> '*chatId*' in config.json file
* Change the value of '*telegram*' -> '*sendNotifications*' in config.json file to *true*
* Run MinerKeeper.exe - you should receive a notification that MinerKeeper has been started 

### Support the project

If you want to support the project you can use the next addresses for donation:
* ZEC t1PtBcUsaE1do2s97Atp89QCJAWbjfCKxym
