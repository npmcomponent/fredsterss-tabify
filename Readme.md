*This repository is a mirror of the [component](http://component.io) module [fredsterss/tabify](http://github.com/fredsterss/tabify). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/fredsterss-tabify`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# Tabify

[Component](https://github.com/component/component) for turning a list into tabs.

Inspired by [stagas/tabify](https://github.com/stagas/tabify) but without all the DOM configuration and with IE support.

## Installation

Install with [component(1)](http://component.io):

```
$ component install fredsterss/tabify
```
You will need to style the default active tab link class ``.active`` and the hidden tab target class ``.hidden`` to see it working.

Your document must have a valid DOCTYPE otherwise IE doesn't support ``querySelectorAll``.

## API

### Tabify(links, targets, [options])
Turns an array of ``links`` into tabs that toggle visibility on the corresponding array of ``targets``. Use ``options.hiddenClass`` and ``options.activeClass`` to override the default classes applied to hidden tab content elements and active tab links respectively.

With the following DOM:
```html
<ul id="tabs">
  <li>tab 1</li>
  <li>tab 2</li>
  <li>tab 3</li>
</ul>

<div id="tabs-holder">
  <div>content for tab 1</div>
  <div>content for tab 2</div>
  <div>content for tab 3</div>
</div>
```
The following javascript tabifys the links.
```js
var links = document.getElementById('tabs').getElementsByTagName('li');
var targets = document.getElementById('tabs-holder').getElementsByTagName('div');

var tabify = require("tabify");
var tabs = tabify(links, targets);
```

Tabify prioritises convention over DOM configuration, so mismatching links / targets will be ignored by Tabify. For more intel, check out the [example.html](example.html).