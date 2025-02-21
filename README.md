Browser Detector
================

[![Build Status](https://travis-ci.org/sinergi/php-browser-detector.svg?branch=master)](https://travis-ci.org/sinergi/php-browser-detector)
[![Latest Stable Version](http://img.shields.io/packagist/v/sinergi/browser-detector.svg?style=flat)](https://packagist.org/packages/sinergi/browser-detector)
[![License](https://img.shields.io/packagist/l/sinergi/browser-detector.svg?style=flat)](https://packagist.org/packages/sinergi/browser-detector)

## ================ INFO ================

This is an updated version of sinergi/browser-detector for PHP 8.4 Compatibility. Nullable function parameters have been amended to allow null, and should be a drop in replacement to the abandoned project.

All namespaces have been left as per the original project, the only differences are the composer package name, and the function type updates.


## ======================================


Detecting the user's browser, operating system, device and language from PHP. Because browser detection is not always
reliable and evolves at all time, use with care and feel free to contribute.

## Requirements

This library uses PHP 8.0+.

## Install

It is recommended that you install the PHP Browser library [through composer](http://getcomposer.org). To do so, run the following command:

```sh
composer require ciaran-moore/browser-detector
```

## Browser Detection

The Browser class allows you to detect a user's browser and version.

### Browsers Detected

 * Vivaldi
 * Opera
 * Opera Mini
 * WebTV
 * Internet Explorer
 * Pocket Internet Explorer
 * Microsoft Edge
 * Konqueror
 * iCab
 * OmniWeb
 * Firebird
 * Firefox
 * Iceweasel
 * Shiretoko
 * Mozilla
 * Amaya
 * Lynx
 * Safari
 * Chrome
 * Navigator
 * GoogleBot
 * Yahoo! Slurp
 * W3C Validator
 * BlackBerry
 * IceCat
 * Nokia S60 OSS Browser
 * Nokia Browser
 * MSN Browser
 * MSN Bot
 * Netscape Navigator
 * Galeon
 * NetPositive
 * Phoenix
 * SeaMonkey
 * Yandex Browser
 * Comodo Dragon
 * Samsung Browser
 * wkhtmltopdf

### Usage

```php
use Sinergi\BrowserDetector\Browser;

$browser = new Browser();

if ($browser->getName() === Browser::IE && $browser->getVersion() < 11) {
    echo 'Please upgrade your browser.';
}
```

#### Compatibility Mode

Detect if Internet Explorer is in Compatibility Mode and send the correct header to have the browser render the page in its standard mode. This must be called before any output is sent to the browser.

```php
use Sinergi\BrowserDetector\Browser;

$browser = new Browser();

if ($browser->getName() === Browser::IE && $browser->isCompatibilityMode()) {
    $browser->endCompatibilityMode();
}
```

## OS Detection

The OS class allows you to detect a user's operating system and version.

### OS Detected

 * Windows
 * Windows Phone
 * OS X
 * iOS
 * Android
 * Chrome OS
 * Linux
 * SymbOS
 * Nokia
 * BlackBerry
 * FreeBSD
 * OpenBSD
 * NetBSD
 * OpenSolaris
 * SunOS
 * OS2
 * BeOS

### Usage

```php
use Sinergi\BrowserDetector\Os;

$os = new Os();

if ($os->getName() === Os::IOS) {
    echo 'You are using an iOS device.';
}
```

## Device Detection

The Device class allows you to detect a user's device.

### Device Detected

 * iPad
 * iPhone
 * Windows Phone
 * Lumia

### Usage

```php
use Sinergi\BrowserDetector\Device;

$device = new Device();

if ($device->getName() === Device::IPAD) {
    echo 'You are using an iPad.';
}
```

## Language Detection

The Language class allows you to detect a user's language.

### Usage

```php
use Sinergi\BrowserDetector\Language;

$language = new Language();

if ($language->getLanguage() === 'de') {
    echo 'Get this website in german.';
}
```

## License

PHP Browser is licensed under [The MIT License (MIT)](LICENSE).
