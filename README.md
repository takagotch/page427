### https://takagotch.github.io/page427/
---



```
```

---
[twitter]: http://twitter.com/raintek_
[demo]: https://rainner.github.io/scroller/
[mit]: http://www.opensource.org/licenses/mit-license.php

# Scroller

![Scroller](https://raw.githubusercontent.com/rainner/scroller/master/thumb.jpg)

Listen for scroll events on the document or a custom target element, fire events while scrolling, or jump to a specified section.
Useful for triggering CSS animations as the user scrolls a page, or to lazy-load content when a section enters the visible area of the screen. This class uses throttling to preserve scroll performance.

[Check out the demo][demo]

### Install

```bash
npm install rainner/scroller
```

### Usage
Import as a module and bundle using your preferred bundling method (Webpack, Gulp, etc)...

```js
// import class
import Scroller from 'scroller';

// setup scroller ( scrollElement, options )
let scroller = new Scroller( null, {} );

// when scroll position changes (realtime)
scroller.onScroll( e => {
    console.log( 'onScroll', e.pageY );
});

// when scroll position changes (throttled)
scroller.onChange( pos => {
    console.log( 'onChange', pos );
});

// monitor elements as they enter/leave the viewport
scroller.onVisible( '.someClass', ( elm, visible, pos ) => {
  console.log( 'onVisible', elm, visible, pos );
});

// when scrolling up (triggered once)
scroller.onUp( pos => {
    console.log( 'onUp', pos );
});

// when scrolling down (triggered once)
scroller.onDown( pos => {
    console.log( 'onDown', pos );
});

// when scroll position is greater than a number (triggered once)
scroller.moreThan( 200, pos => {
    console.log( 'moreThan 200', pos );
});

// when scroll position is less than a number (triggered once)
scroller.lessThan( 200, pos => {
    console.log( 'lessThan 200', pos );
});

// scroll to position by number
button.addEventListener( 'click', e => {
    scroller.jumpTo( 500 );
});

// scroll to position by selector
button.addEventListener( 'click', e => {
    scroller.jumpTo( '#someElement' );
});
```

### Author

Rainner Lins: [@raintek_][twitter]

### License

Licensed under [MIT][mit].



