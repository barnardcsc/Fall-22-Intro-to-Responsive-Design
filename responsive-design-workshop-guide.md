## Intro to Responsive Web Design - Fall 2022

### Prerequisites

- None
- **Optional:** [Mozilla guide to start a local dev server](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/set_up_a_local_testing_server)


### Goals

- Develop familiarity with the fundamentals of responsive web design using media queries, Flexbox, and CSS Grid.


### Resources

CSC Github Page (this guide)

- [Workshop](https://github.com/Barnard-Computational-Science-Center/2022-Fall-Intro-to-Responsive-Design)


Practice / Educational Games

- [Grid Garden](https://cssgridgarden.com)
- [Flexbox Froggy](https://flexboxfroggy.com)

Guides

- [Grid Guide](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Grid Poster](https://css-tricks.com/wp-content/uploads/2022/02/css-grid-poster.png)
- [Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) 
- [Flexbox Poster](https://css-tricks.com/wp-content/uploads/2022/02/css-flexbox-poster.png)

Layout Testing

- [Grid Generator](https://cssgrid-generator.netlify.app)
- [ResponsivePX](http://www.responsivepx.com)

YouTube

- [Kevin Powell](https://www.youtube.com/kepowob)
- [Layoutland](https://www.youtube.com/c/LayoutLand)




---

### 1.0 Getting started


Download the project folder from the [CSC Github page.](https://github.com/Barnard-Computational-Science-Center/2022-Fall-Intro-to-Responsive-Design) Double-click `index.html` to open it in a browser (I'm using Chrome). Finally, open the project folder in your preferred editor (I'm using Visual Studio  Code):

```Visual Studio Code 2 > File > Open Folder > ...react-workshop-app > Open```

**(Optional)** You can also start a local development server by running the following from your project directory:

```python3 -m http.server```

While this project shouldn't require a local server, if you add additional functionality, like network requests, you will need to run a server. [See this guide for more information](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/set_up_a_local_testing_server).

### 1.1

- The initial `index.html` has some preset elements and attributes set for you. These are common across most websites.
- By default, browsers have some initial `padding` & `margin`, which we remove.


`index.html`
 
```html
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1" />
      <title>Responsive Design Workshop</title>
      <link rel="stylesheet" href="styles.css">
   </head>
   <body>
      	 <p>       
         Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
         sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
         Ut enim ad minim veniam, quis nostrud exercitation ullamco
         laboris nisi ut aliquip ex ea commodo consequat.
        </p>
   </body>
</html>
```

`styles.css`

```css
body {
     margin: 0;
     padding: 0;
}
```



### 1.2

Working on a blank canvas is difficult. Instead, try to find a website that's similar to what you are trying to build. I'll use the [CSC website](https://csc.barnard.edu) as a template to generate some ideas.

- When creating responsive websites, it's easier to start with the mobile view. Open Chrome DevTools for both the [CSC website](https://csc.barnard.edu) and `index.html`:

```
Right-click on the page > Inspect > Dimensions (on top) > iPhone SE
```

Now add the elements without worrying about styles or placement. Strive for semantic html, but don't worry about being overly accurate. Also, replace menus, logos, buttons, etc., with placeholders. I will add the following sections, replacing text with *lorem ipsum*:

- Header
- *Welcome to the CSC*  
- *What is computational science*  
- *Our values*  
- *Participate & Engage*  
- Footer

*Note:* I skipped the hero/banner image for now.


`index.html`
 
```html
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1" />
      <title>Responsive Design Workshop</title>
      <link rel="stylesheet" href="styles.css">
   </head>
   <body>
      <header>
         <div>
            <div>Menu</div>
            <div>Logo</div>
            <div>Search</div>
         </div>
      </header>
      <section>
         <div>
            <img src="images/image-1.jpg" alt="River in Iceland">
         </div>
         <div>
            <h2>Welcome to the CSC</h2>
		      	 <p>       
		         Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
		         sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
		         Ut enim ad minim veniam, quis nostrud exercitation ullamco
		         laboris nisi ut aliquip ex ea commodo consequat.
		        </p>
         </div>
      </section>
      <section>
         <div>
            <img src="images/image-2.jpg" alt="Dog">
         </div>
         <div>
            <h2>What is computational science?</h2>
		      	 <p>       
		         Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
		         sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
		         Ut enim ad minim veniam, quis nostrud exercitation ullamco
		         laboris nisi ut aliquip ex ea commodo consequat.
		        </p>
         </div>
      </section>
      <section>
         <div>
            <img src="images/image-3.jpg" alt="Bookshelf">
         </div>
         <div>
            <h2>Our Values</h2>
		      	 <p>       
		         Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
		         sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
		         Ut enim ad minim veniam, quis nostrud exercitation ullamco
		         laboris nisi ut aliquip ex ea commodo consequat.
		        </p>
         </div>
      </section>
      <section>
         <div>
            <img src="images/image-4.jpg"  alt="Person working on laptop" >
         </div>
         <div>
            <h2>Participate & Engage</h2>
		      	 <p>       
		         Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
		         sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
		         Ut enim ad minim veniam, quis nostrud exercitation ullamco
		         laboris nisi ut aliquip ex ea commodo consequat.
		        </p>
         </div>
      </section>
      
      <hr />

      <footer>
         <div >
            <h3>Departments</h3>
            <ul>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
            </ul>
         </div>
         <div >
            <h3>Teaching & Learning Centers</h3>
            <ul>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
            </ul>
         </div>
      </footer>
   </body>
</html>
```


### 1.3 Flexbox, responsive images, and line-height

- What do you think of the website so far?
- Are there any issues that immediately jump out?
  1. Images don't fit the viewport & cause horizontal scrolling
  2. Text feels cramped
  3. Navbar items should span horizontally across the header, not vertically

- Add the `line-height` property to the `body` to update the entire document
- To fix the `img` elements, set the `width` to `100%`, `display` to `block` (default value is `inline`), and `height` to `auto`.
- Add a new class called `.navbar` and set the display to `flex`. Flex containers have their own flex formatting context, and flex items - the direct children inside the container - become part of that context (they are no longer block-level boxes, as is the default for `div`).

Two flex properties to note:

- `justify-content`
  - start
  - center
  - space-between
  - space-around
  - space-evenly

- `align-items`
  - stretch
  - center
  - start
  - end

`styles.css`

```css
body {
     margin: 0;
     padding: 0;
     line-height: 1.5;
}

img {
     display: block;
     width: 100%;
     height:auto;
}

.navbar {
    background: cyan;
    display: flex;
    justify-content: space-around;
    align-items: center;
    min-height: 3rem;
}
```

```html
	  <!-- Same code are 1.1, except we added class="navbar" to <header> -->
      <header class="navbar">
         <div>
            <div>Menu</div>
            <div>Logo</div>
            <div>Search</div>
         </div>
      </header>
```


### 1.4 Desktop viewport, sections, and footer

- In Chrome DevTools, set the dimensions to responsive and use drag handle to change the width of the viewport. Is anything broken, or look particularly bad?
  1. The images are too large (taking up the entire screen)
  2. Text runs wide (should wrap at ~80 characters)
  3. In mobile, the footer should be a single centered column; as the screen gets wider, it should flow into two side-by-side columns

  
- Start by adding a `max-width` property to the `section` elements. I went with with `48rem` (48*16px = 768px). Next, center horizontally with `margin: 0 auto`. This tells the browser to assign 0 top/bottom margin and automatically calculate left/right margin. 
- Do the same for the `footer`. Also, you can remove the bullet points from the `ul` with the `list-style-type` property, and zero out your `padding`. Lastly, center the text with `text-align: center;`.
- If you remove the `max-width` property from either `section` or `footer` but retain the auto `margin`, it doesn't seem to work. Why not?

`index.html`

```html
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1" />
      <title>Responsive Design Workshop</title>
      <link rel="stylesheet" href="styles.css">
   </head>
   <body>
      <header>
         <div class="navbar">
            <div>Menu</div>
            <div>Logo</div>
            <div>Search</div>
         </div>
      </header>
      <section>
         <div>
            <img src="images/image-1.jpg" alt="River in Iceland">
         </div>
         <div>
            <h2>Welcome to the CSC</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
            </p>
         </div>
      </section>
      <section>
         <div>
            <img src="images/image-2.jpg" alt="Dog">
         </div>
         <div>
            <h2>What is computational science?</h2>
            <p>
               Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
            </p>
         </div>
      </section>
      <section>
         <div>
            <img src="images/image-3.jpg" alt="Bookshelf">
         </div>
         <div>
            <h2>Our Values</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
            </p>
         </div>
      </section>
      <section>
         <div>
            <img src="images/image-4.jpg"  alt="Person working on laptop" >
         </div>
         <div>
            <h2>Participate & Engage</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
            </p>
         </div>
      </section>

      <hr />

      <footer class="text-center">
         <div >
            <h3>Departments</h3>
            <ul>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
            </ul>
         </div>
         <div >
            <h3>Teaching & Learning Centers</h3>
            <ul>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
            </ul>
         </div>
      </footer>
   </body>
</html>
```


```css
body {
     margin: 0;
     padding: 0;
     line-height: 1.5;
}

img {
     display: block;
     width: 100%;
     height:auto;
}

section {
     margin: 0 auto;
     max-width: 48rem; /* 768px */
}

footer {
    margin: 0 auto;
    max-width: 48rem;
    text-align: center;
}

footer ul {
    list-style-type: none;
    padding: 0;
}

.navbar {
    background: cyan;
    display: flex;
    justify-content: space-around;
    align-items: center;
    min-height: 3rem;
}
```

### 2.0 Media query for the footer

While the footer is now properly centered for mobile screens, we need to update it for larger screens. To do so, we can use a media query. Media queries allow us modify our CSS based on targeted parameters, like the viewport width. Using what we covered earlier, a good way to align elements in one dimension is with flexbox. 

```css
 @media (min-width: 768px) {
     footer {
        display: flex;
        gap: 3rem;
        text-align: left;
     }
}
```

Add the above to `styles.css`. When this media query evaluates to true (when the width of the viewport is 768px or greater), the `display` property is set to `flex`. Since we didn't specify a display property for the footer except in the media query, it simply reverts back to its default value for footers when the viewport is less than 768px (`block`). Note that we also added `text-align: left` and space between the flex items with `gap`.


### 2.1 Media query for the header

If you expand the viewport for the CSC website far enough, you will notice that the header changes:

1. The hamburger menu disappears and is replaced by `< Barnard.edu` (which I will replace with `< Home`)
2. The nav items that were inside the menu now form a new block under our initial header

Start by adding all the missing items (`< Home` & 7 links), ignoring any styling or layouting issues:

```html
<header>
   <div class="navbar">
      <div>Menu</div>
      <div><a href="#">< Home</a></div>
      <div>Logo</div>
      <div>Search</div>
   </div>
   <div>
      <a href="#">Link 1</a>
      <a href="#">Link 2</a>
      <a href="#">Link 3</a>
      <a href="#">Link 4</a>
      <a href="#">Link 5</a>
      <a href="#">Link 6</a>
      <a href="#">Link 7</a>
   </div>
</header>
```

Writing out what we want to happen can help us think about ways to develop the CSS:

1. Show `Menu` only on mobile viewports.
2. Show `< Home` only on wider / desktop viewports. 
3. Never show them at the same time. 
4. Make sure to show at least one at all times.

Next, notice that the links (Link 1, Link 2, etc.) are not stacked on top of each another, even though they aren't inside a flex container. This is because the default `display` property for an anchor element is `inline`, and __not__ `block`. Still, we can apply the same `navbar` class to the parent `div` container, just like earlier. And just like the above, we only want to show this navbar on larger viewports.


```html
<header>
   <div class="navbar">
      <div class="hidden-desktop">Menu</div>
      <div class="hidden-mobile"><a href="#">< Home</a></div>
      <div>Logo</div>
      <div>Search</div>
   </div>
   <div class="navbar hidden-mobile">
      <a href="#">Link 1</a>
      <a href="#">Link 2</a>
      <a href="#">Link 3</a>
      <a href="#">Link 4</a>
      <a href="#">Link 5</a>
      <a href="#">Link 6</a>
   </div>
</header>
```

```css
@media (min-width: 48rem) {
     .hidden-desktop {
         display: none;
    }
}

@media (max-width: 48rem) {
     .hidden-mobile {
         display: none;
    }
}
```


### 2.2 More Media queries, flex-basis

Let's address some issues with the `section` elements:

1. Things still feel a bit cramped, particularly between sections.
2. Sections still feel too large on wider screens - maybe split image & text into two columns?

Starting with 1, we can simply add some `padding` to all 4 sides to each section with `padding: 2rem`. 

Next, use a media query and `display: flex` (and `gap`) to arrange the `img` and `div` in a row. Lastly, add the `flex-basis` property to make each flex item equal in size:

```css
@media (min-width: 48rem) {
    section {
        display: flex;
        gap: 2rem;
    }

    section > div {
        flex-basis: 50%;
    }
}
```

Flex-basis sets the size of the flex item. Since we have two items, we can make them "flex" the same amount of space by setting flex-basis to 50%. If we had four items that we wanted equal-sized, we could set flex-basis to 25%. Alternatively, we could set flex-basis to 100% to always have equal sized items, regardless of how many.

### 2.3 Adding a responsive "Hero" section 

The "hero" section is the first thing a user sees when they land on your website (usually an image overlayed with some text). The example I use extends the method from this [Stack Overflow post](https://stackoverflow.com/questions/43333495/text-over-image-responsive). I copy/pasted the answer and made a couple minor changes, such as updating the `.thumbnail` display from `inline-block` to `block`, setting a `max-height` and hiding the `overflow`.


```html
<!--   ↑↑↑ Header ↑↑↑ -->

<div class="thumbnail">
   <img src="images/image-5.jpg" alt="Night sky">
   <div class="caption">
      <p>Lorem Ipsum</p>
      <p>Lorem ipsum dolor sit amet</p>
   </div>
</div>

<!--   ↓↓↓ Sections & Footer ↓↓↓ -->
```

```css
.thumbnail {
    position: relative;
    display: block;
    max-height: 500px;
    overflow: hidden;
}

.caption {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate( -50%, -50% );
    text-align: center;
    color: white;
    font-weight: bold;
    font-size: 2rem;
}

@media (min-width: 48rem) {
    .caption {
        font-size: 4.5rem;
    }
}
```


### 3.0 Introducing Grid

We will finish by introducing CSS Grid Layout. Grid is similar to flexbox, but works in two dimensions (rows and columns). It also resembles the table element, but was specifically designed for creating layouts and is more dynamic, flexible, and powerful. 

Our grid will be similar to the events/calendar section on the CSC home page. Give the parent and child containers descriptive class names, like `events-grid` and `event-item` (create at least 5 `event-item` grid items):


```html
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1" />
      <title>Responsive Design Workshop</title>
      <link rel="stylesheet" href="styles.css">
   </head>
   <body>
      <header>
         <div class="navbar">
            <div class="hidden-desktop">Menu</div>
            <div class="hidden-mobile"><a href="#">< Home</a></div>
            <div>Logo</div>
            <div>Search</div>
         </div>
         <div class="navbar hidden-mobile">
            <a href="#">Link 1</a>
            <a href="#">Link 2</a>
            <a href="#">Link 3</a>
            <a href="#">Link 4</a>
            <a href="#">Link 5</a>
            <a href="#">Link 6</a>
         </div>
      </header>
      <div class="thumbnail">
         <img src="images/image-5.jpg" alt="Night sky">
         <div class="caption">
            <p>Lorem Ipsum</p>
            <p>Lorem ipsum dolor sit amet</p>
         </div>
      </div>
      <section>
         <div>
            <img src="images/image-1.jpg" alt="River in Iceland">
         </div>
         <div>
            <h2>Welcome to the CSC</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
            </p>
         </div>
      </section>
      <section>
         <div>
            <img src="images/image-2.jpg" alt="Dog">
         </div>
         <div>
            <h2>What is computational science?</h2>
            <p>
               Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
            </p>
         </div>
      </section>
      <section>
         <div>
            <img src="images/image-3.jpg" alt="Bookshelf">
         </div>
         <div>
            <h2>Our Values</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
            </p>
         </div>
      </section>
      <section>
         <div>
            <img src="images/image-4.jpg"  alt="Person working on laptop" >
         </div>
         <div>
            <h2>Participate & Engage</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
            </p>
         </div>
      </section>
      
      <!--   ↓↓↓ Events Grid Start ↓↓↓ -->
      
      <div class="events-grid">
         <div class="event-item">
            <h3>Date</h3>
            <img src="images/image-4.jpg"  alt="Person at their desk working on laptop" >
            <p>Event Name</p>
            <p>Event Information</p>
         </div>
         <div class="event-item">
            <h3>Date</h3>
            <img src="images/image-4.jpg"  alt="Person at their desk working on laptop" >
            <p>Event Name</p>
            <p>Event Information</p>
         </div>
         <div class="event-item">
            <h3>Date</h3>
            <img src="images/image-4.jpg"  alt="Person at their desk working on laptop" >
            <p>Event Name</p>
            <p>Event Information</p>
         </div>
         <div class="event-item">
            <h3>Date</h3>
            <img src="images/image-4.jpg"  alt="Person at their desk working on laptop" >
            <p>Event Name</p>
            <p>Event Information</p>
         </div>
         <div class="event-item">
            <h3>Date</h3>
            <img src="images/image-4.jpg"  alt="Person at their desk working on laptop" >
            <p>Event Name</p>
            <p>Event Information</p>
         </div>
      </div>
      
      <!--   ↑↑↑ Events Grid End ↑↑↑ -->
      
      <hr />
      <footer class="text-center">
         <div >
            <h3>Departments</h3>
            <ul>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
            </ul>
         </div>
         <div >
            <h3>Teaching & Learning Centers</h3>
            <ul>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
               <li>Lorem ipsum dolor </li>
            </ul>
         </div>
      </footer>
   </body>
</html>
```




```css
body {
     margin: 0;
     padding: 0;
     line-height: 1.5;
}

img {
     display: block;
     width: 100%;
     height: auto;
}

section {
     margin: 0 auto;
     max-width: 48rem;
     padding: 2rem;
}

footer {
     margin: 0 auto;
     max-width: 48rem;
     text-align: center;
}

footer ul {
     list-style-type: none;
     padding: 0;
}

.navbar {
     background: cyan;
     display: flex;
     justify-content: space-around;
     align-items: center;
     min-height: 3rem;
}

@media (min-width: 768px) {
     footer {
          display: flex;
          gap: 3rem;
          text-align: left;
     }
}

@media (max-width: 48rem) {
     .hidden-mobile {
         display: none;
    }
}

@media (min-width: 48rem) {
     .hidden-desktop {
         display: none;
    }
}

@media (min-width: 48rem) {
    section {
        display: flex;
        gap: 2rem;
    }

    section > div {
        flex-basis: 50%;
    }
}

.thumbnail {
    position: relative;
    display: block;
    max-height: 500px;
    overflow: hidden;
}

.caption {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate( -50%, -50% );
    text-align: center;
    color: white;
    font-weight: bold;
    font-size: 2rem;
}

@media (min-width: 48rem) {
    .caption {
        font-size: 4.5rem;
    }
}

.events-grid {
      display: grid;
      border: 3px solid blue;
}

.event-item {
     border: 3px solid red; /* To help us visualize */
}
```


### 3.1 Grid continued

You may have noticed that not much changed! Also, the new grid container suffers from some of the same issues (spacing, margin, width) that we ran into earlier. 

Fortunately, we can fix these easily. Let's start by setting the number of columns with the `grid-template-columns` property on the `events-grid` class. You can try different variations:

  - `grid-template-columns: 20% 20% 20% 20% 20%;`
  - `grid-template-columns: 50% 300px 300px;`
  - `grid-template-columns: 50% 50%;`
  - `grid-template-columns: 1fr; (Fr: fractional unit)`
 
The `1fr` value is equal to 1 fractional unit. A fractional unit is 1 part of the available space. It's similar to a percentage, but percentages include unavailable space, like gutters, column widths, and gaps.

Use the `repeat` function to make our CSS easier to read: `repeat(n, unit)` where n is the number of times to repeat the unit. For example, to create 5 equally sized grid items, we can write either:

- `grid-template-columns: 1fr 1fr 1fr 1fr 1fr;`
- `grid-template-columns: repeat(5, 1fr);`

We can also add spacing with the gap property:


```css
.events-grid {
      display: grid;
      grid-template-columns: repeat(5, 1fr);
      gap: 1rem;
      border: 3px solid blue;
}
```

Note that we haven't defined a `max-width` and that `gap` conveniently only adds spacing between the grid items, and not from the edges of the parent container.



### 3.2 Grid column start & span utility classes

- Update the `grid-template-columns` property on the `.events-grid` class to `repeat(3, 1fr)`. 
- We can control where grid items start, stop, and span with the `grid-column-start` and `grid-column` properties.
- Create some utility classes and experiment by updating your grid-items.

```html
<div class="events-grid">
   <div class="event-item col-span-2">
      <h3>Date</h3>
      <img src="images/image-4.jpg"  alt="Person at their desk working on laptop" >
      <p>Event Name</p>
      <p>Event Information</p>
   </div>
   <div class="event-item">
      <h3>Date</h3>
      <img src="images/image-4.jpg"  alt="Person at their desk working on laptop" >
      <p>Event Name</p>
      <p>Event Information</p>
   </div>
   <div class="event-item">
      <h3>Date</h3>
      <img src="images/image-4.jpg"  alt="Person at their desk working on laptop" >
      <p>Event Name</p>
      <p>Event Information</p>
   </div>
   <div class="event-item">
      <h3>Date</h3>
      <img src="images/image-4.jpg"  alt="Person at their desk working on laptop" >
      <p>Event Name</p>
      <p>Event Information</p>
   </div>
   <div class="event-item">
      <h3>Date</h3>
      <img src="images/image-4.jpg"  alt="Person at their desk working on laptop" >
      <p>Event Name</p>
      <p>Event Information</p>
   </div>
   <div class="event-item col-start-2">
      <h3>Date</h3>
      <img src="images/image-4.jpg"  alt="Person at their desk working on laptop" >
      <p>Event Name</p>
      <p>Event Information</p>
   </div>
   <div class="event-item">
      <h3>Date</h3>
      <img src="images/image-4.jpg"  alt="Person at their desk working on laptop" >
      <p>Event Name</p>
      <p>Event Information</p>
   </div>
</div>
```


```css
.events-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1rem;
      border: 3px solid blue;
}

.col-span-full {
	grid-column: 1 / -1;
}

.col-span-2 {
	grid-column: span 2;
}

.col-span-3 {
	grid-column: span 3;
}

.col-start-2 {
	grid-column-start: 2;
}
```


### 3.3 Challenge - grid media queries

While the grid holds up on larger screens, it struggles on mobile devices. Can you try to fix it? A couple of hints:

- The default display property for a div is `block`, which worked well on mobile. Maybe you don't need a grid at all until your viewport reaches a certain size: 

```css
.events-grid {
      /* display: grid; */
      /* grid-template-columns: repeat(3, 1fr); */
      /* gap: 1rem; */
      border: 3px solid blue;
}

@media (min-width: 640px) {
	.events-grid {
		display: grid;
		gap: 1rem;
		grid-template-columns: repeat(2, 1fr);
	}
}

@media (min-width: 768px) {
	.events-grid {
		grid-template-columns: repeat(3, 1fr);
	}
}
```


