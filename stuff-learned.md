## 01

<some DOM element>.play()
.currentTime

addEventListener('transitionend', ...) [after an animation has ended
]

e.propertyName !== 'transform'

http://keycode.info/

## 02

- by default CSS elements will rotate (via tranform()) around their middle - you can change this with transform-origin
  - by default, this transforms the origin along the x-axis, so `tranform-origin: 100%` would move the origin to the right-most edge of the element
- you can use deg to rotate: `transform: rotate(90deg)`
- you can add a duration to transforms:
  - Bos uses `transition: all 0.5s`
  - could also do this: `transition: transform 0.5s`
  - or this `transition-duration: 0.5s` (I think I like this best)
- you can play with the easing with `transition-timing-function`
  - COOL BEANS: in Chrome inspector, you can click on the little curvy icon and then DRAG AROUND THINGS TO MODIFY THE CURVE VISUALLY
  - COOL BEANS: you can use the mousewheel in Chrome inspector to modify numeric values
- you can use window.setInterval() to run a function every x ms: [docs](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setInterval)

## 03 - updating CSS variables with JS

- there are now actual CSS variables. O M G
  - define with --blah
  - use wherever you normally would with var(--blah)
    - ex: --spacing: 10px; (define) ==> padding: var(--spacing) (use)
  - they are scoped (apparently using the cascade rules)
- you can add a blur effect:
  - `filter: blur(10px)`
- the event 'mousemove' is useful for things like sliders where you may want things to register **as you're sliding things around**
- .dataset property on a DOM element will give you a DOMStringMap that has all the key:value pairs of any attributes in the DOM element that are like data-<blah>
  - ex: if you have an <input data-name="bo" data-size="10px">, then that dom.dataset gives you back {name: "bo", size: "10px"}
- you can manipulate global css variables with `document.documentElement.style.setProperty(cssvarname, cssvarvalue)`

## 04 - functional practice with Array functions

- if sorting on numerical properties of objects doing a simple subtraction is slickest
  - ex. a.year - b.year
- two suggestions for going from NodeList to Array:
  - Array.from(nodelist)
  - targetArray = [...nodelist];
- got bit by this: if (!obj[key]) works when you have obj[key] undefined...but it ALSO works when ojb[key] is 0!!!
