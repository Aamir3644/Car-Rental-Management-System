## What is HTML ?
>> HyperText Markup Language is the standard markup language used to create web pages.

## What is CSS ?
>> CSS is used to describe the presentation of HTML documents. 

## What is the role of DOCTYPE (Document type) in HTML ?
```html
        <!DOCTYPE html>
```
>> DOCTYPE declaration specifies the version of HTML
>> DOCTYPE tells the browser which version of HTML it is and how to interpret the code

## What will happen if you remove DOCTYPE from HTML ?
>> Then the browser can still render the page, but they will not be able to validate the version of HTML, so it may lead to
   some compatibility issues.

## Difference between head and body tag in html ? 
```html
        <!DOCTYPE html>
        <html>
        <head>
            <title>Page Title</title>
            <meta charset="UTF-8">
            <link rel="stylesheet" href="styles.css">
        </head>
        <body>
            <h1>Hello, World!</h1>
            <p>This is a simple HTML page.</p>
            <img src="example.jpg" alt="An example image">
            <a href="https://www.example.com">Visit Example.com</a>
        </body>
        </html>
```
>> head element where you place meta information (info about the document)
>> body element where you place actual content of your HTML web page.

## Where do we place ``<script>`` tag or JS link in HTML ?
>> There are 2 ways it can be placed in HTML
>> 1) Inside <head> tag : As we know the head will load before body, so script will get fetched and executed before the html elements gets rendered. This can delay the rendering of HTML elements
>> 2) At the end of the <body> tag : We can place the script tag inside body tag just before closing it. if you are manipulating html elements in you JS code then before script gets loaded, html elements will be redered.
>> The placing will depedent on indivisual's requirement

## What is title tag in HTML ?
>> <title> tag is used to define title of a web page
>> title is shown in tab of the browser
>> SEO : search engines use the title as the main heading for search results.

## What is difference between HTML element and HTML tag ?
>> An HTML element is a complete, individual unit within an HTML document. It consists of a start tag, content, and an end
   tag.
>> An HTML tag is a specific part of the element and is used to define the start or end of the element.
>> HTML empty element or void element : <img src="example.jpg" alt="An example image">

## What is <div> element in HTML ?
>> <div> element is a container level or block scoped-level element that is used to group or structure the other elements.
>> it is used to apply common styles or css to grouped elements.

## What is difference between <div> & <span> element ?
>> <div> is a block level element & <span> is a inline element.
>> <span> element in HTML is an inline container used to apply styles or scripting to a specific section of text or content.

## What is <a> ?
>> This is a anchor tag.
>> It is used to create hyperlink. 
>> we write the url in "href" attribute. By clicking on the hyperlink it will redirect to that url.
>> if we don't use target attribute, by default the hyperlink will open in current tab. If we use "target" attribute and 
   give it value "_blank" then it will open in new tab.
>> e.g : <a href ="www.google.com" target="_blank"> Link </a>

## What are the different level elements ?
>> 1) Block Level Elements : 
```html
        Block-level elements create a "block" on the page and typically start on a new line.
        They are used to structure the main sections of a webpage, such as headings, paragraphs, divs, lists, and more.
        Examples of block-level elements include <div>, <p>, <h1>, <ul>, <li>, <table>, <form>, and others.
```

>> 2) Inline Level Elements :
```html
        Inline-level elements do not start on a new line.
        They are used for smaller structures within a block-level context, such as formatting text, links, and images.
        Examples of inline-level elements include <span>, <a>, <strong>, <em>, <img>, and others.
```

## What are Sematic Elements in HTML ?
>> Semantic elements in HTML are tags that carry meaning about the structure and content of a web page.
>> They provide meaning to the content they enclose.
>> e.g : <main>, <header>, <section>, <footer>, <nav>, <aside>, etc.

## What are the ways to apply css in HTML ?
```html
    (1) Using the inline css
        e.g : <h1 style="text-align: center; color: red"> Hello World <h1>
        
    (2) Using the style tag inside head tag
        e.g :   <head>
                    <title>
                        My HTML Page
                    </title>
                    <style>
                        p {
                            color: red;
                            text-align: center;
                        }
                    </style>
                </head>
                <!-- p is called css selector -->
                <!-- color, text-align are called css property -->
                <!-- red, center are called css value -->
        In above example, what will happen is css will get apply to all <p> elements available in the page. In this way we can avoid writing code again and again for same elements.

    (3) Creating a different css file and link that file to the HTML page
        e.g:    <head>
                    <title>
                        My HTML Page
                    </title>
                    <link rel="stylesheet" href="styles.css">
                </head>
                <!-- using link tag we can link the CSS file with HTML page. "rel" attribute used for defining what is the relation of the file with this HTML page  -->
```

## Combination Selectors :
>> (1) Descendant Selectors :
                The descendant selector selects all elements that are descendants of a specified element.
        e.g:
```css
                            /* Selects all <p> elements inside a <div> */
                            div p {
                                color: blue;
                            }
```
>> (2) Grouping Selectors :
                You can group multiple selectors together by separating them with commas.
        e.g:
```css
                            /* Groups multiple selectors */
                            h1, h2, h3 {
                                color: green;
                            }
```
>> There are many combinations of selectors, i have only written which i thought were important.  

## CSS Styling Precedence :
```html
        <!--Remember the Precedence with the the help of " IICTU " means Inline, Id, Class, Type, Universal-->

        (1) Inline Styles :
            Styles applied directly to an HTML element using the style attribute have the highest precedence.

        (2) ID Selectors :
            Styles applied to elements with an id attribute have higher precedence than class selectors.
            e.g : 
            CSS:    #uniqueElement {
                                        color: blue;
                    }
            HTML:   <div id="uniqueElement">This is a blue div.</div>

        (3) Class Selectors :
            Styles applied to elements with a class have lower precedence than IDs.
            e.g:
            CSS:    .highlight {
                                    font-weight: bold;
                    }
            HTML:   <p class="highlight">This is a bold paragraph.</p>

        (4) Type (Element) Selectors :
            Styles applied to elements based on their type (tag name) have lower precedence than classes.
            e.g:
            CSS : p {
                        font-style: italic;
                    }

        (5) Universal Selector :
            The universal selector has lower precedence than type selectors.
            e.g:
            CSS : * {
                        color: gray;
                    }

        (6) Importance (!important) :
            Adding !important to a style rule gives it the highest precedence. However, it is generally recommended to use !important carefully, as it can make the code harder to maintain and debugging.
```

## Pseudo Classes in CSS :
>> Pseudo-classes in CSS are selectors that enable you to select and style elements based on their state or position within
   the document structure. Pseudo-classes begin with a colon (:) followed by the name of the pseudo-class.
>> Syntax :
```css
        li:first-child {
            font-weight : bold;
        }

        li:last-child {
            color : red;
        }

        li:nth-child(3) {
            font-style : italic;
        }
        
        a: link {
            color : yellow; 
            /* now all anchor tag which has href attribute will get color yellow and those anchor tags which does not have href attribute will not get yellow color*/
        }
```

## Pseudo Elements in CSS :
>> Pseudo-elements in CSS allow you to style specific parts of an element, such as the first line, first letter, or generate
   additional content. 
>> Pseudo-elements are denoted by a double colon (::) followed by the name of the pseudo-element.
```css
        /* This will add the content in h2 element after the content it already has. "before" adds content before the content it already has*/
        h2::after {
            content : "ANY CONTENT" ;
            background-color : yellow ;
        }

        p::first-line {
            color : red ;
        }
```

## Absolute Positioning :
>> In a webpage, elements are normally arranged in a flow, one after another, based on the order they appear in the HTML
   document.
>> When you apply ``position : absolute`` to a element, it is taken out of normal flow. It's like lifting it off page and
   placing it wherever you want, without affecting the position of other elements.It will overlap other elements but will not affect their position.
>> Once positioned, you can use properties like top, right, bottom, and left to specify where the absolutely positioned
   element should appear.
>> But when you apply absolute position to a element, the coordinates that you write has to be in relation of any parent
   element. By default the coordinates are in relation with the viewport.
```css
        body {
            position : relative;
        }
        button {
            position : absolute;
            top: 60px ;
            left : 50px ;
        }
```
```html
        <body>
                <div>
                    <button>I am absolutely positioned!</button>
                </div>
        </body>
```

## Float :
>> In CSS, the float property is used to specify whether an element should be placed to the left or right of its container
   allowing other elements to flow around it. 
>> when we apply float to a element, the content near it will float around the floating element.
```css
        .float-left {
            float: left;
            width: 50%;
        }
```
>> Clearing Floats :
```
When elements are floated, it's common to use the clear property to prevent subsequent elements from flowing around them.
This ensures that elements below the floated elements are not affected.
```
```css
        .clearfix::after {
        content: "";
        display: table;
        clear: both;
        /*This is called clear-fix hack method. We can also apply "clear" property to nearing element that is floating around. */
}
```

## FlexBox :
>> FlexBox is a CSS model or set of CSS properties that is used to design complex and responsive web pages.
>> FlexBox is set of CSS properties that is used for building 1-dimensional layouts.
>> When we apply ` display : flex ` to a parent element then all the direct child block elements that are on top of one
   another cause we know block elements starts on new line, will come side by side one after another.
>> There is a property called ` flex-direction ` which is by default row when we apply `display : flex` but if we want child
   elements of flex container to come on top of one another then we can do that by ` flex-direction : column `.
>> When we are using flexbox, we need to keep in mind that flex will affect to direct child elements of flex container 
   element.so if we want to align 2 elements that are sibling elements of more elements then we have wrap those 2 elements into a container that will work as our flex container, then we can easily control those two elements and set out page layout.
>> There are properties like `align-items`, `gap`, `justify-content`, etc. that we can use in flex-container to control
   flex-elements.
   inside 
>> There are properties like `flex-grow`, `flex-shrink`, `flex-basis`
>> (1) `flex-grow` : It determines whether elements are allowed to grow as large as they can or not. It has default value "0"
>> (2) `flex-shrink` : It determines whether flex-box is allowed to shrink element if necessary. It has default value "1".
>> (3) `flex-basis` : In a flex container, to adjust width of elements we do not use width property we use flex-basis.
                      It has default value "auto". It means it's initial size will be decided by its content.

## CSS-Grid :
>> CSS Grid is set of CSS properties that is used for building 2-dimensional layouts.
>> The main idea behind CSS Grid is that we divide a container element into rows and columns that can be filled with its
   child elements.
>> Grid layout is created by turning an HTML element into a grid container using the `display : grid`.
>> Direct children of grid container become grid items.
>> `grid-template-columns` property is used for defining how many columns we need and of which size. We can give size in
    pixels but it can overflow the container and can give issues if browser resizes. so that's why it is a good practice 
    to use "fr" unit to this property, because of this value the column will resize according to the free space.
>> `grid-template-rows` property is used for defining how many rows we need and of which size. its a good practice to use
    "fr" unit to this property.
>> e.g : 
```css
        .container {
            display : grid ;
            grid-template-columns : 1fr 1fr 1fr ; /* Here 3 columns are getting created. Here space between a container is divided into 3 fractions and every column is occupying 1 fraction because we gave each column same value*/
            grid-template-columns : repeat(3, 1fr) ;/* This line is shortcut. repeat funtion takes two arguments, first one is how many columns and second one is how much large they should be. Both the second and third line works the same.*/
            grid-template-rows : 1fr 1fr ; /* Here 2 rows are getting created. the vertical space i.e. height of the container will be divided into 2 fractions and every row will occupy 1 fraction of space.*/
        }
``` 
>> e.g :
```css
        .container {
            display : grid ;
            grid-container-columns : 2fr 1fr 1fr ; /* Here first columns will take double the space compared to other two
            columns. If we use "auto" for one of the column then that column will only take space that is needed for its content.*/
        }
```
>> We can use browser dev tools to see value of grid lines and and use that values in `grid-column` and `grid-row` property
   to place grid item wherever we want. Always remember that these properties are used with grid items.
>> e.g :
```css
        .element {
            grid-column : 2 / 3 ;
            grid-row : -1 / -2 ;
        }
```

## "rem" unit :
>> rem stands for "root em".Unit that is relative to the font-size of root element. Root element in HTML document is <html>.
>> 1 rem is equal to the font-size of the root element.
>> Most browsers have 16px as font-size of html element. so when we do not set font size of html, most of the time by default
>> it has the value 16px.
>> When using rem for sizing, you maintain a consistent sizing system across your project.
   