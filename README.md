#Hybrid Mac

This is an example with gulp build tools of running a Meteor app in a Mac OS X webview

![demo](http://i.imgur.com/upeED2J.png)

### Usage

1. To start the Meteor server and web client
```
cd build
npm start
```

2. To build the Meteor app into the Mac OS X app
```
cd build
npm install
gulp
```

3. After Xcode pops up click run build to start app

============

### TODO

* [ ] Replace Xcode app name
* [ ] Let the user specify icons in mac-config.json
* [ ] Clean up build gulpfile
* [ ] Fix DDP_DEFAULT_CONNECTION_URL replacement and add autoupdate back in
