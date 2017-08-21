# cordova-web-bootloader
> Simpes template de bootloader que carrega sua aplicação na web.

# Dependências
- Apache Cordova ~7.0.1

# Usando
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

# Ponto de entrada
Como qualquer projeto cordova, o ponto de entrada é configurado em **config.xml** na propriedade **content** definindo também a propriedade **allow-navigation** para a url desejada.

# Plugins Cordova
Para carregar o cordova.js e seus plugins, sua aplicação precisa procurar pelos "user agents" customizados de cada plataforma, como no código javascript abaixo:

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

# Licença
Este projeto tem seu código aberto sob a [licença MIT](http://opensource.org/licenses/MIT).