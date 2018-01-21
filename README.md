# JSUtil

This is just a small set of convenience functions that I've needed in many of my projects.

## Usage

### Selection

`JSUtil(sel, ctx)` - Select elements. Basically `(ctx || document).querySelectorAll(sel)`.

`JSUtil.collect(arg1[, ...])` - Return new JSUtil object containing all elements in the arguments.

`.children([idx])` - Return all children, or child `idx` if specified, of each element.

`.get(idx)` - Return element with index `idx`.

`.getObj(idx)` - Like `.get`, but wrapped in a JSUtil object.

### DOM

`JSUtil.createElement(str[, properties])` - If `str` looks like HTML, attempt to create an element from that. Otherwise, take tag name from `str` and properties from `properties`.

`.append(arg)` - Add elements described by `arg` to the beginning of the selection.

`.appendTo(arg)` - Add elements in the selection to the end of `arg`, which can be an HTML node or a JSUtil object.

`.html(str)` - Set HTML content to `str`.

`.prepend(arg)` - Add elements described by `arg` to the end of the selection.

`.remove()` - Remove elements from their respective parents.

`.replaceWith(arg)` - Replace elements with `arg` and return a JSUtil object containing the inserted nodes.

`.text(str)` - Set text content to `str`.

### Attributes

`.attr(name[, value[, prefix]])` - Get, set or remove attribute `name` depending on whether `value` is `undefined`, a string or `null`.

`.attr(attrs[, prefix])` - Set or remove attributes depending on whether the respective attribute value is a string or `null`.

`.data(name[, value])`, `.data(properties)` - Wrapper for `.attr(..., 'data-')`.

`.getAttr(name[, parents])` - Look for attribute `name` in the first element and its parents if `parents == true`. Return first match or `null` if not found.

`.getData(name[, parents])` - Wrapper for `.getAttr(..., 'data-')`.

`.val([value])` - Get or set the value property of each element.

### Events

`JSUtil.onReady(fcn)` - Call `fcn` when the DOM has finished loading.

`.on(events, fcn)`, `.off(events, fcn)` - Add or remove event handlers, where `events` is a list of events separated by spaces.

### Styling

`.addClass(className)`, `.removeClass(className)`, `.toggleClass(className)`

`.hasClass(className)` - Test if the first element has the class `className`.

`.setClass(className)` - Set class to `className`.

`.css(name, value)`, `.css(properties)` - Set CSS properties.

`.show()`, `.hide()`, `.toggle()`

### Ajax

`.ajax(url, opts[, callback])` - Send a HTTP request to `url` using the method given in `opts.method`. Request body is taken from `opts.data`.

`.get(url[, callback])` - Wrapper for `.ajax` with parameters prepared for a GET request.

`.post(url[, data][, callback])` - Wrapper for `.ajax` with parameters prepared for a POST request.

### Compatibility

`JSUtil.fillArray(arr, value)` - Implements `arr.fill(value)`.

`JSUtil.inArray(arr, search[, from])` - Implements `arr.indexOf(search, [from])`.

`JSUtil.keys(obj)` - Implements `Object.keys(obj)`.

`JSUtil.strRepeat(str, count)` - Implements `str.repeat(count)`.

### Numbers

`JSUtil.clamp(n, min, max)`

`JSUtil.formatNumber(n[, precision])` - Return an optionally rounded number with digit grouping.

`JSUtil.lerp(n, min, max)` - Linear interpolation.

`JSUtil.round(n[, precision=0])` - Round without trailing zeroes.

`JSUtil.roundFromZero(n)`, `JSUtil.roundToZero(n)` - Integer rounding away from or towards zero.

`JSUtil.shortenNumber(n, maxLength)` - Round number to up to `maxLength` characters.

`JSUtil.truncate(n)` - Remove decimal part.
