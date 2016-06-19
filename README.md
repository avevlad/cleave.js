# Cleave.js

[![Travis](https://img.shields.io/travis/nosir/cleave.js.svg?maxAge=2592000)](https://travis-ci.org/nosir/cleave.js)

Cleave.js has a simple purpose: to help you format input text content automatically.

The idea is to provide an easy way to increase readability when you are typing. By using the library, you won't need to write any mind-blowing regular expressions or mask patterns to format input text.

However, this isn't meant to replace any form validation or mask library, you should still sanitize and validate your data in backend.

**tl;dr** [the demo page]()

## Features
- Credit card number formatting
- Phone number formatting (lib separated by countries to reduce size)
- Date formatting
- Numeral formatting
- Customize delimiter, prefix and blocks pattern
- CommonJS / AMD support

## Installation

#### npm

```
npm install --save cleave.js
```

#### bower

```
bower install --save cleave.js
```

#### throwback
Grab the file from [dist](https://github.com/nosir/cleave.js/tree/master/dist) folder

## Usage

Simply include

```html
<script src="cleave.min.js"></script>
<script src="cleave-phone.{country}.js"></script>
```

> `cleave-phone.js` is only required when phone shortcut mode is enabled. See more in documentation: [phone lib usage](https://github.com/nosir/cleave.js/blob/master/doc/phone-lib-usage.md) section

Then have a text field

```html
<input class="input-phone" type="text"/>
```

Now in your JavaScript

```javascript
var cleave = new Cleave('.input-phone', {
    phone:      true,
    regionCode: '{country}'
});
```

More examples: [the demo page](https://github.com)

#### CommonJS (Node.js)
```javascript
var Cleave = require('cleave.js');
require('cleave.js/dist/plugin/cleave-phone.{country}');

var cleave = new Cleave(...)
```

#### AMD

```javascript
require(['cleave.js/dist/cleave.min', 'cleave.js/dist/plugin/cleave-phone.{country}'], function (Cleave) {
    var cleave = new Cleave(...)
});
```

## Documentation

- [JavaScript API](https://github.com/nosir/cleave.js/blob/master/doc/js-api.md)
    - [Constructor](https://github.com/nosir/cleave.js/blob/master/doc/constructor.md)
    - [Options](https://github.com/nosir/cleave.js/blob/master/doc/options.md)
    - [Public methods](https://github.com/nosir/cleave.js/blob/master/doc/public-methods.md)
- [Phone lib usage](https://github.com/nosir/cleave.js/blob/master/doc/phone-lib-usage.md)

## Building & Running tests

```
npm install
```

Build assets

```
gulp build
```

Run unit tests and js code validation 

```
gulp mocha && gulp jshint
```

## References

- Payment credit card number IIN https://en.wikipedia.org/wiki/Payment_card_number#Issuer_identification_number_.28IIN.29
- Google phone numbers formatting https://github.com/googlei18n/libphonenumber
- Decimal mark and thousands separating style https://en.wikipedia.org/wiki/Decimal_mark#Examples_of_use

## Licence

Cleave.js is licensed under the [Apache License Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)

- Google [libphonenumber](https://github.com/googlei18n/libphonenumber) is included under its [Apache License Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)
