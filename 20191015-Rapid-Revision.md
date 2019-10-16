# Tuesday 15th October

SOLID
S       Single responsibility - one class does one thing (modular code)
O       Open for modification (think plugin extends software but does not modify it)
L       Liskov : Swap parent/child classes
I       Interfaces : keep small ie Single method
D       Dependancy injection : Design using abstract classes as good practice

Reference Type
Value Type
Stack memory
Heap memory
Primitive

    'primitive structure' ie very simple objects
    in memory we declare the object, give it a type and store its data with object in memory at        that location

        - short     16 bits/2 bytes
        - int       32 bits/4 bytes
        - long      64 bits/8 bytes
        - float     32 bits/4 bytes
        - double    64 bits/8 bytes    
        - decimal   128 bits/16 bytes
        - bit       on/off
        - byte      8 bits
        - byte[] buffer : fastest possible storage type - carries local memory on computer
        - char      
        - nibble    4 bits 1010 hexadecimal 0-9 a-f

Operator

    %                   remainder
    int/int             fractional division
    >> <<               bit shift operator multiply/divide by 2
    &&                  AND
    ||                  OR
    ^                   XOR

Struct              Mini-class : contains only primitives, stored on the stack
String              array of char[]
Pass by Reference   work with a pointer to object so no matter where you are working, if you alter the object, you alter the root object
Pass by value       copy is independent of original

Collection

    ARRAY           Index[n], fixed size, lightning fast to read because we know exact memory address
    LIST            Varying length, has an index, can place data at any place within the list
    ARRAYLIST       list of general object types (no index)
    QUEUE           FIFO : first in, first out
        ENQUEUE - add to the end of the queue
        DEQUEUE - remove from front of the queue
        PEEK    - inspect without removing first item
        CONTAINS
    STACK           LIFO : Last in, first out
        PUSH    - pushes on to the stack
        PULL    - pulls top value off the stack           
    HASHSET         Like a dictionary but with no index[] (no duplicates)
    LINKEDLIST  - Used for storing large objects with ability to add/remove items, very quickly in the middle. 
                - only stores pointers to objects, no index, slow to parse, fast to add remove
    IENUMERABLE     numeric index exists [n] eg array or list
    DICTIONARY

Generics<T> where T is any type eg String, Int etc

Abstract Class  - A class with one or more abstract methods
Abstract method - abstract void DoThis();
Interfaces      - A fully abstract class, fully public properties (not fields) and methods
                - Public keywords are missing but implied
    A Class can inherit from one CLASS/ABSTRACT CLASS but IMPLEMENT (use) many INTERFACES

    IEQUERYABLE - result of a linq query output : lazy loading ie query not run until last possible moment when data needed
    IENUMERABLE - Can enumerate/count through
    IDISPOSABLE - Used for databases, files, streams which are outside of .net complied runtime
                - a dispose method can be attached to these outside/dynamic objects (unpredictable type) so the programmer can
                - manually dispose of them
                - using (HERE {
                    - //automatically disposes of HERE items
                - })

[Serializable] ATTRIBUTE ABOVE CLASS

## WEB TERMS

Bootstrap - framework for front-end website design
JavaScript 
Angular - framework for javascript by google, used for designing responsive websites (good to connect to backend datatypes)
React - look above (Facebook) virtual DOM so repaint only the elements which have changed (REACT)
Redux - Global state of the application and variables across the whole app
Vue  - framework for javascript (best of angular and react) made by one guy, indie project
Indie Project - not backed by any big company, small organisation
vueX - Vue with state (similar to react)
MVC - model (data) view (what the user sees) controller (handles the URL), structures page functionality
Synchronous - line by line
Asynchronous - calls a subthread and continues with the main thread, callback method run when async functions complete
TypeScript.ts - Strict javascript - all data is strictly typed like C#
NativeScript - Make mobile apps
Cordova - make mobile apps
Node.JS - Javascript runtime using chrome's V8 javascript engine, used for running async tasks on a network (STANDALONE LANGUAGE)
NPM - install modules (libraries) in JS App
Yarn - package manager for code (use yarn over JS if possible)
Bower - package manager for web, helps to handle library dependancies
Webpack - packs/bundles libraries together for easy deployment (into larger zip files)
jQuery - standardises commands across browsers
CanIUse.com - tells you the % of browsers using a features
PHP - server side scripting language, worlds most popular, facebook. Runs in the raw HTML. must be run on the webserver
Ruby - Server side scripting language, (ruby on rails) Uses spaces precicely
Python - simple programming language, slow, spaces as a part of the syntax
NuGet - package manager for microsoft packages (c# libraries)
id  - attribute for styling/accessing single element
.class - ^ for many elements (per web page)
Cookie - text file stored on the computer with anonymous functionality (with personal info on it)
REGEX - regular expression, string validation/pattern matching
Session - tracking a current flow of page-clicks on a website for a user, cleared on every visit. Normally has a timeout
API - application programming interface, expose data across the web
SPA - single page application, one URL, full app with different pages in the URL
SAAS - software as a service, cloud based storage etc
WebSockets ws:// wss:// - free way of sending real time web data across the web
web workers - JavaScript background task
cloud - someone else is running the server; you log in and use software on that server
virtual desktop - lightweight replication of a desktop with an OS, allows users to log in to any computer and recieve the same visual experience (software run on the client side, rendered at the server, streamed to client)
citrix - industry standard for virtual desktops
IP - Internet protocol - unique web address for a computer connected to the internet
Port - connection path to a server, channel inside IP :80
Protocol - set of logical instructions to be followed, one after the other/ language that carries the data
Razor - C# inline in the browser
.cshtml - a razor html page
Blazor - upgraded razor, c# in a browser at RUNTIME
IIS - free microsoft web server
Azure - microsoft webserver
AWS - amazon cloud
Apache - open source server
Lamp Stack - linux apache MySql PHP
WAMP Stack - windows replica wamp stack
Open Source - software that is free to be copied, modified and used by others, forking, git etc
MIT Licence - opensource licence
Cross Platform - software that can compile and run on different machines (operating systems, hardware etc)
MYSQL - type of sql used for web applications (free sql database)
PHPMyAdmin - online visual representation of mysql database, paid software to manage free slq database??
CORS - Cross origin response, allows web requests between domains
-ng  - angular prefix
v-for - example of vue element
document.getElementByID/tag/classname - javascript method to identify an element in the page by name
flexbox - responsive container for linear dataset 1D
grid - same but for 2D
MaterialUI - google standards for UI design
Vuetify - vue + MaterialUI
Mixin - modify CSS
Preprocessor - pre-compile CSS before use
SCSS - example of this
Responsive menu - can go from big to small, page looks good
Collapsing menu - drop down menu
Carousel - moving image on main page to attract attention
glyphicon - forward >> very small icon image
Modal popup - tiny window popup to ask a question (are you sure?)
<pre> - used to render raw text / code with all spaces intact
