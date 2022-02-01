# Derpcord
A new, great way to interact with your TF2Autobot, along with other features! Derpcord is fully written in NodeJS using Discord.js V13.
Heavily inspired from [Gobot's TF2 Autocord](https://github.com/Gobot1234/tf2-autocord).
I decided to write a similar bot where it will send messages to your Autobot via Steam through the use of Discord commands.

## Features
- Allows you to see basic server information about your Discord using the `serverinfo` command
- Don't know the SKU to a specific item? Just use the `get` command followed by the full name of the item, and the bot will show you the SKU, along with the item's backpack.tf page and marketplace.tf page.
- The `get` command also works for getting an item's name. Simply use `get` followed by the SKU, and the bot will show you the item's name along with the other information as mentioned above.
- Finally, `send` is the command that will send Steam messages to your Autobots. Note that only one person(i.e, the trade bot's owner) can use this command.
- Supports multiple trade bots!


## Requirements
- You will need a Steam account for this to work, and this account __MUST NOT BE THE SAME__ as the account on which you run TF2Autobot. Therefore, you will need to create a new account, if one isn't already available.
- You will need the `shared_secret` of this Steam Account, therefore, it is recommended to set up your Mobile Authenticator using [Jesscar's SDA](https://github.com/Jessecar96/SteamDesktopAuthenticator).
- Your own Discord Server is needed for this to run as well.
- In your TF2Autobot's config, remember to add this bot's ID64 to the ADMIN section, otherwise you will not be able to use admin commands.
- Follow the steps [here](https://discordjs.guide/preparations/setting-up-a-bot-application.html) to create a bot on Discord and add it to your server. The token you see here is what will be needed to log your bot in to Discord.


## Installation and Setup
- Clone the repo to a folder of your choice
- Head to the folder, open a Terminal Window / Command Prompt within it, and run `npm i`.
- Once complete, go to the `config` folder, and open the `template_discord_config.json` file.
  - Under this, you will see 2 variables, namely `prefix` and `token`
    - Prefix is what the bot will use to recognize commands sent to it on Discord, it can be anything.
    - Token is basically like a password which logs your bot in to Discord. __DO NOT SHARE THIS WITH ANYONE.__
    - Fill in the required details, and save the file as `discord_config.json`
- Head on over to the `template_steam_config.json` file, fill in the Steam login details of your bot there and save it as `steam_config.json`.
- You're almost done! We just have a few more changes to make, go back to the root directory and open the `discord_bot.js` file in a Code Editor of your choice.
  - For `commands_channel_id`, right click on the channel on which you wish to see certain responses coming from your bot in, and click on Copy ID. Paste it in between the quotes.
  - For `bot_owner_id`, right click on your name, and click on Copy ID, and paste that between quotes here.
  - For `bot_ids`, fill in the name of your bot, followed by the Steam ID64 of that bot. If you have multiple bots, you can do that too! Fill in the details as shown below:
    ```js
    const bot_ids = {
        'bot1':'id64 of bot1 here',
        'bot2':'id64 of bot2 here',
      }
    ```
  - `bot_pictures` will show you images of your bot's profile picture/any picture you want when you send/receive messages from that particular bot. The profile images must come from a URL which ends in a '.jpg' or a '.png', example would be: https://cdn.discordapp.com/attachments/670639866824097813/845547326121443358/materialRobot.jpg. If you have multiple bots, same format applies as above. __Remember to use the same names for the bots as you have used above.__
  - Finally, we have `bot_trade_offer`, where you will input your bot(s)' trade offer URLs. Same format applies as above. Save the file and close it.
- And we are done!

## Running the bot
- After following the steps above, open up a command prompt / terminal and type `node discord_bot.js`
- If all is well, you should see a message from the bot in the channel you want to see its messages go to, saying it has logged in and set its game to TF2. Voila! You're ready to go!

## Problems/Issues?
Facing any issue with setup? Join my Discord [here](https://discord.gg/YD2tyYF).
