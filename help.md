# Requirements

Microsoft .NET Framework 4.6 should be installed on the PC - [download](https://www.microsoft.com/en-us/download/details.aspx?id=49981).

The miner should be run with API enabled option:
* For **Ewbf ZCash (ZEC) cuda miner** include *"--api"* option to your *.bat file

# Configuration

You can find all of the configuration options inside the *config.json* file.

## Root section options

Option | Description
-------|------------
miner       | The name of the miner that you want to monitor<br />Possible values:<br/>"ewbf" - to monitor Ewbf ZCash (ZEC) cuda miner
pathToMiner | The path to miner's *.bat file.<br />For example: "D:\\\Coins\\\Ewbf\\\start.bat"
monitorMinerIntervalInSeconds | The interval in seconds that MinerKeeper uses to check the miner health<br/>You can use any interval, but it makes no sense to use an interval that is below the refresh interval of the selected miner (eg. 30 seconds for Ewbf miner)
apiUrl | The ULR to miner API, if blank then MinerKeeper will use the default URL address for selected miner (eg. http://127.0.0.1:42000/getstat for Ewbf ZCash (ZEC) cuda miner)
sendEmailWhenRestartMiner | If equals "true" the MinerKeeper will send an email message on each restart of the miner 
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
