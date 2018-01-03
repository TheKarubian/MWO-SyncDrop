# MWO-SyncDrop
## Synopsis
This script is a plugin for the Streamlabs Chatbot for Twitch.
It's purpose is to provide a simple way to synchronize a drop between 
several Players of MechWarrior Online, while not grouped.

### How does it work?
Its function is simple: via a single command, a countdown is initiated, 
at which end the players receive an order to initiate the drop.
The countdown can be configured either via parameters to the command or by UI.
By default, the script will send its output to the channel from which it has 
received the command. This can be either the Twitch chat or Discord.
Via the "Use both chats" option in the UI, the script can be forced to always send
the countdown and launch order to both chat systems, no matter from where it was 
actually started.

## Installation
### Prerequisites
* First, you need the Streamlabs Chatbot, which you can download from the 
[Streamlabs Website](https://www.streamlabs.com/chatbot). 
Please follow the instruction provided there.
* Second, you need Python 2.7.x (highest version preferable), for which there 
also is a link on the Streamlabs Website. (2.7.x is a restriction coming from the
Chatbot. My scripts will usually also work with Python 3.x)

### Install the script
Within the chatbot, you go to the "scripts" section and click on the cog in the upper right corner.
There, you need to specify Python's Lib folder, usually "C:\Python27\Libs" unless you installed 
Python somewhere else.

Then you can simply click on "Import Script" and select the downloaded zip-file.
This will install the script, and you're done.

## Usage
### Commandline Syntax
While every possible option is available via the script's UI, the most important 
options can also be entered via command line. Please note that the commandline will
always take precedence over the settings defined via UI. The settings in the UI
however will be stored in a file, and loaded upon next start of the bot automatically.
The parameters on the commandline are valid only for the one, single call.

```
!syncdrop [<countdown> | <countdown> <regions>]
``` 

As you can see, you can call the script without any parameters at all. This will
then take the default settings as defined by the scripts UI.

You can also call it with a single parameter, which then will be interpreted as the 
countdown timer in seconds. The value provided here will take precedence over the 
value defined in the script's UI.

You can also call it with two parameters, the first again being the countdown timer,
and the second denoting the regions you have selected in your Quick-Launch button.
Values can be:

* EU for the european region
* NA for the north american region
* OC for the oceanic (Asia, Australia, New Zealand, etc). reagion

You can also use any combination of these values by concatenating them with a "|" character.

```
!syncdrop 5 EU
```
Launches the countdown with 5 seconds for region EU.
```
!syncdrop 5 EU|NA
```
Launches the countdown with 5 seconds for region EU and NA.
```
!syncdrop 5 EU|NA|OC
```
Launches the countdown with 5 seconds for region EU, NA and OC.

The script will tell the users about which regions you have 
selected, so they can adjust to your selection.
