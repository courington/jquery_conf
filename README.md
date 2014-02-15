# jQuery Conf - San Diego 2/12/2014

## Dave Methvin
### Performance
  - browser is not just a run-time library
    - incredibly rich environment with features
    - must fit js into that env responsibly
  - find the slow stuff && make it not slow ;)
  - JS loop optimization
  - don't waste time figuring out optimizations that don't matter
    - you can screw up the code more for the future
    - 97% doesn't matter / focus on the 3% to optimize
    - fix the thing that's slow after you've determined it's slow
  - prefetch content / tell the browser to prefetch the content
    - some client side mvc templates don't render until dom is loaded
  - modern.ie can identify legacy IE fixes that will cause modern IE problems
  - webpagetest.org
    - allows you to mock "real" user connection
    - can identify blocking resources, ads, scripts, etc.
  - 'High Performance Browser Networking' Ilya Grigorik
  - Avoiding Forced Layout
    - look out for `:visible` or `:hidden`
    - minimize document-wide style/class changes
      - use `data-` atrs of `$.data()` if non-stylistic
    - get JS out of the path
      - use CSS tranistion/animations

## Edna Piranha
### Meatspace Chat
  - open api
    - can fork and host within own company
    - chat.meatspace.es
    - chatspac.es

## Ariya Hidayat
### Dynamic Code Analysis for JavaScript
  - http://ariya.ofilabs.com
  - slides: http://speakerdeck.com/ariya
  - http://esprima.org/
  - phantomjs
  - Istanbul https://github.com/gotwarlost/istanbul
  - Plato (https://github.com/es-analysis/plato)
    - http://ariya.ofilabs.com/2013/01/javascript-code-complexity-visualization.html (https://github.com/es-analysis/plato)
  - Utility Belt
  	  - dynamic analysis
  	  	- function instrumentation
  	  	- code coverage
  	  	- parser + code generator
  	  - syntax tree analysis
  	    - mozilla spidermonkey spec
  - Code Coverage
    - regenerative transformation
      - parses your code, runs your test and figures out how much is tested
    - statement & expression coverage
      - dig deeper into expressions to ensure all are tested
    - branch coverage
      - `if/else` & `while` have multiple branches
    - profile-guided optimization
      - test optimal profile of function
    - Istanbul, QUnit, Karma
  - function instrumentation
    - timing
      - prepare the stopwatch, mark the statrt/end
      - is it fast enough?
      - run-time complexity
    - sampling
      - periodically check which function is being ecevuted
    - tracing
      -track all cunftion calls and exits
    - 'the big rock'
      - target the big things first and move down
      - in CI env target whole `$` app and target how many functions are called, and how many times each is called
        - then move down
  - Test Madness
  	- TDD && BDD

## Brian Arnold
### Digging && Debugging
  - we are professional students
	  - learn about dev tools
	    - http://discover-devtools.codeschool.com/
	  - rubber duck
	- command line api
	  - `$0` variable is reference to last item inspected in console
	    - `$...` variables, `$1` becomes last `$0` once `$0` is reset
	    - `$_` last thing console evaluated to
	- detailed viewing
	  - use all the available `console` attributes
	    - `.group()` logs out tree
	    - `.time()` logs out time, set start/end
	    - `.warn()`
	- stop the presses
	  - `debugger;` statement for programmatic breakpoint
	  - `watch` expression in top right of dev tools
	    - allows you to enter and watch a specific expression
	  - put an expression on breakpoints to only break on specific condition
	- setting xhr breakpoints
	- `cmd + o` to open fuzzy finder
	- use private mode for debugging
	- settings (chrome)
	  - experiments (canary/chromium)
	  	- step in candidates
	  	  - add directories (i.e. `bower`) to not step into

## CORY GACKENHEIMER
### Unified Widget Theory: Building for Desktop and Mobile
  - JQ Mobile & JQ UI use the `$.widget` factory
    - allows author to write extensible widget
  - anatomy of widget
    - name
      - namespace
    - base
      - optional
      - 
    - prototype
      - methods for creating, initializing, destroying your widget

## Alex Sexton
### Hacking Front-End Apps
  - Content Injection
    - escaped HTML
    - `$.text()` excapes HTML while `$.html()` does not
    - Samy Kamker bug && evercookie
    - Billy Hoffman whitespace attack
  - CSS Hacks
    - privacy and the `:visited` selector
    - `.getComputedStyle()`
  - Timing Attacks
    - correct v incorrect passwords - hashing passwords
    - security by inaccuracy
    - `.requestAnimationFrame()` + `:visited` selector === modern timing attacks
      - time to render
  - JSON-P
    - use CORS
    - ...ajax `xhrFields: { withCredentials: true }`
    - enable-cors.com
  - CSRF for forms
  - Contextis White Paper
  - we need a fix
    - Content Securtiy Policy
  	  - by default dis-allows JS, CSS
  	- a white list
  - white listing is security by default

## Kirsten Jones
### Demistfying REST
  - HTTPScoop
    - trace http traffic
    - or use wireshark

## Greg Franko
### Building JavaScript Tools
  - Static Code Analysis tools
    - analyze code (performance || maintainability || etc., anything)
  - Plato
    - code complexity visualization tool
  - where to start to create your own static code analysis tools
    - it starts with a `var` and a string
      - `var foo = "function bar() {}";`
      - called an abstract syntax tree
        - an object that represents the structure of tyour code
        - does not store everything - it is abstract
  - common AST questions
    - how to generate an AST?
      - use a parser library or create your own parser
      - esprima - http://esprima.org/
        - js parser the generates ast
        - can be used in a node.js or web env
        - adheres to mdn spidermonkey parser
  - Estraverse
    - js library that provides AST traversal and update methods
    - can be used in node.js or web env
    - adheres to mdn spidermonkey
  - Escodegen
    - js library that will generate code from an ast
    - node.js && web environment
    - adheres to spidermonkey parsers api

## Rebecca Murphy
### Ain't no party like a third-party JS Party
  - BazaarVoice Firebird : product to put ratings/reviews on brand/retailer websites
  - using a scout file to load resources; relevant to all but mostly to third parties
  - 'Third Party Javascript' Ben Vinegar & Anton
  - code defensively -- even if you're first party

## SCOTT GONZÁLEZ
### jQuery UI: Behind the scenes
  - WAI-ARIA
    - hack for auto complete menu
      - `aria-relelvant=additions`
        - assertive regions
        - polite regions
  - jQUI works closely with standards bodies/browser vendors to create accessbile ui widgets
  - localization
    - Globalize (https://github.com/jquery/globalize)
      - now uses Unicode CLDR (http://cldr.unicode.org/)
  - `$npm install -g pretty-diff`
    - colorized diff tool for command line

## Scott Hanselman
### Javascript and the new VM
  - there are essentially five computers
    - amazon, google, rackspace, azure...
  - msopentech (http://vmdepot.msopentech.com/List/Index)
  - think about the many clients as virtual machine farm

## Monica Piotrowicz
### Accessibility (a11y) A feature you can build
  - WCAG 2.0 AA (accessibility standard)
  - assistive tools to consider
    - screen readers
    - bumped font size
    - braile readers
  - accessibility != checklist
  - color checker
    - test for color blindness
  - ARIA widget roles
    - tooltip
    - slider
    - tab
      - `tablist` : `tabpanel`
    - .etc
  - ARIA `aria-label`
    - correlates a wraper to an element
  - single page application
    - ARIA roles can "force" screen reader to pick up new page

## Jason Strimpel
### Unit Testing a client-server AMD code base
  - challenge 1 - choose your tools
    - grunt-castle
      - handles requirements; write a config and it handles

## Lon Ingram
### Functional Reactive Programming w/ jQuery, Flight & Bacon.js
  - what is functional reactive programming?
    - functional programming
      - avoid state, mutation side affects
      - single input, single out ; always
    - reative programming
      - oriented around data flows and propagation of change
      - commone example: spreadsheets
        - flow of data with a formula (cell c is equal to the sum of cells a-b)

## Timmy Wilson
### JQ: Now Ideal for Low Bandwidth
  - http://en.wikipedia.org/wiki/Jake_Weary
  - jankfree.org
  - custom build
    - remove -effects in lieu of css animations/transitions
    - remove ajax if it's not needed
  - `grunt-phantomjs` grunt plugin for phantomjs performance monitoring

## Jarrod Overson
### Real World Web Components
  - http://bit.ly/jqcon-webcomponents
  - HTML imports
    - `<link rel="import" href="source.html">`
    - import external HTML element, widget, etc.
  - Polymer
    - http://www.polymer-project.org/
    - satifying way to deal w/ cross platform web components
  - node webkit
    - native app wrapper for html/web components
    - https://github.com/rogerwang/node-webkit

## Danni Friedland
### NSA.js
  - github.com/bluehotdog/ruadan
  - scrolling
  - mouse movement
  - screen size
  - user selection
  - Mutation Observer (introdcued in DOM level 4)
    - dom changes
      - child/root observation
      - attribute changes
      - content changes
      - old/new data
  - limitations
    - assets (images, fonts) are hard to serialize
    - external css

## Vernon Kesner
### Using Node & Grunt to create and awesome workflow
  - focus on the tools you use to steal your time back
    - not a code monkey, get time back to work on oss
  - node/grunt/istanbul/phantomjs/jasmine
  - grunt
    - seperate out your grunt config files
    - `grunt load tasks`
    - require grunt modules
  - contextual jquery
    - http://vimeo.com/40873228
    - http://www.slideshare.net/dcneiner/contextual-jquery
  - two unique workflows
    - testing cycle, hot fixes, etc.
      - `grunt preview` task
        - reverse proxy environments
        - live data sources
        - ability to localize any asset or data response
        - selective compilation
        - source maps to aid in debugging
    - new & enhancement features
      - `grunt local` task
        - rapid development of components & layouts
        - living styleguide
    - both workflows use common components but the approach is distinctly different
  - selective builds

## Lenny Markus
### NodeJS in the enterprise
  - speed up the process
    - mock up applications with node
    - use a modern templating engine
      - dust.js (http://akdubya.github.io/dustjs/)
      - handlebars
      - underscore/lodash
  - Kraken (http://krakenjs.com/)
    - sits on top of expressjs, just with some added structure and syntactic sugar
    - out of the box security
    - scalable
    - `$ yo kraken` yeoman project template generation
  - security middleware === Lusca
    - clickjacking
    - CSRF
    - CSP
    - P3P headers
  - internationalization === Makara
    - seperation of templates and content
  - proxy for private NPM server === Kappa
    - want to keep your private modules private
    - want access to the public modules as well
    - blacklisting certain modules (concern around licensing, malicious)
      - licence checks in the proxy
  - best practices
    - get away from custom stuff, use standards
    - stop "not written here" syndrome
      - versions don't evolve
      - missing out on collective knowledge
    - Github exposes sacred code
  - hiccups
    - shared server understanding
    - SSL resumption
      - nginx can terminate SSL into your app
      - to make https calls you'l want this for performance
    - scaling and monitoring
      - use nodejs cluster; cluster2 or pm2 for mngmt
  - paypal is a nodejs shop






