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
  - 

