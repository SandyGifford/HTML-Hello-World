# HTML Hello World

From zero to [Hello World](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program):

- First we’ll load a plane text document with just the phrase “Hello World!” In it in a browser.
- Then we’ll add some very basic formatting.
- Then we’ll learn the basic structure of an HTML document.

**BUT** before we get going there are a few things we’re going to need:

### Prerequisits

- A browser (any will do, I’m sure you have this covered already)
- A plain text editor

It’s important that you use a plain text editor (one that doesn’t have any formatting options).  Formatted text (or even unformatted text from an editor that can make formatted text) is filled with lots of other data behind the scenes that a browser won’t know how to read.

There are plenty of options, I’d recommend (VS Code)[https://code.visualstudio.com/].  Other good options are:

- [Sublime Text](https://www.sublimetext.com/) (this is a close second to VS Code for me)
- [BBEdit](https://www.barebones.com/products/bbedit/index.html)
- [Notepad++](https://notepad-plus-plus.org/downloads/) (Windows only)
- Notepad (the one that comes with Windows - NOT Worded)

Any tutorials I write are going to assume VS Code.  There’s not going to be any difference to the code you write, but I may reference keyboard commands, or post screen shots that will be different in different editors.

**SO**!  Let’s get started.


### Setting up VS Code and your first project

There’s not a lot to do here.  Once the app is downloaded and installed, pop it open!

VS Code works a lot like any other text editor, you open files and they appear (as text) in front of you.  One big thing that editors like this do that makes life a lot easier is give you the ability to open directories (folders):

From the “File” menu choose “Open…”

![VS Code File Menu/Open](https://user-images.githubusercontent.com/5024843/116785132-ed9f7000-aa65-11eb-92fe-a43c35e5e2c8.png)

You’ll get an open dialog

![Open dialog](https://user-images.githubusercontent.com/5024843/116785285-bed5c980-aa66-11eb-9613-b623c3f6e80a.png)

You’ve probably seen these before.  Find a good place for your project to live (I usually make a folder in documents called “coding” or something, but you know how you organize your computer better than I do) - navigate there and click “New Folder” in the bottom left.  Give your new folder a name, click “Create” then “Open”.

![Create folder](https://user-images.githubusercontent.com/5024843/116785295-da40d480-aa66-11eb-885f-19d9d74c83e6.png)

And we’re ready to go!

![VS Code welcome](https://user-images.githubusercontent.com/5024843/116786253-9e5c3e00-aa6b-11eb-9476-d2478d4a9be4.png)

> **Why are we opening a folder instead of just making a file?**
> 
> Although throughout this walkthrough we’ll only be using a single file, as we go forward we’ll be adding others.  VS Code gives you the option to open a folder so you can easily switch through all folders in a single project.  If you ever need to open a single file you can use the “Open…” dialog in exactly the same way except instead of choosing a folder, choose a file.


### Your first HTML file

From the menu select "File > New File".  An unnamed file will be created in the editor.

![VS Code, blank file](https://user-images.githubusercontent.com/5024843/116786291-c186ed80-aa6b-11eb-9b4d-e4ae5f839c14.png)

From the menu select "File > Save".  A save dialog will appear (it should already be in the folder you created), name your file `index.html` and click "Save".

![Save file dialog](https://user-images.githubusercontent.com/5024843/116785478-c5b10c00-aa67-11eb-88db-987b891e3d1d.png)

> **Why are we naming the file "index"?**
> 
> You could really name this file anything, but `index` has a special meaning.  Many web servers serve files directly from a folder system just like on your computer.  If you had a folder `dana` and inside of it a file `about.html` on a server, you would access it through `https://whatever.com/dana/about.html`.  If you named that same file `index.html` it could be accessed through either `https://whatever.com/dana/index.html` or (more commonly) `https://whatever.com/dana`.

And that's it!  We've created an HTML file.  `index.html` should appear in the tab at the top of the screen and in the sidebar (if you have the sidebar open)

![VS Code sidebar and tabs](https://user-images.githubusercontent.com/5024843/116785645-baaaab80-aa68-11eb-8c12-f83131db7a55.png)


### Opening your file in a browser

This changes a bit from browser to browser but in general you can (from the menu) go to "File > Open File..." (or similar).

![Firefox Menu: file > open file...](https://user-images.githubusercontent.com/5024843/116785994-8afca300-aa6a-11eb-8ccd-00e98f7a42d0.png)

Find your file in the dialog and click "Open"

![Firefox open file dialog](https://user-images.githubusercontent.com/5024843/116786082-eaf34980-aa6a-11eb-8637-fe6e61e919cd.png)

And just like that our HTML file is open!

![Blank file in Firefox](https://user-images.githubusercontent.com/5024843/116786220-72d95380-aa6b-11eb-8539-9a5e0f4b3e8b.png)

Looking a little empty though...

### Hello World

Let's put some content in that doc!

Back in VS Code, write the text "Hello World" into your document and save it.  Back to your browser, reload the page.

![Hello World!](https://user-images.githubusercontent.com/5024843/116786445-9fda3600-aa6c-11eb-90ab-84223390687b.png)

*tada* You've made your first HTML page!

> **What's up with all of this "Hello World" business?**
>
> When learning a new language the first thing you'll often write is a "Hello World" program.  This is simply the fastest easiest way to output the text "Hello World" in that language.


### HTML formatting

Let's jazz that text up a bit.  We're going to add some elements.  In HTML, elements are little bits of code that tell the browser all sorts of stuff about our page.  Most (but not all, more on that later) elements have two "tags": an "open tag" and a "close tag".  Between the tags goes the "content" or "children".  In the sentence below I'm using `em` tags to italicize "Hello", and `strong` tags to make my name bold:

```html
<em>Hello</em>, my name is <strong>Sandy</strong> and I like to code
```

Open tags take the form `<tagName>` and close tags take the form `</tagname>`.

> **What about `b` and `i`?**
> 
> If you are coming into this with slightly older HTML knowledge, you may be confused by the `strong` tag:  In older versions of HTML, we'd use `<b>Sandy</b>` to add boldness.  As of HTML 5, many formatting tags that implied the sort of formatting to be done ("b" for "bold") have been replaced by tags which suggest the *reason* you would want that formatting (I want this text to appear "strong").
> 
> This has two effects:
> - screen readers can more easily interpret the purpose of the text
> - not everyone wants their strong text to be bold (maybe you want to style it as *red*)
>
> Similarly `i` (italic) has been replaced with `em` (emphasis).

Let's use this in our document.  Add emphasis to "Hello" and make "World" strong.

When you're done your document should look something like this:

![basic formatting on your doc](https://user-images.githubusercontent.com/5024843/116787249-19742300-aa71-11eb-8de0-89649b579a7c.png)


### Structure of an HTML page

Copy/paste the following code into your document:

```html
<!DOCTYPE html>
<html>
	<head>
		<title>Hello World in HTML</title>
	</head>
	<body>
		<em>Hello</em> <strong>World</strong>
	</body>
</html>
```

Reload the page in your browser again.  What's changed?  (hint: it's not anything about the main content of your page).

Here's a brief overview of what each new tag does:
- `<!DOCTYPE html>`: This tag lets browsers know what version of HTML we're using.  Each version had a slightly different variation on the tag and it was always a huge pain to deal with.  As of HTML 5 all documents start with this simple DOCTYPE tag (it's better this way, trust me).
- `<html>`: This is your document!  In HTML (and other XML-like languages) all content after your DOCTYPE should have one common parent.  That's what the `<html>` element is for!
- `<head>`: Most things that aren't content go here.  This includes the title of your document (which appears in the browser's tab), style sheets, document meta data and more.
- `<body>`: This is where your content goes!

> **If adding all of this barely changed anything - why bother adding it?**
>
> It's true that for now it's not adding a lot of utility, but as we move on you'll find that there are more and more things that you'll want to add to the `head` section of your document.


### Resources

You may need to search the internet for some of these.  In addition to your favorite search engine, here are some good resources:

- [Stack Overflow](https://stackoverflow.com/): Asking questions here is a little tough, there's a long list of rules and if you don't follow them you get down-voted into oblivion.  **HOWEVER**, because of all of these rules it is an *excellent* repository of existing questions and answers.
- [MDN Web Reference](https://developer.mozilla.org/en-US/docs/Web/Reference): A pretty definitive reference for all things web.
  - [MDN HTML 5 Element Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element): For HTML, easily the most important page on the MDN web reference.  This will be especially important for the exercises below.


### Exercises

- Change the text that appears in the browser's tab
- Add a line break between the words "Hello" and "World"
  - Can you figure out more than one way to do this?
- Make an HTML page with at least two paragraphs, and larger "header" text at the top


### What's next?

Next it's time to dive either into CSS (if you want to learn more about formatting and styling a page) or Javascript (if you want to learn more about making a page interactive, or just the basics of traditional programming). 
