# CSS position property

An important concept to understand first is that every single element on a web page is a block. Literally a rectangle of pixels. This is easy to understand when you set the element to display: block; or if that element is block-level by default like a 
```html 
<div>
```
This means you can set a width and a height and that element will respect that. But elements that are display: inline;, like a <span> by default, are also rectangles, they just flow onto the page differently, lining up horizontally as they can.

Now that you are picturing every single page element as a block of pixels, we can talk about how positioning is used to get the blocks of pixels exactly where you want them to go.

```html

.el {
  position: static;
  position: relative;
  position: absolute;
  position: fixed;
  position: sticky;
  position: inherit;
}

```

## static
It is the default value of position property. The element is rendered in order of placement. It doesn't break the flow of the document. top/left/bottom/right attribute don't work with static position property.
Why to use: It will scale on all browser

## relative
Elements with position: relative remain in the normal flow of the document. But, unlike static elements, the left, right, top, bottom and z-index properties affect the position of the element. An offset, based on the values of left, right, top and bottom properties, is applied to the element relative to itself.

## absolute
Elements with position: absolute are positioned relative to their parent elements. In this case, the element is removed from the normal document flow. The other elements will behave as if that element is not in the document. No space is created for the element in the page layout. The values of left, top, bottom and right determine the final position of the element.

One thing to note is that an element with position: absolute is positioned relative to its closest positioned ancestor. That means that the parent element has to have a position value other than position: static.

If the closest parent element is not positioned, it is positioned relative to the next parent element that is positioned. If there's no positioned ancestor element, it is positioned relative to the <html> element.

## fixed
A fixed position element is positioned relative to the viewport, or the browser window itself. The viewport doesn’t change when the window is scrolled, so a fixed positioned element will stay right where it is when the page is scrolled.

This might be used for something like a navigation bar that you want to remain visible at all times regardless of the pages scroll position. The concern with fixed positioning is that it can cause situations where the fixed element overlaps content such that is is inaccessible. The trick is having enough space to avoid that, and tricks like this.

## sticky
Sticky positioning is really unique! A sticky element will just sit there like a static element, but as you scroll past it, if it’s parent element has room (usually: extra height) the sticky element will behave as if it’s fixed until that parent element is out of room. It sounds weird in words like that, but it’s easy to see what’s happening