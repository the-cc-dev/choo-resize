# choo-resize
Resize Event plugin for Choo. It simply adds an event handler to the window and emits the ```state.events.RESIZE``` event.

## Installation
```
npm i -S choo-resize
```

## Example
```javascript
const choo = require('choo')
const resize = require('choo-resize')

const app = choo()

app.use(resize(true))
app.use(function (state, emitter) {
  emitter.on(state.events.RESIZE, function () {
    console.log('window resized')
  })
})

app.route('*', require('./views/main'))

app.mount('body')

```

## API
### ```resize(render)```
Takes an optional argument. If true emits the ```state.events.RENDER``` event too. If you only need to render when the page's resized.
