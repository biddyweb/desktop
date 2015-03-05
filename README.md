#Hybrid Mac

[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/meteorhybrid/platform?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

This is an example of running Meteor wrapped in a Mac OS X app (using gulp for build tools)

![demo](http://i.imgur.com/EnpM8fG.png)
![demo](http://i.imgur.com/xvkbbrA.png)

### Development

To add Mac OS X native specific code
```
if (Meteor.isMac) {
	return "WOOT";
}
```

##### Config (located in the root of your Meteor app)
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

##### Icons 
*Currently they have to be located in resources/icons/mac/*
(this can be changed in the gulp file and build/Contents.json)

============

### Running and building

Run all the following commands from the build directory
```
cd build
```

To start the Meteor server
```
npm start
```

To build the Meteor app into the Mac OS X app
```
npm install
gulp
```

After Xcode opens, run the application

============

### TODO

* [ ] Replace Xcode app name
* [ ] Let the user specify icons in mac-config.json
* [ ] Turn gulpfile into a simple node.js lib
* [ ] Fix DDP_DEFAULT_CONNECTION_URL replacement and add autoupdate back in

============

### Details

* Built using [MacGap2](https://github.com/MacGapProject/MacGap2)
* For more details on Mac OS X specific API features please refer to http://docs.macgap.com/
