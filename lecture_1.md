# Web Apps
A web app is a type of website with a url and html structure, and are sort of like a cross between a website and a mobile app
- Examples: facebook
They are often transactional instead of just interactive and may have membership involved

## The HTTP Request
<mark>HTTP</mark> requests happens when you put a URL into a browser. 

What comes back to the browser is called an <mark>HTTP response</mark>.

## Anatomy of a URL
URL = Uniform Resource Locator

### https://now.feedme.com/snacks.php?flavor=salty
- http = Hyper Text Transfer Protocol
- s = secure, meaning there's an SSL certificate
- feedme.com = domain (TLD (Top Level Domain, aka .com) + domain name)
- now = subdomain/subfolder, can help differentiate domains if you want to, say, launch a mobile version, or a different version for employees... these don't have to be registered as a separate domain
- snacks.php = file/default file
- ?flavor=salty = query string, aka a set of name value pairs, where flavor is a key and salty is value, can be used to pass info to an API, can be multiple of these, separated by ampersand (flavor=salty&color=blue)
 
The domain is mapped to the <mark>IP Address</mark> of the server
- IP addresses are 32 bits, thus 4 sets of number from 0-255
    - like for example 81.138.15.252
    - everything hooked to the internet has one of these!
- every domain is hosted on a server, and is connected to it via an <mark>A Record</mark>
- the domain has a DNS that points to the server by setting the A record to the IP address of the server it belongs to
- there are multiple kinds of records, that correspond to different things
    - for example: MX is an email record

## Serverside
- servers figure out what file we want based on the url, and will send it. if it can't find it, it'll return an index instead. then it sends back html/javascript/css to the browser thru what's called an HTTP response
- sometimes there's some serverside processing that goes on, such as what goes on with React
- servers are called servers bc they "serve" files

## What is a SPA (Single Page Web App)?
Traditional Web App: 

browser sends http request thru the URL -> server sends back some html/js/css -> browser sends some user data back thru a form -> server sends a new page based on the specifications from the user data

Single Page Web App:

only one interaction, and we're not refreshing the page each time bc we have placeholders that are populated with javascript

initial request for page -> server sends back html/js/css -> send request for content from somewhere and response is immediately rendered into the established placeholders

features:
feels like a client-server app, but with the speed of a client side app, not as many round trips to the server
interactive
rich user interface
page doesn't need to be reloaded
resources are loaded as needed often in the background
various open-source frameworks based on JS have been adapted to the paradigm of an SPA (eg. AngularJS, React.js (we'll be exploring this one), Vue.js)

## Pros of SPAs
- faster loading times
- no reload needed
- feels like a mobile app

## Cons of SPAs
- poorer metric for rankings with search endings, which think that more pages is better, worse indexing
- needs state of the art browser capabilities
- needs javascript
- more security issues such as exposing data

why not just a mobile app? bc mobile apps are more expensive to develop, since you need to deal with native mobile technology. also have to deal with the app store, which is a long and challenging process and has a lot of vetting involved

why React.js?
it's very widely used and very fast
integrates great with HTML
builds apps very quickly
unfortunately there's a lot of Javascript and also JSX involved
need to learn dynamic binding, using components to extend functionality and modularize your app, using routes to create a multi-view app, using asynchronous programming to grab data from the server

# HTML & CSS Refresher

## HTML
HTML (Hyper Text Markup Language) is made up of tags that look like `<this>` that inform a browser how to present content
tags are commands that have attributes (things that further specify tag specifics) that can also have values (specify the attributes)
divided beween head and body
general convention is:
- things written in the head get displayed
- things written in the body doesnt't
tags can be containers, and have a start/end tag
the style attribute lets us use inline CSS in tags
add a slash to a standalone tag to let it serve as a beginning AND an end tag-- do this with things like `<br/>`
- entities describe a character, and start with an ampersand and end with a semicolon. these desrive a single character. eg a space is just `&nbsp;` and the copyright symbol is `&copy;`

Example of a page:
```html
<html>
    <head>
        <title>I am the page title</title>
    </head>
    <body>
        <h1>I am a header</h1>
        Hi I am some plain text bc i do not have tags!
    </body>
</html>
```
### Basics
HTML ignores whitespace, meaning no matter how many times you hit space, it'll treat it as just one

It's also case insensitive, tho it's good practice to use lowerspace

Some basic tags:
- `<p>` - paragraph/double line break
- `<br />` - single line break, not a container tag
- `<div>` - single line break, a container tag
- `<span>` - a container, no line break

Headings look like `<h1>, <h2>... <h6>`
- use `<h1>` to indicate what's most important

`<hr>` is just a horizontal line

formatting tags (these can be done with CSS)
`<STRONG>` - bold
`<EM>` - italic, and can also be written as `<i>`
`<SUP>, <SUB>` - superscript and subscript
tags can be nested

### Deploying a Web Page
For local view
1. create the file with .html extension
2. open file manager
3. drag and drop file into browser
4. save any changes, then refresh browser to view them

For web view
1. set up a github account
    - github has source control, which means that it saves the old versions of your work when you have saved them previously, which lets you restore older versions if needed
    - github also allows you to collab with people
        - lets you create branches off of a master document, which allows you to work on sections separately from the master document, so that you can develop/test new features in isolate and without affecting the master branch
        - lets you also merge side branches into the master document so that everyone can be on the same page
    - react also needs to be deployed on a separate server, so we can post something in git and then deploy it in heroku    
2. create a github repository
    - git uses repos (short for repository), which is like a project that holds a bunch of files. these are public by default
3. create a file within the repository, or upload it
4. commit the change, and tag it with a message elaborating on what you're creating
5. go to github settings, name the default branch if you wish, click on pages, select the branch to be deployed, and save
6. click deploy, and add yourpage.html to the address, and you'll be able to see your page

### Hyperlinks
they look like this: `<a href="file.html">text to be linked</a>`
`<a>` is a container tag that stands for "anchor"
click to link email and phone by writing this:
- `<a href="mailto:me@aol.com">`
- `<a href="tel:6178128969">`
to open in a new tab/window, add the attribute target="_blank", like `<a href="google.com" target="_blank">`

### Images
img tag looks like `<img src="abg.jpg">`
png can be transparent
jpg can be easily compressed while maintaining quality
not a container tag
attributes for accessibility are alt, title
ideally you should make images as small as you can while being functional. these may auto-size but this may deter performance
you can use birme.net to resize images and adjust quality
you can find stock photos at unsplash

### HTML Lists
`<ul>` unordered list, so just bullets
`<ol>` ordered list, so numbered
`<li>` list item, so this is where you put the actual text that the bullets go in
looks like this:
```html
<h1>This is a list</h1>
<ol>
    <li>item one</li>
    <li>item two</li>
</ol>
```
attributes are start and type
you can create an indent level by creating a list inside of an `<li>`
you can use CSS styling to shut off bullets by using `<ul style="list-style-type:none">`
lists are often used to group items for custom styling such as navigation
