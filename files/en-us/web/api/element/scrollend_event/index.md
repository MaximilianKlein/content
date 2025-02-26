---
title: "Element: scrollend event"
slug: Web/API/Element/scrollend_event
page-type: web-api-event
browser-compat: api.Element.scrollend_event
---

{{APIRef}}
{{SeeCompatTable}}

The **`scrollend`** event fires when element scrolling has completed.
Scrolling is considered completed when the scroll position has no more pending updates and the user has completed their gesture.

Scroll position updates include smooth or instant mouse wheel scrolling, keyboard scrolling, scroll-snap events, or other APIs and gestures which cause the scroll position to update.
User gestures like touch panning or trackpad scrolling aren't complete until pointers or keys have released.
If the scroll position did not change, then no scrollend event fires.

For detecting when scrolling inside a Document is complete, see the {{domxref("Document/scrollend_event", "Document: scrollend event")}}.

## Syntax

Use the event name in methods like {{domxref("EventTarget.addEventListener", "addEventListener()")}}, or set an event handler property.

```js
addEventListener("scrollend", (event) => {});

onscrollend = (event) => {};
```

## Event type

A generic {{domxref("Event")}}.

## Example

### Using `scrollend` with an event listener

The following example shows how to use the `scrollend` event to detect when the user has stopped scrolling:

```html
<div
  id="scroll-box"
  style="overflow: scroll; height: 100px; width: 100px; float: left;">
  <p style="height: 200px; width: 200px;">Scroll me!</p>
</div>
<p style="text-align: center;" id="output">Waiting on scroll events...</p>
```

```js
const element = document.querySelector("div#scroll-box");
const output = document.querySelector("p#output");

element.addEventListener("scroll", (event) => {
  output.innerHTML = "Scroll event fired, waiting for scrollend...";
});

element.addEventListener("scrollend", (event) => {
  output.innerHTML = "Scrollend event fired!";
});
```

{{EmbedLiveSample("Using_scrollend_with_an_event_listener", "100%", 120)}}

### Using `onscrollend` event handler property

The following example shows how to use the `onscrollend` event handler property to detect when the user has stopped scrolling:

```html
<div
  id="scroll-box"
  style="overflow: scroll; height: 100px; width: 100px; float: left;">
  <p style="height: 200px; width: 200px;">Scroll me!</p>
</div>
<p id="output" style="text-align: center;">Waiting on scroll events...</p>
```

```js
const element = document.querySelector("div#scroll-box");
const output = document.querySelector("p#output");

element.onscroll = (event) => {
  output.innerHTML = "Element scroll event fired, waiting for scrollend...";
};

element.onscrollend = (event) => {
  output.innerHTML = "Element scrollend event fired!";
};
```

{{EmbedLiveSample("Using_onscrollend_event_handler_property", "100%", 120)}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Element `scroll` event](/en-US/docs/Web/API/Element/scroll_event)
- [Document `scrollend` event](/en-US/docs/Web/API/Document/scrollend_event)
- [Document `scroll` event](/en-US/docs/Web/API/Document/scroll_event)
