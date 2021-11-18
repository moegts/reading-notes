# Read: 13 - Local Storage

## DIVING IN

### what is it

#### Persistent local storage is one of the areas where native client applications have held an advantage over web applications. For native applications, the operating system typically provides an abstraction layer for storing and retrieving application-specific data like preferences or runtime state. These values may be stored in the registry, INI files, XML files, or some other place according to platform convention. If your native client application needs local storage beyond key/value pairs, you can embed your own database, invent your own file format, or any number of other solutions

#### Historically, web applications have had none of these luxuries. Cookies were invented early in the web’s history, and indeed they can be used for persistent local storage of small amounts of data. But they have three potentially dealbreaking downsides

#### Before HTML5, all attempts to achieve this were ultimately unsatisfactory in different ways

### A BRIEF HISTORY OF LOCAL STORAGE HACKS BEFORE HTML5

#### In the beginning, there was only Internet Explorer. Or at least, that’s what Microsoft wanted the world to think. To that end, as part of the First Great Browser Wars, Microsoft invented a great many things and included them in their browser-to-end-all-browser-wars, Internet Explorer. One of these things was called DHTML Behaviors, and one of these behaviors was called userData

#### userData allows web pages to store up to 64 KB of data per domain, in a hierarchical XML-based structure. IE does not present any form of permissions dialog, and there is no allowance for increasing the amount of storage available

#### In 2002, Adobe introduced a feature in Flash 6 that gained the unfortunate and misleading name of «Flash cookies.» Within the Flash environment, the feature is properly known as Local Shared Objects. Briefly, it allows Flash objects to store up to 100 KB of data per domain. Brad Neuberg developed an early prototype of a Flash-to-JavaScript bridge called AMASS , but it was limited by some of Flash’s design quirks. By 2006, with the advent of ExternalInterface in Flash 8, accessing LSOs from JavaScript became an order of magnitude easier and faster. Brad rewrote AMASS and integrated it into the popular Dojo Toolkit under the moniker dojox.storage. Flash gives each domain 100 KB of storage «for free.» Beyond that, it prompts the user for each order of magnitude increase in data storage

#### In 2007, Google launched Gears, an open source browser plugin aimed at providing additional capabilities in browsers. Gears provides an API to an embedded SQL database based on SQLite. After obtaining permission from the user once, Gears can store unlimited amounts of data per domain in SQL database tables

#### In the meantime, Brad Neuberg and others continued to hack away on dojox.storage to provide a unified interface to all these different plugins and APIs. By 2009, dojox.storage could auto-detect Adobe Flash, Gears, Adobe AIR, and an early prototype of HTML5 storage that was only implemented in older versions of Firefox

##### As you survey these solutions, a pattern emerges: all of them are either specific to a single browser, or reliant on a third-party plugin. Despite heroic efforts to paper over the differences , they all expose radically different interfaces, have different storage limitations, and present different user experiences. So this is the problem that HTML5 set out to solve: to provide a standardized API, implemented natively and consistently in multiple browsers, without having to rely on third-party plugins

### INTRODUCING HTML5 STORAGE

#### What I will refer to as «HTML5 Storage» is a specification named Web Storage, which was at one time part of the HTML5 specification proper, but was split out into its own specification for uninteresting political reasons. Certain browser vendors also refer to it as «Local Storage» or «DOM Storage.» The naming situation is made even more complicated by some related, similarly-named, emerging standards that I’ll discuss later in this chapter

#### So what is HTML5 Storage? Simply put, it’s a way for web pages to store named key/value pairs locally, within the client web browser. Like cookies, this data persists even after you navigate away from the web site, close your browser tab, exit your browser, or what have you. Unlike cookies, this data is never transmitted to the remote web server . Unlike all previous attempts at providing persistent local storage, it is implemented natively in web browsers, so it is available even when third-party browser plugins are not

### HTML5 STORAGE SUPPORT

- +3.5+4.0+4.0+10.5+2.0+2.0+

#### From your JavaScript code, you’ll access HTML5 Storage through the localStorage object on the global window object. Before you can use it, you should detect whether the browser supports it

#### Instead of writing this function yourself, you can use Modernizr to detect support for HTML5 Storage

#### if { // window.localStorage is available! // no native support for HTML5 storage : // maybe try dojox.storage or a third-party solution

### USING HTML5 STORAGE

#### HTML5 Storage is based on named key/value pairs. You store data based on a named key, then you can retrieve that data with the same key. The named key is a string. The data can be any type supported by JavaScript, including strings, Booleans, integers, or floats. However, the data is actually stored as a string. If you are storing and retrieving anything other than strings, you will need to use functions like parseInt or parseFloat to coerce your retrieved data into the expected JavaScript datatype

#### Calling setItem with a named key that already exists will silently overwrite the previous value. Calling getItem with a non-existent key will return null rather than throw an exception

#### Like other JavaScript objects, you can treat the localStorage object as an associative array. Instead of using the getItem and setItem methods, you can simply use square brackets. For example, this snippet of code: var foo = localStorage.getItem

### localStorage

#### There are also methods for removing the value for a given named key, and clearing the entire storage area

#### Calling removeItem with a non-existent key will do nothing

#### Finally, there is a property to get the total number of values in the storage area, and to iterate through all of the keys by index

#### If you call key with an index that is not between 0–, the function will return null

### TRACKING CHANGES TO THE HTML5 STORAGE AREA

#### If you want to keep track programmatically of when the storage area changes, you can trap the storage event. The storage event is fired on the window object whenever setItem, removeItem, or clear is called and actually changes something. For example, if you set an item to its existing value or call clear when there are no named keys, the storage event will not fire, because nothing actually changed in the storage area

#### The storage event is supported everywhere the localStorage object is supported, which includes Internet Explorer 8. IE 8 does not support the W3C standard addEventListener . Therefore, to hook the storage event, you’ll need to check which event mechanism the browser supports

### window

#### The handle_storage callback function will be called with a StorageEvent object, except in Internet Explorer where the event object is stored in window.event

#### At this point, the variable e will be a StorageEvent object, which has the following useful properties

### STORAGEEVENT OBJECT

- Note: the url property was originally called uri. Some browsers shipped with that property before the specification changed. For maximum compatibility, you should check whether the url property exists, and if not, check for the uri property instead.

- The storage event is not cancelable. From within the handle_storage callback function, there is no way to stop the change from occurring. It’s simply a way for the browser to tell you, «hey, this just happened. There’s nothing you can do about it now; I just wanted to let you know».

### LIMITATIONS IN CURRENT BROWSERS

#### In talking about the history of local storage hacks using third-party plugins, I made a point of mentioning the limitations of each technique, such as storage limits. I just realized that I haven’t mentioned anything about the limitations of the now-standardized HTML5 Storage. I’ll give you the answers first, then explain them. The answers, in order of importance, are «5 megabytes,» «QUOTA_EXCEEDED_ERR,» and «no»

#### «5 megabytes» is how much storage space each origin gets by default. This is surprisingly consistent across browsers, although it is phrased as no more than a suggestion in the HTML5 Storage specification. One thing to keep in mind is that you’re storing strings, not data in its original format. If you’re storing a lot of integers or floats, the difference in representation can really add up. Each digit in that float is being stored as a character, not in the usual representation of a floating point number

#### «QUOTA_EXCEEDED_ERR» is the exception that will get thrown if you exceed your storage quota of 5 megabytes. «No» is the answer to the next obvious question, «Can I ask the user for more storage space?» At time of writing , no browser supports any mechanism for web developers to request more storage space. Some browsers allow the user to control each site’s storage quota, but it is purely a user-initiated action, not something that you as a web developer can build into your web application

### HTML5 STORAGE IN ACTION

#### Let’s see HTML5 Storage in action. Recall the Halma game we constructed in the canvas chapter. There’s a small problem with the game: if you close the browser window mid-game, you’ll lose your progress. But with HTML5 Storage, we can save the progress locally, within the browser itself. Here is a live demonstration. Make a few moves, then close the browser tab, then re-open it. If your browser supports HTML5 Storage, the demonstration page should magically remember your exact position within the game, including the number of moves you’ve made, the position of each of the pieces on the board, and even whether a particular piece is selected

### localStorage = gPieces

#### As you can see, it uses the localStorage object to save whether there is a game in progress . If so, it iterates through the pieces and saves the row and column number of each piece. Then it saves some additional game state, including which piece is selected , whether the piece is in the middle of a potentially long series of hops , and the total number of moves made so far

#### On page load, instead of automatically calling a newGame function that would reset these variables to hard-coded values, we call a resumeGame function instead. Using HTML5 Storage, the resumeGame function checks whether a state about a game-in-progress is stored locally. If so, it restores those values using the localStorage object

#### The most important part of this function is the caveat that I mentioned earlier in this chapter, which I’ll repeat here: Data is stored as strings. If you are storing something other than a string, you’ll need to coerce it yourself when you retrieve it. For example, the flag for whether there is a game in progress is a Boolean. In the saveGameState function, we just stored it and didn’t worry about the datatype

#### Similarly, the number of moves is stored in gMoveCount as an integer

### BEYOND NAMED KEY-VALUE PAIRS: COMPETING VISIONS

#### While the past is littered with hacks and workarounds, the present condition of HTML5 Storage is surprisingly rosy. A new API has been standardized and implemented across all major browsers, platforms, and devices. As a web developer, that’s just not something you see every day, is it? But there is more to life than «5 megabytes of named key/value pairs,» and the future of persistent local storage is… how shall I put it… well, there are competing visions

### One vision is an acronym that you probably know already: SQL. In 2007, Google launched Gears, an open source cross-browser plugin which included an embedded database based on SQLite. This early prototype later influenced the creation of the Web SQL Database specification. Web SQL Database provides a thin wrapper around a SQL database, allowing you to do things like this from JavaScript

#### ↶ actual working code in 4 browsers openDatabase'documents', '1

#### As you can see, most of the action resides in the string you pass to the executeSql method. This string can be any supported SQL statement, including SELECT, UPDATE, INSERT, and DELETE statements. It’s just like backend database programming, except you’re doing it from JavaScript! Oh joy

#### The Web SQL Database specification has been implemented by four browsers and platforms

### WEB SQL DATABASE SUPPORT

- ··4.0+4.0+10.5+3.0+2.0+

#### Of course, if you’ve used more than one database product in your life, you are aware that «SQL» is more of a marketing term than a hard-and-fast standard. Sure, there is an actual SQL specification , but there is no database server in the world that conforms to that and only that specification. There’s Oracle’s SQL, Microsoft’s SQL, MySQL’s SQL, PostgreSQL’s SQL, and SQLite’s SQL. Indeed, each of these products adds new SQL features over time, so even saying «SQLite’s SQL» is not sufficient to pin down exactly what you’re talking about. You need to say «the version of SQL that shipped with SQLite version X.Y.Z»

#### This specification has reached an impasse: all interested implementors have used the same SQL backend , but we need multiple independent implementations to proceed along a standardisation path. Until another implementor is interested in implementing this spec, the description of the SQL dialect has been left as simply a reference to Sqlite, which isn't acceptable for a standard

#### It is against this backdrop that I will introduce you to another competing vision for advanced, persistent, local storage for web applications: the Indexed Database API, formerly known as «WebSimpleDB,» now affectionately known as «IndexedDB»

#### The Indexed Database API exposes what’s called an object store. An object store shares many concepts with a SQL database. There are «databases» with «records,» and each record has a set number of «fields.» Each field has a specific datatype, which is defined when the database is created. You can select a subset of records, then enumerate them with a «cursor.» Changes to the object store are handled within «transactions»

#### If you’ve done any SQL database programming, these terms probably sound familiar. The primary difference is that the object store has no structured query language. You don’t construct a statement like «SELECT * from USERS where ACTIVE = 'Y'». Instead, you use methods provided by the object store to open a cursor on the database named «USERS,» enumerate through the records, filter out records for inactive users, and use accessor methods to get the values of each field in the remaining records. An early walk-through of IndexedDB is a good tutorial of how IndexedDB works, giving side-by-side comparisons of IndexedDB and Web SQL Database

#### At time of writing, IndexedDB has only been implemented in a beta version of Firefox 4. Google has stated that they are considering IndexedDB support for Chromium and Google Chrome. And even Microsoft has said that IndexedDB «is a great solution for the web»

#### So what can you, as a web developer, do with IndexedDB? At the moment, virtually nothing beyond some technology demos. A year from now? Maybe something. Check the «Further Reading» section for links to some good tutorials to get you started
