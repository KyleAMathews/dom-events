# dom-events

Forked from https://www.npmjs.com/package/dom-events so [will build in
Webpack](https://github.com/defunctzombie/dom-events/pull/7).


DOM event binding and triggering

## api

### .on(element, name, fn [, useCapture])

Bind `fn` to be called when `name` is triggered on `element`.

```js
var eve = require('dom-events');

var div = document.createElement('div');
eve.on(div, 'click', function(ev) {
    console.log(ev);
});
```

### .off(element, name, fn [, useCapture])

Remove `fn` from being called when `name` is triggered on `element`

```js
var eve = require('dom-events');

var fn = function(ev) {
    console.log(ev);
};

var div = document.createElement('div');
eve.on(div, 'click', fn);

// emit some stuff

eve.off(div, 'click', fn);
```

### .once(element, name, fn [, useCapture])

Calls `fn` the first time the event happens and unsubcribes immediately.

### .emit(element, name [, opts])

Force emit `name` on `element`.

```js
var eve = require('dom-events');

var div = document.createElement('div');
eve.on(div, 'click', function(ev) {
    console.log(ev);
});

eve.emit(div, 'click'):
```

## license

MIT

