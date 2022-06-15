_________                                .__                                                                                                      
/   _____/__ ________   ________________  |  |    ____   ____  ______                                                                              
\_____  \|  |  \____ \_/ __ \_  __ \__  \ |  |   / ___\ /  _ \/  ___/                                                                              
/        \  |  /  |_> >  ___/|  | \// __ \|  |__/ /_/  >  <_> )___ \                                                                               
/_______  /____/|   __/ \___  >__|  (____  /____/\___  / \____/____  >                                                                              
      \/      |__|        \/           \/     /_____/            \/                                                                               
 _____                .__    .__                .____                              .__                   _________                                
/     \ _____    ____ |  |__ |__| ____   ____   |    |    ____ _____ _______  ____ |__| ____    ____    /   _____/ ______________  __ ___________
/  \ /  \\__  \ _/ ___\|  |  \|  |/    \_/ __ \  |    |  _/ __ \\__  \\_  __ \/    \|  |/    \  / ___\   \_____  \_/ __ \_  __ \  \/ // __ \_  __ \
/    Y    \/ __ \\  \___|   Y  \  |   |  \  ___/  |    |__\  ___/ / __ \|  | \/   |  \  |   |  \/ /_/  >  /        \  ___/|  | \/\   /\  ___/|  | \/
\____|__  (____  /\___  >___|  /__|___|  /\___  > |_______ \___  >____  /__|  |___|  /__|___|  /\___  /  /_______  /\___  >__|    \_/  \___  >__|   
      \/     \/     \/     \/        \/     \/          \/   \/     \/           \/        \//_____/           \/     \/                 \/       
---------------------------------------------------------------------
***To run a Test Case Server you need to setup two workspaces***
---------------------------------------------------------------------
Server Mining workspace.

Test Case Server.


For best results and to help keep things organised it is recommended to create a mining workspace.
---------------------------------------------------------------------
***Create the Server Mining Workspace***
---------------------------------------------------------------------
Step 1: Load up the getting started tutorials workspace
Step 2: Rename the workspace to something related to the server eg: yourusername-mining-servername
Step 3: Delete the 3 tutorials
Step 4: Locate the Plugins/Data-Mining node and "Add specified plugin data mine"
Step 4: Add the specified data mine you plan to enable within the test server sensor bot, along with candles and masters.
Step 5: Save and reload the workspace.
Step 6: Locate the Crypto Ecosystem node and expand then find Exchange Markets, Hover over BTC/USDT and select "Install Market".
Step 7: Locate the data tasks node inside my computer node, then continue and expand BTC/USDT/Candles/Candles/Exchange Raw Data/Exchange Raw Data Sensor Bot and configure as follows:
---------------------------------------------------------------------
{
    "startDate": "2017-06-01"
}
---------------------------------------------------------------------
Step 8: Delete every "resistances and supports Multi-Time-Frame-Daily" node leaving only "resistances and supports Multi-Time-Frame-Market" nodes on each data mine task node. This will help reduce unnecessary processing.
Step 9: Run all project data tasks from the Data Tasks node.
Step 10: Save the workspace you are finished with the Mining workspace.

---------------------------------------------------------------------
***Server Workspace***
---------------------------------------------------------------------
The server workspace can be accessed by requesting a default template from the machine learning telegram group.
---------------------------------------------------------------------
Step 1: Edit Test-Server Sensor Bot Instance with the following and replace YOUR-SERVER-NAME with the name of your server:
{
    "networkCodeName": "Testnet",
    "targetSuperalgosHost": "localhost",
    "targetSuperalgosHttpPort": 34248,
    "pythonScriptName": "Bitcoin_Factory_LSTM.py",
    "serverInstanceName": "YOUR-SERVER-NAME",
    "timeSeriesFile": {
        "labels": [

Step 2: If you are running multiple instances of Superalgos and require data transfer from instance then input the IP address of the Superalgos instance in the "targetSuperalgosHost": "IP-ADDRESS-HERE",
Step 3: Edit each indicator you wish to activate like below.
Indicator with range "ON" must be mining and up-to-date (from mining workspace preferably)

            {
                "dataMine": "Delta",
                "indicator": "MFI",
                "product": "MFI",
                "objectName": "mfi",
                "propertyName": "value",
                "range": [
                    "ON"
                ]
            },

Step 4: Create Task-Server-App from within your User Profile/User Apps. (If haven't done already)
Step 5: Use the Profile Constructor to Install Signing Accounts. (If haven't done already)
Step 6: If you have signed your account don't forget you need to save your profile and merge it with the plugins/governance/user-profiles develop branch on github.com
Step 7: Reference Task Server App Reference to the task server app in your profile.
Step 8: Start the Test-Server Task and check the console you should see something like this:

Superalgos TaskServer is Running!

Websockets Client will try to Connect to Network Node via Web Sockets ........ Trying to Connect to devosonder -> P2P Network Node #1 -> 99.81.83.180:18042
Websockets Client Connected to Network Node via Web Sockets .................. Connected to devosonder -> P2P Network Node #1 -> 99.81.83.180:18042
2022-06-15T10:23:12.605Z Working with these Parameter Ranges:
┌────────────────────────────────────┬─────────────┐
│              (index)               │      0      │
├────────────────────────────────────┼─────────────┤
│           LIST_OF_ASSETS           │  [ 'BTC' ]  │
│         LIST_OF_TIMEFRAMES         │ [ '01-hs' ] │
│      NUMBER_OF_LAG_TIMESTEPS       │     10      │
│ PERCENTAGE_OF_DATASET_FOR_TRAINING │     80      │
│          NUMBER_OF_EPOCHS          │     750     │
│       NUMBER_OF_LSTM_NEURONS       │     50      │
└────────────────────────────────────┴─────────────┘
2022-06-15T10:23:12.638Z              Binance   BTC/USDT      Bitcoin-Factory                    Test-Server                              Test-Server       Main Loop #        1                                      
2022-06-15T10:23:13.339Z Starting Network "Testnet" with these Test Clients:
┌─────────┬────────────────────────┬────────────────────────────┬───────────────────────────────────────────────────────────────────────┬──────────────┬────────────────────────────────────────┬──────────────┬─────────────────────────┐
│ (index) │          type          │            name            │                                config                                 │   project    │                   id                   │ savedPayload │       userProfile       │
├─────────┼────────────────────────┼────────────────────────────┼───────────────────────────────────────────────────────────────────────┼──────────────┼────────────────────────────────────────┼──────────────┼─────────────────────────┤
│    0    │ 'Test Client Instance' │ 'New Test Client Instance' │                '{\n    "codeName": "WorkFromHome"\n}'                 │ 'Governance' │ '43bc2026-c743-4896-a706-c54e187162a4' │  undefined   │      'BastianMuc'       │
│    1    │ 'Test Client Instance' │         'rx300-1'          │                 '{\r\n    "codeName": "rx300-1"\r\n}'                 │ 'Governance' │ 'f182a3c3-ebc0-4200-b2e3-2da85e77b104' │  undefined   │        'BlaaSwe'        │
│    2    │ 'Test Client Instance' │         'rx300-2'          │                 '{\r\n    "codeName": "rx300-2"\r\n}'                 │ 'Governance' │ 'd0a97fe3-7b0b-4466-8783-9d91557c4412' │  undefined   │        'BlaaSwe'        │
│    3    │ 'Test Client Instance' │         'rx300-3'          │                 '{\r\n    "codeName": "rx300-3"\r\n}'                 │ 'Governance' │ '17d39be6-1c6a-445f-88b9-1dab4b1eb84b' │  undefined   │        'BlaaSwe'        │

Congratulations the test server is now running !

---------------------------------------------------------------------
***Governance***
---------------------------------------------------------------------
Machine learning test cases are deployed to users and all test data is stored within your Bitcoin-Factory/Test-Server/YOUR-SERVER-NAME
It is important to note that you are required to keep this data and provide it in a report to allow the system to accurately account for all test cases solved by each user. Test reports are to be combined into a single report then merged into the Bitcoin-Factory/Reports folder with the naming style as follows:

Testnet-2022-05-27.csv



---------------------------------------------------------------------
Random Notes:

1. You can not turn off the minimun 3 labels: Candle Close, Max, Min and 1 Feature: Candle Open. At the Test Server config all this must be ON.
2. Remember that the Test Cases Array JSON file is generated once the first time the Test Server run and does not detect that this file exists. If you change the config adding or removing ON / OFF switches for indicators, you need to manually delete this file and the Forecast Cases Array file so that the Test Server generates it again. Failing to do so will produce errors executing the tests at the Docker container, since dimensions for reshapes will not match, since they were calculated at the moment this file was generated but the changed config produces datasets with other amount of data.