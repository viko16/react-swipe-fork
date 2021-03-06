# Just another fork of react-swipe

[![npm version](http://badge.fury.io/js/react-swipe-fork.svg)](http://badge.fury.io/js/react-swipe-fork)

## Demo

Check out the [demo](http://voronianski.github.io/react-swipe/demo/) from a mobile device (real or emulated).

<img src="https://user-images.githubusercontent.com/974035/34205307-30965ccc-e582-11e7-9384-fe1ce991ff4f.gif" width="600" />

## Install

```bash
npm install react swipe-js-iso-fork react-swipe-fork --save
```

## Usage

### Examples

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import ReactSwipe from 'react-swipe';

const Carousel = () => {
  let reactSwipeEl;

  return (
    <div>
      <ReactSwipe
        className="carousel"
        swipeOptions={{ continuous: false }}
        ref={el => (reactSwipeEl = el)}
      >
        <div>PANE 1</div>
        <div>PANE 2</div>
        <div>PANE 3</div>
      </ReactSwipe>
      <button onClick={() => reactSwipeEl.next()}>Next</button>
      <button onClick={() => reactSwipeEl.prev()}>Previous</button>
    </div>
  );
};

ReactDOM.render(<Carousel />, document.getElementById('app'));
```

### Props

- `swipeOptions: ?Object` - supports all original options from [Swipe.js config](https://github.com/voronianski/swipe-js-iso#config-options). If passed object differs from the previous one `react-swipe` will re-initiate underlying Swipe.js instance with fresh options

- `style: ?Object` - object with 3 keys (see [defaults](https://github.com/voronianski/react-swipe/blob/gh-pages/src/index.js#L28)):

  - `container: ?Object`
  - `wrapper: ?Object`
  - `child: ?Object`

- regular props as `className`, `id` for root component are also supported

- `childCount: ?Number` - use it to explicitely tell `react-swipe` that it needs to re-initiate underlying Swipe.js instance. For example, by setting the `childCount` prop to the `length` of the images array that you pass into `react-swipe`, re-rendering will take place when the `images.length` differs from the previous `render` pass:

```js
<ReactSwipe childCount={images.length}>{images}</ReactSwipe>
```

## Methods

Component proxies all [Swipe.js instance methods](https://github.com/voronianski/swipe-js-iso/#swipe-api).

### Playground

Configure the ReactSwipe component in a sandbox environment at [CodeSandbox](https://codesandbox.io/s/q86m8n9qnj).

---

**MIT Licensed**
