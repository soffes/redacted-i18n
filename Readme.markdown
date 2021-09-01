# Redacted i18n

All of the strings files for [Redacted](https://itunes.apple.com/app/redacted/id984968384?mt=12&uo=6&at=1l3vmtU&ct=).


## Organization

Each language has its own `.lproj` folder. Inside are several `.strings` files:

| Name                         | Description                                 |
|------------------------------|---------------------------------------------|
| iOS Description.txt          | App Store description for iOS app           |
| iOS InfoPlist.strings        | Strings used by the system for the iOS app  |
| iOS.Strings                  | Strings used in the iOS app                 |
| Keywords.txt                 | App Store keywords for both apps (must be less than 100 characters) |
| macOS Description.txt        | App Store description for macOS app         |
| macOS Release Notes.markdown | What’s new in each version of the macOS app |
| macOS.strings                | Strings used in the macOS app               |
| Shared.strings               | Strings used in both apps                   |


## Contributing

If you’d like to contribute a localization, thank you! ❤️

There are a few types of files: `.strings`, `.txt`, and `.markdown`. For `.txt` and `.markdown`, translate the whole thing.


### Strings Files

`.strings` files are a little more complicated. Here’s a simple excerpt in English:

``` c
/* Modes */
"MODE" = "Mode";
"PIXELATE" = "Pixelate";
"BLUR" = "Blur";
"BLACK_BAR" = "Black Bar";
```

Here it is in French:

``` c
/* Modes */
"MODE" = "Mode";
"PIXELATE" = "Pixéliser";
"BLUR" = "Brouiller";
"BLACK_BAR" = "Barre de censure";
```

You can see the `/* Modes */` doesn’t get translated. This is simply a comment for the localizers to read. The left side of the equal sign is the *key*. Don’t change this! The right side is where you can change the English into your language. Be sure to keep the semicolon after the closing quote.

Here’s another example:

``` c
"VERSION_FORMAT" = "Version %@";
```

The `%@` is a placeholder. The app will replace this with some text while it’s running. In English, this will look something like "Version 1.2". If you wanted the number to come before the word in your language, simply move the `%@` to the front. Don’t change the order of `%@` though.

### Tips

Here are some quick tips:

* Make sure you do each file.
* Don’t localize keys in strings files.
* Don’t localize comments in the strings files. (They look `/* like this */`.)
* Run the tests to check your work. Simple run `rake` in this directory.
* Open a PR when you’re ready.

Feel free to [email me](mailto:sam@soff.es) if you have any questions about a string’s usage, need help opening a pull request, or anything else. Thanks again!


## Thanks

Huge thanks to all of the volunteers that have helped localize Redacted!

### French

* [Mattieu Gamache-Asselin](https://twitter.com/MattieuGA)
* [Maxime Bornemann](https://twitter.com/MBornemann)
* [Valentin Menardie](https://github.com/valanz)


### Dutch

* [Hidde van der Ploeg](https://twitter.com/hiddevdploeg)


### Portuguese

* [Rafael Conde](https://twitter.com/rafahari)


### Simplified Chinese

* [Yiming Tang](https://twitter.com/yiming_t)


### Danish

* [Chriztian Steinmeier](https://github.com/greystate)


### Spanish

* [Fernando Paredes](https://github.com/nanoxd)


### Romanian

* Radu Ursache

### Japanese

* [Ryo Nakano](https://github.com/ryonakano)
* [Nob Nukui](https://twitter.com/nobtaka)
