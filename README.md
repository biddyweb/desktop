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

### Usage

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
* [ ] Clean up build gulpfile
* [ ] Fix DDP_DEFAULT_CONNECTION_URL replacement and add autoupdate back in
* [x] Add Meteor.isMac flag
* [ ] Build into a Meteor package

============

### Details

* Built using [MacGap2](https://github.com/MacGapProject/MacGap2)
* For more details on Mac OS X specific API features please refer to http://docs.macgap.com/
