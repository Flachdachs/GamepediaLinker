# GamepediaLinker
A configurable Discord bot for linking wiki articles from any Gamepedia-based community.

# Syntax
`[[<article name>]]` or
`--<article name>--` -> starts a search and links the first article found 
as `http://xxx.gamepedia.com/<found_article_name>`

e.g. --thing-- gives `http://xxx.gamepedia.com/Thing` 

`--[<raw article>]--` -> just creates a link without search like `http://xxx.gamepedia.com/<raw_article>`

e.g. --(thing)-- gives `http://xxx.gamepedia.com/thing` 

## Other commands
`gl~help` - Link to this README.

`gl~sinfo` - Shows info about the configuration of the bot on the server.

## Server admin commands
`gl~swiki` - Sets the global wiki for the server.

`gl~cwiki` - Sets the override wiki in the current channel.

`gl~bchan <value>` - Sets the broadcast channel of the server to the mentioned channel. Accepted values are:
*   A #channel mention
*   No value given - sets current channel as broadcast channel
*   off - disables broadcast channels for the current server

## Bot admin commands
`gl~restart` - Restarts the bot. **The bot *must* be run under a process manager such as PM2, otherwise this will just error out the bot!**

`gl~bc` - Broadcasts a message across all of the servers the bot is in - to the broadcast channel is set, or the general channel otherwise.

# Inviting it
Click the following link: <https://discordapp.com/oauth2/authorize?client_id=439155758819573781&scope=bot&permissions=3072>

The bot only has read message and send message permissions when added - additional permissions and limiting to channels must be done manually.

# Running it yourself
1.  Download the repository.
2.  Make sure you have NodeJS and NPM with all of its dependencies installed.
3.  `npm install`
4.  Make a `config.json` file; an example is provided. Fill the fields with:
  . `token` contains the token of the bot account used.
  . `admin_snowflake` contains the ID of the admin user. **REQUIRED FOR THE BOT TO START UP.**
  . `prefix` the prefix to activate commands.
5.  `node wikilinker.js` to run it!
