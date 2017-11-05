# Требования

Microsoft .NET Framework 4.6.1 должен быть установлен на компьютере - [загрузить](https://www.microsoft.com/en-us/download/details.aspx?id=49981).

Майнер должен быть запущен с включенной опцией для API:
* Для **Ewbf ZCash (ZEC) cuda miner** включите опцию *"--api"* в ваш *.bat файл

# Инсталляция

* Загрузите [последнюю версию](https://github.com/anmalkov/minerkeeper/releases/download/v2.2.0/MinerKeeper.2.2.0.zip) MinerKeeper с GitHub
* Распакуйте содержимое архива в любую папку на вашем диске (например C:\MinerKeeper)
* Откройте эту папку в проводнике windows
* Откройте файл config.json на редактирование в вашем любимом текстовом редакторе (например Notepad)
* Установите конфигурационные опции (смотрите раздел "Конфигурация" ниже)
* Запустите MinerKeeper.exe - он запустит ваш майнер автоматически

# Конфигурация

Вы найдете все параметры конфигурации внутри файла *config.json*.

## Параметры корневой секции

Опция | Описание
-------|------------
user | Параметры конфигурации пользователя MinerKeeper (смотрите ниже)
rigName | Имя вашей фермы.<br/>Это имя будет использоваться как уникальный идентификатор вашей фермы, и оно будет добавлено ко всем  уведомлениям, чтобы определить, к какой ферме относится это уведомление
miners | Массив параметров конфигурации для майнера (смотрите ниже)
currencyForGettingRates | Валюта которая будет использоваться для получения текущих курсов для криптовалют (например: USD, EUR, и т.д.)
currencyRules | Массив параметров конфигурации для правил курсов криптовалют (смотрите ниже)
monitorMinerIntervalInSeconds | Интервал в секундах, который используется MinerKeeper для проверки майнера
restartMinerEachHours | Количество часов, через которое майнер будет автоматически перезапущен (например, 24 - перезапускать майнер один раз в день)<br />Если значение равно 0 (ноль) - майнер не будет автоматически перезапускаться
restartPcEveryHours | Количество часов, через которое компьютер будет автоматически перезагружен (например, 720 - перезагружать компьютер один раз в месяц)<br />Если значение равно 0 (ноль) - компьютер не будет автоматически перезагружаться
delayBetweenStopAndStartInSeconds | Задержка в секундах перед рестартом майнера, что бы дать возможность видеокартам корректно рестартовать
language | Язык интерфейса MinerKeeper и всех нотификаций<br />Поддерживаемые языки:<br />"english" - английский, используйте [MinerKeeperBot](https://t.me/MinerKeeperBot) для Telegram сообщений<br />"russian" - русский, используйте [MinerKeeperRuBot](https://t.me/MinerKeeperRuBot) для Telegram сообщений
sendSummaryNotificationEveryHours | Количество часов, за которое будет сформирован и отправлен суммарный отчет о вашей ферме (например, 24 - отправлять отчет раз в день)<br />Если значение равно 0 (ноль) - суммарный репорт не будет отправляться
telegram | Параметры конфигурации Telegram нотификаций (смотрите ниже)
email | Параметры конфигурации нотификаций по электронной почте (смотрите ниже)

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
totalAcceptedSharesChangeIntervalMinutes | The duration that will be used to monitor if the total amount of accepted shares changed or not. If it is not changed during that interval, a miner will be restarted

## Rules for the cryptocurrencies rates section options

You can configure any number of the rules.
You will receive a notification for each rule in case of your condition will be positive.

Option | Description
-------|------------
currency | The name of the cryptocurrency which rate you want to monitor (e.g. ZEC, ZEN, ZCL, ETH, etc.)
condition | The condition of the rule<br />Possible values:<br />"more" - the notification will be sent if the current cryptocurrency rate will be more than the expected rate value<br />"equals" - the notification will be sent if the current cryptocurrency rate will be equal to the expected rate value<br />"less" - the notification will be sent if the current cryptocurrency rate will be less than the expected rate value
rate | The expected rate

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

# Использование Telegram для получения нотификаций

* Установите [Telegram Messenger](https://telegram.org/) на ваш смарт девайс или ноутбук
* Добавьте [MinerKeeperBot](https://t.me/MinerKeeperBot) бот, если вы хотите получать нотификации на английском, или [MinerKeeperRuBot](https://t.me/MinerKeeperRuBot), если вы хотите получать нотификации на русском языке, в ваш Telegram (просто начните чат). Этот чат-бот будет отправлять вам нотификации от MinerKeeper, который установлен на вашей ферме, и также будет отправлять ваши команды на MinerKeeper
* Используйте комманду '/start' (просто введите данный текст и отправьте сообщение боту) для MinerKeeperBot для того, что бы получить ваш уникальный чат ID
* Введите этот номер в поле 'telegram' -> 'chatId' в файле config.json
* Измените значение поля 'telegram' -> 'sendNotifications' в файле config.json на true
* Запустите MinerKeeper.exe - вы должны получить нотификацию о старте MinerKeeper на ваш Telegram

# Поддержите проект

Если вы хотите поддержать проект, используйте пожалуйста следующие адреса для пожертвований:
* ZEC t1PtBcUsaE1do2s97Atp89QCJAWbjfCKxym
* ETH 0x65FEB65A56E10D3a1a87C5D4e1ad345534489842
