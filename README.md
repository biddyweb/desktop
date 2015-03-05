#Hybrid Mac

This is an example of running a Meteor wrapped in a Mac OS X app (using gulp for build tools)

![demo](http://i.imgur.com/EnpM8fG.png)

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

After Xcode opens, run the application just like with `meteor run ios-device`

============

### TODO

* [ ] Replace Xcode app name
* [ ] Let the user specify icons in mac-config.json
* [ ] Clean up build gulpfile
* [ ] Fix DDP_DEFAULT_CONNECTION_URL replacement and add autoupdate back in
* [ ] Add Meteor.isMac() flag
* [ ] Build into a Meteor package
