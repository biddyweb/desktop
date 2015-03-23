# ![Hybrid](http://i.imgur.com/jUDMlbO.png) Desktop

[![Join the chat at https://gitter.im/buildhybrid/platform](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/buildhybrid/platform?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

> Hybrid desktop app build tools for Meteor 

*March 14 - I renamed this project to Desktop. I'm in the process of adding atom-shell and nw.js build tools so you can choose whichever wrapper you want.*
---

This is an example of running Meteor wrapped in a Mac OS X app (using gulp for build tools). 

Since the [cordova-osx](https://github.com/apache/cordova-osx) platform is basically dead, this integration uses [MacGap2](https://github.com/MacGapProject/MacGap2) which is what [Slack](http://slack.com) uses for their app. I tried to match the Meteor Cordova integration as much as possible as far as file locations and naming conventions. 

*Note: MacGap 2 is considered beta, the development isn't very active, and the documentation is sparse. I don't think it is ready to be added as a core Meteor platform but it is cool to play around with! I'm going to start contributing to it when I have time.*

![demo](http://i.imgur.com/EnpM8fG.png)
![demo](http://i.imgur.com/xvkbbrA.png)

============

### Requirements

* Xcode 6

============

### Usage instructions

Since this repo has a submodule (MacGap2), use the `--recursive` flag when cloning.
```
git clone https://github.com/meteorhybrid/mac.git --recursive
```

Run all the following commands from the build directory.
```
cd mac/build
```

To start the Meteor server
```
npm start
```

To build the Meteor app into the Mac OS X app, open a new terminal and navigate to the build directory.
```
npm install
gulp
```

After Xcode opens, run the application.

============

### Development

To add Mac OS X native specific code
```
if (Meteor.isMac) {
	return "WOOT";
}
```

#### Config (located in the root of your Meteor app)
`mac-config.json`

Example Config
```
{
	"main": "public/index.html",
	"name": "Leaderboard",
	"description": "",
	"version": "1.0.0",
	"plugins" : {
		"Dock":"Dock",
		"Dialog":"Dialog",
		"Fonts": "Fonts",
		"Clipboard":"Clipboard",
		"StatusItem":"StatusItem",
		"Task": "Task",
		"Sound": "Sound",
		"Defaults": "Defaults",
		"File": "File"
	},
	"window" : {
		"title": "Leaderboard",
		"width": 595,
		"height": 690,
		"position": "center",
		"min_width": 400,
		"min_height": 200,
		"max_width": 1200,
		"max_height": 800
	}
}
```

#### Icons 
*Currently they have to be located in app/resources/icons/mac/*

(this can be changed in the gulp file and build/Contents.json)

============

### TODO 

MacGap
* [ ] Replace Xcode app name
* [ ] Let the user specify icons in mac-config.json
* [ ] Turn gulpfile into a simple node.js lib
* [ ] Fix DDP_DEFAULT_CONNECTION_URL replacement and add autoupdate back in
General
* [ ] atom-shell build tools
* [ ] nw.js build tools

============

### Details

* Built using [MacGap2](https://github.com/MacGapProject/MacGap2).
* For more details on Mac OS X specific API features please refer to http://docs.macgap.com/.
