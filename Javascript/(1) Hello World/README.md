# Javascript Hello World

Writing your first lines of code \*sniff\* I'm so proud.

In this tutorial

- We'll learn how to use browser development tools
- We'll learn how to embed a script in an HTML page
- We'll learn how to import a script into an HTML page as a separate file
- We'll learn how to write "Hello World" to the browser console
- We'll learn how to write "Hello World" onto the page


### Prerequisits

Before anything else, make sure you have a basic understanding of HTML.  This tutorial assumes you know at least the material covered in [this](../HTML/(1)%20Hello%20World) tutorial.

- A browser (any will do, for this tutorial I'll be using Firefox)
- A plain text editor


### Accessing your browser's development tools

Browsers come with a set of tools for developers.  These allow you to see the internal state of your web page and debug code.

Most dev-tools work in relatively the same way having an output console and an element inspector, but this tutorial assumes you're using Firefox.

In the Firefox menu, go to "Tools > Browser Tools > Web Developer Tools"

![Firefox developer tools menu](https://user-images.githubusercontent.com/5024843/116814140-3ff39600-ab25-11eb-933f-1cc80030ef25.png)

A panel should open to the right of your browser window:

![Firefox developer tools](https://user-images.githubusercontent.com/5024843/116814213-a8db0e00-ab25-11eb-9d5f-b6043ac731fa.png)

> **What's this error I'm getting?  Character encoding?**
>
> There are many ways to store text data, including the text data in your plain text HTML file!  In the modern world almost everything you'll do will be in UTF-8 encoding.  We can tell the browser this by adding `<meta charset="utf-8" />` anywhere in the `<head>` tags.

There's an overwhelming amount of stuff here, so let's break it down and isolate the parts we'll be using.

At the top of the tools panel is a tab bar.

![Dev tools tab bar](https://user-images.githubusercontent.com/5024843/116814400-d1afd300-ab26-11eb-88c5-aed7b1ef9d8d.png)

Each of these represents a separate tool set for developing web sites.  For this tutorial we'll only be concerned with "Inspector" and "Console".

Make sure **Inspector** is the active tab.

![Inspector panel](https://user-images.githubusercontent.com/5024843/116814503-43881c80-ab27-11eb-8f2c-a1c910e09823.png)

The inspector is made of two panels, on the left are all of the elements on your page, on the right are the styles for the element that's selected in the left panel.  We aren't going to be doing any work with styles for now, so feel free to minimize this panel (you can drag the line between the two panels to resize).

> **I have a third panel at the bottom of my dev tools**
>
> You may have a third panel at the bottom of your dev tools.  This is your console!  It's the exact same console that you can access by clicking on the **Console** tab; for ease of use it's accessible while in any other dev tool.  You can toggle its visibility by hitting the `ESC` key while the dev tools have focus.

Click on the **Console** tab

![Dev tools console](https://user-images.githubusercontent.com/5024843/116814755-5fd88900-ab28-11eb-80b3-f65d03ff6cf0.png)

The console is one of the most important parts of development.  In the console you can:

- see any errors or warnings
- print output from your code
- run any arbitrary Javascript directly in the browser

This last one is SUPER handy for quickly testing code.  Try it now!  Click into the console and type `2 + 3` and hit `Enter`.

### Embedding a script on the page

Let's start with a basic HTML page:

```HTML
<!DOCTYPE html>
<html>
	<head>
		<title>Hello World</title>
		<meta charset="utf-8" />
	</head>
	<body>
	</body>
</html>
```

Time to learn a new tag: `<script>`

`<script>` tags can have Javascript as a direct child.  Add some script tags to the body of your page

```HTML
<!DOCTYPE html>
<html>
	<head>
		<title>Hello World</title>
		<meta charset="utf-8" />
	</head>
	<body>
		<script type="text/javascript">
			console.log("Hello World");
		</script>
	</body>
</html>
```

> **Why am I adding scripts to the body instead of the head?**
>
> Scripts can go in either location.  Once upon a time it was a requirement that scripts appear in the head, but these days it's very common to put scripts you write at the very end of the `<body>` tags (still inside the tags though!).
> 
> Why?
> 
> HTML pages are read from top to bottom.  This includes scripts, stylesheets and elements.  If your script wants to reference an element on the page, that element needs to have been read and loaded.  By putting the script last, you ensure that everything is ready for your code.
>
> Confusing?  I promise this will start making more sense as you go on.

### Importing a script from an external file

Above we learned that you can write scripts directly on an HTML page using `<script>` tags by writing scripts between them.

This is a great way to quickly hammer an interactive page out, but as your scripts become more complex you may find it easier to have them in separate files.

First let's make a new folder in the same directory as your HTML page named `scripts`.  In it make a new file named `myFirstScript.js`.  Now remove the content of the script tags and add a `src` attribute as below:

```javascript
    <script type="text/javascript" src="scripts/myFirstScript.js"></script>  
```

> **Attribute?**
>
> HTML elements have three primary defining parts:
> - **a tagname**: The identifying name of the element (`div`, `script`, `em`, `strong`)
> - **content** or **children**: What goes between the tags.  This can be text, scripts, other elements and more depending on the type of element.
> - **attributes**: These are additional pieces of data that we feed into our element.  Different elements accept different attributes, but all take the form of `attributeName="value"`.

> **Do I have to put my script in a folder called "scripts"?**
>
> Not at all!  I just wanted to put our Javascript file in a folder to make it clear that the `src` attribute of the `script` element uses a path.  Paths on the web can take many forms, but for now just worry about these two phrases:
> - **absoulte path**: Absolute paths take the form `https://domain.com/path/to/your/file`.  Absolute paths are useful when you're linking to an object on another site, or when you want your link or reference to work no matter where your file is kept.
> - **relative path**: Relative paths take the form `path/to/your/file`.  Relative paths are great when you know where your files are *relative* to the one you're referencing them from.  This is useful if your entire site fits in one folder as it makes it self-contained and portable.  Just be careful when putting a `/` at the beginning of your path, doing that will start the path at the root of whatever file system you're on.
>
> Having said all of that, it's very common to put all of your scripts in a single folder for organization sake.

### Outputting to the console (your first script!)

Let's getting coding!

Open `myFirstScript.js` and write this in it:

```javascript
console.log("Hello World");
```

There's actually a lot here, let's unpack it all:

```javascript
 console.log("Hello World");
└───────┘
```

**`console`** is a built-in object in Javascript.  You can think of objects as containers for other bits of code.  The `console` object contains several functions to help you interact with the console in the dev tools we saw earlier

```javascript
 console.log("Hello World");
       └─┘
```

The **`.`** (pronounced: "dot") after `console` is used to access properties on `console`.  In this case we'd say "console-dot-log" indicating that we're accessing the `log` function on `console`

```javascript
 console.log("Hello World");
        └───┘
```

**`log`** is a function.  Functions are the backbone of most programming languages.  In Javascript functions are executed by putting parenthesis after their name.  Some functions take "arguments" (see below) which go inside their parenthesis.

```javascript
 console.log("Hello World");
            └─────────────┘
```

**`"Hello World"`** is a `string` that we're passing into `console.log` as an argument.  A `string` is what we call text-data in Javascript.  It's one of 7 "primitive" types in Javascript.  Primitive data is anything that is not an object; another way to think about this is that primitive data is the most granular type of data accessible to you when you code in Javascript.

For now, only worry about these three data types:

- `string`: Text-data, you can make a string by adding text between either double or single quotes
- `number`: Pretty self explanitory, numbers can be created simply by typing them out without quotation marks (ie: `console.log(5);`)
- `boolean`: `true` or `false`.  We won't be using these in this tutorial, but it's good to start thinking about them now.  True or false values can be declared by writing `true` or `false` (without quotation marks, case sensitive) (ie: `console.log(true);`)

It's important to know that some functions only take certain types of data.  `console.log`, however, is designed to be able to take any sort of data you throw at it.

```javascript
 console.log("Hello World");
                          └─┘
```

The **`;`** at the end of the line lets the browser know that this statement is over, time to read the next one.  This will make more sense as your lines of code become more complex.  The semi-colon is *techinically* optional in most cases (the browser won't throw a fit) but there are a few edge cases where not having one will change the way your code acts.  You won't run into any of these for a while, but it's a good habit to get into now.

> **What's this "built-in" business?**
>
> Coding languages come with a lot of rules and syntax to help you build your own code, but also come with functions, objects and properties to add utility.  These are called "built-ins".  `console` is a built-in object that comes with a bunch of functions for outputting data to the console.

**Save** your script.

**Reload** the page in your browser.

What changed?  (hint: you'll have to check the dev tools)


### Outputting directly to the page

Writing to the console is handy for testing code, but not very useful to your website.  Let's put some content directly on the page.

Put the following in your script:

```javascript
document.body.textContent = "Hello World";
```

**Save** your script.

**Reload** the page in your browser.

The words "Hello World" should appear on the page.

Let's break it down:

```javascript
 document.body.textContent = "Hello World";
└────────┘
```

**`document`** is a built-in object that contains all of the data for your HTML document.  This includes all of the elements on it.

```javascript
 document.body.textContent = "Hello World";
         └────┘
```

**`body`** is a property on `document`.  It's the `body` element in your document.

```javascript
 document.body.textContent = "Hello World";
              └───────────┘
```

**`textContent`** is a property on all `Element` objects.  It allows you to set (and get) the text content of the element.  Note that this isn't a function like `console.log`, `textContent` is a property which means we set it with `=`.


#### let's add some formatting

Empty out your script and replace it with:

```javascript
document.body.textContent = "<em>Hello</em> <strong>World</strong>";
```

Did this work?  If not why not?

Now try this:

```javascript
document.body.innerHTML = "<em>Hello</em> <strong>World</strong>";
```

What do you think the difference between `textContent` and `innerHTML`?


### Resources

- [MDN Javascript reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript): Full reference for Javascript including all built-ins and some fantastic tutorials

### Excersizes

- Use your script to print solve this math equation and print it to the console: `1 + 2 / 3 - 4`
- Print `"Hello World"` to the console, and then `"Goodbye World"` to a separate line in the console

When you're done it should look like this:
![Hello World, Goodbye World](https://user-images.githubusercontent.com/5024843/116821630-a0e09580-ab48-11eb-83ce-c62de6fbbbb5.png)

- Can you do the same thing but write the two lines to the page?
- Take a look at the MDN page for [Document](https://developer.mozilla.org/en-US/docs/Web/API/Document) (the object we used above).  Can you print the document's URL to the console? (note that the **type** of `document` is `Document` with a capital `D`; the object has a lowercase `d`).

### What's next?

Now that you've covered the basics of HTML and Javascript, you can either move on to CSS to learn some styling or you can continue with Javascript and learn about variables and functions.
