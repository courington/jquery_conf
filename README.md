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



