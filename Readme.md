# Geometry Dash Web port
Created By Bog.
Geometry Dash compiled to the web. Do not play unless you actually own the game. Geometry dash is cheap.

## A (not) Detailed Explanation of what goes on internally, mostly for my own use.
### Index.html
- First, towards the top of the file, `sw.js` is registered as a service worker.
- The next script blah blah blah boomlings proxy.
  - It starts by disabling scramjet to avoid 404 errors. My best guess is to use scramjet's functions without it stepping out of turn looking for nonexistent functions.
  - Next, it clears out broken/stale proxies from localstorage. Most likely was used during development.
  - declares a bunch of functions to build and fetch gd proxy server stuff
  - you can tell I'm losing steam now.
  - One of these functions assembles the split gd_web.data files.
  - defines some functions for sending and receiving data
- The next script fetches and reassembles chunks.
  - somewhat self explanatory. Interesting how it works though. might add more later.
- Sends your data to Google analytics?
  - "[bog] is actively measuring metrics like visitor counts, page views, how long people stay on a page, and what links they click" (from gemini).
  - Ahhh, cheeky boyyy
  - pretty valid, was not aware of this though. Creates some privacy concerns.
- next script, a couple of event listeners:
  - "gd-focus": prevents scrolling
  - "gd-fullscreen": requests fullscreen
  - checks if clicking is happening on the canvas or somewhere else. this gets a little buggy sometimes.
- (273) a bunch of webpage stuff I wont explain yet
- (300)
  - Gets the console, tries to set the stack trace limit to 400.
  - Checks for url parameter 'debug' and if it's not true, it disables the console.
  - log dump?
  - Quiet?
  - Wierd window logging stuff
  - gd clear cashe
  - set assembler?
  - checking and forcing a finish of loaded assets
  - progress checking and resetting
  - forces loading to be done if the first frame of the game started rendering
  - gd progress tick? speed hack stuff?
  - (510) idk
  - restore saves
  - more later imma play deadlocked.
