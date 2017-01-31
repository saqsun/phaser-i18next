Phaser i18next
==============
Phaser i18next is a plugin for Phaser that allows you to have seamless translations in your game. It uses i18next as it's source for translations management, which is widely adopted by the JS community in other projects as well.

Key features:
* Support for translations namespaces
* Simple key/value JSON
* Seamless switching of languages
* No extra function calls for translating strings, directly build into Phaser's Text object

Getting Started
---------------
First you want to get a fresh copy of the plugin. You can get it from this repo or from npm, ain't that handy.
```
npm install @orange-games/phaser-i18next --save-dev
```

Next up you'd want to add it to your list of js sources you load into your game
```html
//Local installed version
<script src="node_modules/@orange-games/phaser-i18next/build/phaser-i18next.js"></script>
//Or use our cdn:
<script src="//cdn.fbrq.io/phaser-i18next/v0.0.1/phaser-i18next.min.js"></script>
```

After adding the script to the page you can activate it by enabling the plugin:
```javascript
//Load the plugin with the options, for more details on all possible options, see: http://i18next.github.io/i18next/pages/doc_init.html
game.plugins.add(PhaserI18n.Plugin, {
    fallbackLng: 'en'
});
```

Usage
-----
First up, you need to preload the languages you wish to have in the game.
```javascript
//And here we preload all locales for our game
game.load.locale(
    //all the languages we support: (en, de, nl)
    languages,
    //The path from which we can load the translations, by default this path also includes the translation namespace
    //But since we only have one namespace, we skip this for now.
    '/locales/{{lng}}.json',
    //The namespaces on which the translations are handled, defaults to ['translation']
    ['translation']
);
```

Manage translations
-------------------
When you're all done and set up for translations and have your key value file, next up is starting to translate them. For smaller games this is fairly simple and still managable by editing your translations in a text file.
But when you start with bigger games and more translations (and translation namespaces) you want to manage your translations better, and maybe even use external translator services.

Two of those service you could use are [locize](https://locize.com/) and/or [Poeditor](https://poeditor.com). Both these services allow you to online edit key value JSON translations that are used in i18next.
The advantage of using suchs tools is that it's easier to allow external people work on your translations and they aggragate the statistics of your projects (translation completion, languages managed, etc.) 

Todo
----
* Add support for Phaser's BitmapText
* Expose more powerfull feature of i18next
* Extend documentation
* Add Browser Language Detector

Disclaimer
----------
We at OrangeGames just love playing and creating awesome games. We aren't affiliated with Phaser.io or i18next. We just needed some awesome translations in our awesome HTML5 games. Feel free to use it for enhancing your own awesome games!

Phaser i18next is distributed under the MIT license. All 3rd party libraries and components are distributed under their
respective license terms.