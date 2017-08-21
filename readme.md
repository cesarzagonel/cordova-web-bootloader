# cordova-web-bootloader
> Simple bootloader template that loads your application from web.

# Dependencies
- Apache Cordova ~7.0.1

# Usage
``` bash
$ git clone git@github.com:cesarzagonel/cordova-web-bootloader
$ cordova prepare
```

Android:
``` bash
$ cordova run android
```

iOS:
``` bash
$ cordova run ios
```

# Entry point
As any cordova project, the entry point is configured at **config.xml** on **content** property, also setting the **allow-navigation** property for your desired url.

# Cordova plugins
For loading cordova.js and its plugins, your application needs to look for the custom platform user agents, as the example javascript code below:
``` javascript
// index.html
 
/**
 * Check for custom user agent for loading cordova.js
 * This is necessary for using cordova plugins
 */
var ua = navigator.userAgent;
var cordovajs = document.createElement('script');
 
if(ua.match(/(CordovaAndroid)/)){
    // Custom user agent for Android
    cordovajs.src = 'cdvfile://localhost/assets/www/cordova.js';
}else if(ua.match(/(CordovaiOS)/)){
    // Custom user agent for iOS
    cordovajs.src = 'cdvfile://localhost/bundle/www/cordova.js';
}
 
document.body.appendChild(cordovajs);
```

# License
This project is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).