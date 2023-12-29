## What is HTML ?
>> HyperText Markup Language is the standard markup language used to create web pages.

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
>> 1) Inside <head> tag : As we know the head will load before body, so script will get fetched and executed before the html
      elements gets rendered. This can delay the rendering of HTML elements
>> 2) At the end of the <body> tag : We can place the script tag inside body tag just before closing it. if you are
      manipulating html elements in you JS code then before script gets loaded, html elements will be redered.

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
>> it is used to apply common styles to or css to grouped elements.

## What is difference between <div> & <span> element ?
>> <div> is a block level element & <span> is a inline element.
>> <span> element in HTML is an inline container used to apply styles or scripting to a specific section of text or content.

## What is <a> ?
>> This is a anchor tag.
>> It is used to create hyperlink. 
>> we write the url in "href" attribute. By clicking on the hyperlink it will redirect to that url.
>> e.g : <a href ="www.google.com"> Link </a>

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

## 