# Noizmaker
Noizmaker is a bot for your Discord server that will play custom soundbites in response to commands entered in the text chat channel.

Noizmaker is a fork of Airhornbot, an example application using the [Discord API](https://discordapp.com/developers/docs/intro). Airhornbot, and in turn Noizmaker, utilizes the [discordgo](https://github.com/bwmarrin/discordgo) library, a free and open source Golang implementation of the Discord API. Airhorn Bot requires Go 1.4 or higher.

#WARNING
This is currently in development! You should at this point assume that none of this works and may cause more headache than happiness. I am working on simplifying the bot to make it super easy to deploy to Heroku for personal use. Until this warning has been removed, clone this at your own risk.

## Usage
So you want to get your own custom version of Airhornbot up and running in your private Discord server? You want to make it easy for you and your friends to add new sounds? You tried to figure out what the official Airhornbot code is doing but were turned away by the lack of documentation combined with not knowing Go? Me too!

What follows is a super simple guide that will get you your own custom Airhornbot running in a matter of minutes.

###Register an Application
The first thing to do is register an application with Discord. To do that, head to the [Discord developers](https://discordapp.com/developers/docs/intro) page (you'll likely have to log in or something) and go to the My Applications section. Create a new application and name it whatever you want your bot to be called. You should be taken to the main page of your app, where you'll want to click the button that asks if you'd like to add a bot. Make sure you mark the bot as public, and feel free to change the description and the picture as to suit your tastes.

Next is allowing the thing to join your channel and giving it the correct permissions. The easiest way to do this is to go to a URL that you can build given the app's client ID and the permission's code that we need. The URL takes the following form:

`https://discordapp.com/oauth2/authorize?client_id=<client_id>&scope=bot&permissions=<permission_code>'

You want to take the client ID of your app, which you can find on your app's administration page that you were just on, and the following permission code `3148800` and use them to replace `<client_id>` and `<permission_code>` in that URL. Visit that page with your browser and it will take you to a page that will allow you invite the bot to whatever servers you have permissions in, and it also indicates that you are giving the bot a few permissions. Accept all of them and invite it to whatever server you want it to play in.

At the end of this you'll have a bot account sitting in your channel, but it won't respond to anything.

###Running A Bot Locally
First step is to set up a deve environment the way Go likes it. For now, I'm leaving it up to you to figure that out. Next, you'll want to pull down this repo. Best way to do that is to do:

`go get github.com/nickcharles/noizmaker`
`go install github.com/nickcharles/noizmaker`

This will place a `noizmaker` executable in your `$GOPATH/bin` directory. You are now capable of running the bot on your local machine! The command requires two arguments: the bot username and the bot token. These can be found in the bot user section of your app's administration page. Given those, here is what the command should look like:

`./noizmaker -o <bot_name> -t <bot_token>`

There will be some debug output but assuming everything is in the right place you should now be able to send the bot some commands in your server. To confirm this, the bot should say something in the channel, and you can give it a try by typing `!wtc` into your chat.

###Running The Bot On Heroku
Coming soon.