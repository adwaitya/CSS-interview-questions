## When to use Flexbox and when to use CSS grid

<img src="flex-grid.png" alt="CSS layout" />

## ***Flexbox***
Flexbox was introduced in 2009 as a new layout system, with the goal to help us build responsive web pages and organize our elements easily, and since then, it’s gained more and more attention. It turns out it’s now used as the main layout system for modern web pages.

Flexbox is a one-dimensional layout system that we can use to create a row or a column axis layout. It makes our life easier to design and build responsive web pages without having to use tricky hacks and a lot of float and position properties in our CSS code.

To start to use Flexbox, all you need to do is create a flex container using the display: flex property. After that, every element that you have inside that flex container turns into a flex item.

<img src="flex1.png" alt="flex layout" />

The main direction that our flex items take in our flex container is a row.

<img src="row.png" alt="row layout" />

We can change the direction of our flex items in our flex container very easily to a column, by passing a flex-direction: column property to our flex container.

<img src="column.png" alt="column layout" />

Flexbox has a lot of other properties that we can use to create awesome things. We can order the elements the way we want, we can reverse the order of elements, we can determine if our elements should grow or shrink, etc.

For example, let’s imagine that we have a div element and inside that div we have three elements, with the same width and height:

```html

<div id="container">
  <div id="one">1</div>
  <div id="two">2</div>
  <div id="three">3</div>
</div>

```
In our CSS, we’re using Flexbox to order and align our elements:

```css

#container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-evenly;
  padding: 10px;
}

#one,
#two, 
#three {
  width: 200px;
  height: 100%;
  background: red;
}
```

We can easily reverse the order of an element using the order property. If we wanted to change the order of the element with id of two, we would do this:

```css
#two {
  order: 3;
}
```

Now our element is the last one in the flex container. These are some of the features that Flexbox introduced to us and they’re very useful for the style and alignment of elements.

Now that we know that Flexbox is a one-dimensional layout system, let’s understand briefly how CSS grid works and differences between these layout systems.

## ***CSS grid***

If Flexbox is a powerful layout system because it’s a one-dimensional system (meaning that we can work with rows or columns) CSS Grid is considered now the most powerful layout system available.

CSS grid is a two-dimensional layout system, we can work withs rows and columns together, which means that it opens a lot of different possibilities to build more complex and organized design systems, without having to fall back to some “hacky ways” that we were using in the past.

To define a grid container, all you need to do is pass a display: grid property to your block element. Now you have a grid, so you should define how many rows and columns do you want.

To create rows you use the grid-template-rows property, and pass how many you want, like this:

> grid-template-rows: 200px 200px;

To create columns it’s almost the same, we use the grid-template-columns property:

> grid-template-columns: 200px 200px;

## ***You should consider using Flexbox when:***

-   **You have a small design to implement-** Flexbox is ideal when you have a small layout design to implement, with a few rows or a few columns

-   **You need to align elements —** Flexbox is perfect for that, the only thing we should do is create a flex container using display: flex and then define the flex-direction that we want

-   **You need a content-first design—** Flexbox is the ideal layout system to create web pages if you don’t know exactly how your content is going to look, so if you want everything just to fit in, Flexbox is perfect for that.

Of course, you can build your whole application using only Flexbox and get the same result as if you were building with CSS grid, that’s totally fine. But for a better CSS approach, to have a more concise, well-written, and maintainable application in the long-term, to create and fit your layout perfectly, the ideal method is to use CSS grid.

## ***CSS grid is better when:***
-   **You have a complex design to implement**  —  in some use cases, we have complex designs to implement, and that’s when the magic of CSS grid shows itself. The two-dimensional layout system here is perfect to create a complex design, we can use it in our favor to create more complex and maintainable web pages
-   **You need to have a gap between block elements**  —  another thing that’s very helpful in CSS grid, that we don’t have in Flexbox, is the gap property. We can define the gap between our rows or columns very easily, without having to use the margin property, which can cause some side effects especially if we’re working with many breakpoints
-   **You need to overlap elements**  —  overlap elements using CSS grid is very easy, you just need to use the grid-column and grid-row properties and you can have overlapping elements very easily. On the other hand, with Flexbox we still need to use some hacks such as margins, transforms, or absolute positioning
-   **You need a layout-first design**  — when you already have your layout design structure, it’s easier to build with CSS grid, and the two-dimensional layout system helps us a lot when we’re able to use rows and columns together, and position the elements the way we want


Before you decide which one you should use, don’t forget:

-     CSS grid is for layout, Flexbox is for alignment

Here’s an example of the right use of CSS grid, let’s imagine that we’re going to build a simple application, and the barebones of our applications is going to look like this:

<img src="cssgrid.png" alt="grid" />

## ***CSS Grid vs Flexbox***

-   CSS Grid Layout is a two-dimensional system, meaning it can handle both columns and rows, unlike flexbox which is largely a one-dimensional system (either in a column or a row).
-   A core difference between CSS Grid and Flexbox is that — CSS Grid’s approach is layout-first while Flexbox’ approach is content-first.
If you are well aware of your content before making layout, then blindly opt for Flexbox and if not, opt for CSS Grid.
-   Flexbox layout is most appropriate to the components of an application (as most of them are fundamentally linear), and small-scale layouts, while the Grid layout is intended for larger scale layouts which aren’t linear in their design.
If you only need to define a layout as a row or a column, then you probably need flexbox. If you want to define a grid and fit content into it in two dimensions — you need the grid.