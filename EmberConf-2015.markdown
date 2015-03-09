EmberConf 2015
==============

[Leah Silber](https://twitter.com/wifelette) and [Kait Olson](https://twitter.com/@tildekait) and the volunteers did an incredible job again this year of putting together this conference. Learn how Leah creates memorable conferences in her book: [Event Driven](https://leanpub.com/eventdriven/).

Summary
-------

The themes of the Ember community are productivity and friendliness. As mentioned by Chris Eppstein in the closing talk, those two goals may often be at odds, especially considering how the drive to compete is most often tightly bound with adversarial behavior. So far though, Ember developers demonstrate strong commitment to both advancing frontend web development as well as curating healthy community.

### Health
  * There were 625 attendees of the conference and it sold out quickly.
  *  Only 13 no-shows on the first day!
  * [Ember Community Survey results](http://201-created.com/ember-community-survey-2015)

### Themes
  * Design and user experience.
  * Performance.

### Companies
  * Good representation from large to small organizations.

### Projects targeting beta release on June 12, 2015
  1. Ember 2.0
  2. Ember Inspector 1.0
  3. Ember CLI 1.0
  4. Liquid Fire 1.0
  5. Ember Data 1.0

### Status of projects from EmberConf 2014
  1. [Ember-CLI](http://www.ember-cli.com) is now the default tool for Ember apps.
  2. [Broccoli](http://broccolijs.com) powers the fast builds of Ember CLI.
  3. [HTMLBars](https://github.com/tildeio/htmlbars) landed progressively starting in Ember 1.8.
  4. [Ember Data 1.0](http://emberjs.com/blog/2014/03/18/the-road-to-ember-data-1-0.html) has an official beta release date!

### Links to EmberConf 2015 resources:
* [EmberConf 2015 Summary](https://github.com/poteto/emberconf-2015) from [@sugarpirate_](https://twitter.com/@sugarpirate_)

Videos
------

[All the videos (Confreaks)](http://confreaks.tv/events/emberconf2015)

* [Keynote](https://www.youtube.com/watch?&v=o12-90Dm-Qs)

Talks
-----

  *  *  *  *
__Tuesday 2015-03-03__
  *  *  *  *

### Intro

Code of conduct: Don't exclude and make an effort to include.

### Opening Keynote

Yehuda Katz and Tom Dale | [@wycats](https://twitter.com/wycats) and [@tomdale](https://twitter.com/tomdale) | [Tilde](http://www.tilde.io) | [Slides](https://speakerdeck.com/wycats/emberconf-2015-keynote) | [Video](https://www.youtube.com/watch?&v=o12-90Dm-Qs)

*  625 attendees, more ember-cli users, more addons
*  [Built With Ember](http://builtwithember.io): square cash, heroku dashboard, ghost, beatport, intercom.io, consul, customer.io, nest store
*  lots of meetups
*  3 new core team members
  * [@mixonic](https://github.com/mixonic)
  * [@ef4](https://github.com/ef4)
  * [@mmun](https://github.com/mmun)
*  what's new? / report card
  * Rapid release worked great. Easier upgrade path for developers as a consequence.
  * [getrwjblueabeer.com](http://getrwjblueabeer.com)
  * New RFC process
  * Features landed:
    * HTMLBars landed in 1.10+
    * Ember Inspector ([@teddyzeenny](https://twitter.com/@teddyzeenny))
    * Ember CLI
    * Testing is way better
    * Query Params
    * JavaScript modules
  * Ember Data ([@terzicigor](https://twitter.com/@terzicigor))
  * ES6 Early Adopter
*  what's next?
  * Versioned guides
  * Ember CLI is the starting point for beginners
  * Engines
  * List View
  * `<angle-bracket>` Components
  * Liquid Fire animation library
  * Async & Routable Components
  * Ember 2.0 just removes support for deprecations
  * Ember Data
    * jsonapi.org
    * Pagination & Filtering
*  shipping it: _June 12_
*  Ember FastBoot
    * curl your ember app
    * Works with disabled JS
*  Performance
    * [@ryanflorence](https://twitter.com/@ryanflorence) video demonstrating poor performance for Ember
    * React insights
      * DOM is the bottleneck: JS is fast, DOM is slow
      * “Just Refresh It”
    * _Glimmer_
      * [Glimmer versus dbmonster](https://dbmonster.firebaseapp.com)
      * [Pull request on GitHub](https://github.com/emberjs/ember.js/pull/10501)
      * [Is Ember Fast Yet?](https://is-ember-fast-yet.firebaseapp.com)
      * Landing in 1.13

_“Your antidote to the hype fatigue”_

### Ember.js Performance

Stefan Penner | [@stefanpenner](https://twitter.com/@stefanpenner) | [Yahoo!](https://www.yahoo.com) | [Slides (_Coming soon…_)]() | [Video (_Coming soon…_)]()

* Promises performance improvements
  * Look inside the black box of browser performance
  * Bluebird library
    * Align with language primitives
* Idempotent rerender branch
* JS performance cargo-cult problem
  * Better question: When is X slow? When is X reasonable?
  * Shapes
* “Mechanical sympathy” from F1 driver
  * Look inside browser runtime implementations such as V8.
  * Code that is understandable and predictable (from both human and computer POV) is fast.
* Misalignments in Ember
  * Do less work
    * Explicit data-flow: Actions up, bindings down
    * Explicit life-cycle: RIP Singleton Controllers
  * init/super
    * Problems
      * Hard to learn
      * Misaligned with ES2015
    * Solution
      * Implicit defaults in init
      * Pass args
  * Ember.Object.reopen
    * Problems
      * Buggy
      * Complex
      * Meta is live inheriting
      * actionsFor from Meta.listeners
    * Solution
      * Working on a spike for this to reform Ember.Object.reopen

### Designing for Ember Apps

Steve Trevathan | [@strevat](https://twitter.com/@strevat) | [Dockyard](http://dockyard.com) | [Slides](https://speakerdeck.com/kidfribble/designing-for-single-page-applications) | [Video (_Coming soon…_)]()

* Designing single page apps.
* Users are difficult.
* Mental models.
  * Familiarity
  * Assumptions
  * Can be updated.
* What is “home”?
  * Valuing of thing is based on previous experience.
* Macro: What is it for?
* Micro: How does it work?
* Use patterns explicitly if they directly apply.
* Methods and patterns:
  1. Gradual engagement - Get started and recognize value with minimal effort
  1. Skeleton UI - Thinning out the spinners and replace with placeholder images, controls, and animation
  1. …don't leave me hanging - Handoffs. Contextually aware UI such as Rdio and Spotify knowing which device music is playing from.
  1. Core Interactions - Become a symbol of your app (product).
  1. Offline Mode - “Goliath Mode”. Respond optimistically, but be careful.
* Tools of the Trade
  * [Sign up for launch notification](http://toolsofthetrade.dockyard.com)

### Hijacking Hacker News with Ember.js

Godfrey Chan | [@chancancode](https://twitter.com/@chancancode) | [brewhouse](http://brewhouse.io) | [Slides](https://speakerdeck.com/chancancode/hijacking-hacker-news-with-ember-dot-js) | [Video (_Coming soon…_)]()

[Blog post: Adapter Patterns in Ember.js](http://brewhouse.io/blog/2015/03/06/adapter-patterns-in-ember-js.html)

* Canada!
* _Adapter pattern_
* [HN Reader](http://chancancode.github.io/hn-reader/about)
* Scraping from html document to JSON
* DS.Adapter to fetch data
* DS.Serializer to transform
* Preferences stored in local storage
* _Cocoa Bars!!!_ (kidding)

### The Art of Ember Deployment

Luke Melia | [@lukemelia](https://twitter.com/@lukemelia) | [Yapp](https://www.yapp.us) | [Slides](https://speakerdeck.com/lukemelia/the-art-of-ember-app-deployment)

“The future is already here, it's just not very evenly distributed.” -William Gibson

* Current server app deployment model is not appropriate for Ember apps.
* How to keep static assets working during the switchover?
  * Push all static assets to a CDN and keep them around.
  * Long lived sessions?
    * We have multiple versions of our Ember apps in use at once.
* Learn from native mobile apps.
* Key differences:
  * HTML pages bootstrap Ember apps
    * Points to fingerprinted assets, but is not itself fingerprinted.
    * …
* Use Redis (low latency store) to deploy index.html to app server.
  * Allows
    * Preview before activating.
    * Dynamic HTML rewriting between Redis and app server.
      * Feature flags
      * CSRF tokens
    * A/B testing
    * Notify clients of new version availability
* Which approach from the projects that currently do this?
  * ember-deploy, front-end-builds, ember-cli-deploy
  * Merge all 3! -> ember-cli-deploy
  * Great example of community desire to coalesce
* Timeline
  * 0.4.0 This week
  * 0.5.0 Soon
* [:addon ember-cli-deploy](https://github.com/ember-cli/ember-cli-deploy)

### Ambitious UX for Ambitious Apps

Lauren Tan | [@sugarpirate_](https://twitter.com/@sugarpirate_) | [Homely](http://www.homely.com.au) | [Slides](bit.ly/sugarpirate)

Self-taught designer, then self-taught developer.

* _“Design is how it works.”_ -Steve Jobs
  * Salt and pepper shakers. How many holes is the salt shaker?
* _Good Design is Reactive_
  * Reactive?
    * Flow of data
    * Maintaining relationships
  * FRP (Function Reactive Programming)
    * Immutability
    * Some side effects
    * Streams are an array of events (Unsure whether I noted this correctly)
    * Look at Bacon.js
  * Computed Property Macros
  * Observers
* _Good Design is Playful_
  * Loading messages
  * Shower thoughts reddit
* _Good Design is Informative_
  * System status visibility
  * [:addon ember-cli-flash](https://github.com/poteto/ember-cli-flash)
* _Good Design is Intuitive_
  * Drag and drop

### Bring Sanity to Frontend Infrastructure with Ember

Sam Selikoff | [@samselikoff](https://twitter.com/@samselikoff) | [TED](http://www.ted.com) | [Slides (_Coming soon…_)]() | [Video (_Coming soon…_)]()

* Issues scaling frontend from monolith at the start to multiple APIs and Interfaces.
* Ember and Ember CLI
* Process of discovery from manual to script to addon to service
* Identify redundancies and abstractions
  * Hard to do
  * Need a process
* This is the philosophy of Ember.

### Dynamic Graphic Composition in Ember

Chris Henn | [@cwhnn](https://twitter.com/@cwhnn) | [chrishenn.net](http://chrishenn.net/) | [Slides](https://speakerdeck.com/chnn/composing-data-visualizations-in-ember) | [Video (_Coming soon…_)]()

* [github.com/chnn/composing-graphics](https://github.com/chnn/composing-graphics)
* How should we split a statistical graphic into parts?
  * Separate features to change
  * Suggest they are possible to change
  * Encourage composability
* Scatterplot example
* [Leland Wilkinson's The Grammar of Graphics (1999)](http://www.cs.uic.edu/~wilkinson/TheGrammarOfGraphics/GOG.html)
* [Hadley Wickham's A Grammar of Graphics: Past, Present, and Future (2007)](http://ggplot2.org/resources/2007-past-present-future.pdf)
* [Hadley Wickham, Stat405: Grammar of Graphics (2012)](http://stat405.had.co.nz/lectures/21-grammar-of-graphics.pdf)
* What does this look like in Ember?

### Test-Driven Development by Example

Toran Billups | [@toranb](https://twitter.com/@toranb) | [toranbillups.com](http://toranbillups.com) | [Video (_Coming soon…_)]()

* Live coding like no one is watching.
* Building an app and writing tests.
* tmux + vim + testem all in one view is very nice.
* fauxjax for mocking JSON API
* Go back and watch this in slow motion.

_Mic drop: Apple Menu > Shut Down…_

  *  *  *  *
__Wednesday 2015-03-04__
  *  *  *  *

### Fault Tolerant UX

Dan Gebhardt | [@dgeb](https://twitter.com/@dgeb) | [Cerebris](http://www.cerebris.com) | [Slides](https://speakerdeck.com/dgeb/fault-tolerant-ux) | [Video (_Coming soon…_)]()

* Fault tolerance in naval ship design.
* To prevent operator defaults, controls must be laid out as clearly as possible.
* Transactional UX (ACID)
  * _Atomic_: All or nothing.
  * _Consistent_:
  * _Isolated_: Allow concurrent changes.
  * _Durable_: Changes persist.
* Forgiving UX
  * Transitional Persistence: Preserve data that user has entered but not saved.
  * Undo and redo.
  * Offline support (Non-blocking): Even when network connection is down.
  * Asynchronous (Non-blocking) Interface: Don't need to wait for server response.
* Event subscriber pattern
* _Orbit.js_
  * Request
  * Transform
* Sources
  * Memory
  * Local storage
  * JSON API
  * …more
* ember-orbit
* [github.com/orbitjs](https://github.com/orbitjs)
* [orbitjs.com](http://orbitjs.com): Coming soon…

### Aligning Ember with Web Standards

Matthew Beale | [@mixonic](https://twitter.com/@mixonic) | [201 Created](http://www.201-created.com) | [Slides](http://www.slideshare.net/mixonic/aligning-emberjs-with-web-standards) | [Video (_Coming soon…_)]()

[Blog post: Aligning Ember.js with Web Standards](http://madhatted.com/2015/3/6/aligning-ember-js-with-web-standards-emberconf-2015)

1. JS standardization process is changing -> “Living Standard” like HTML -> ES2015
Standards
  * Portable
  * Best practices
  * Enduring
  * Participants win
2. Transpilers are here to stay
  * Remy Sharp coined “Polyfill”
  * For stuff that can't be polyfilled, must transpile.
  * Babel (Previously 6to5)
3. Aligning Ember's object model
* ES Classes
  * `class`
  * `extend`
  * `super`
* ES Decorators proposal
* [_Ember Community Survey 2015_](http://www.201-created.com/ember-community-survey-2015)

### Growing Ember One Tomster at a Time

Jamie White | [@jgwhite](https://twitter.com/@jgwhite) | [With Associates](http://2015.withassociates.com) | [Slides](https://speakerdeck.com/jgwhite/growing-ember-one-tomster-at-a-time) | [Video (_Coming soon…_)]()

* Community is vibrant. How did that come about?
* Reflections on EmberConf 2014
* Community does not automatically follow design engineering.
* Tomster represents productivity and friendliness.
* Compare Ember release cycle pages to Chrome release cycle pages.
* “Ambitious” and “Friendly” are hard to combine.
* Lindsey Wilson: Tomster is adaptable. Wasn't overly done.
* Use language to coalesce concepts and philosophy.
* For docs: “If something is difficult to explain it probably means we're exposing the wrong primitives.” -[Trek](https://twitter.com/@trek)

### Interaction Design with Ember 2.0 and Polymer

Bryan Langslet | [@blangslet](https://twitter.com/@blangslet) | [Envoy](http://signwithenvoy.com) | [Slides (_Coming soon…_)]() | [Video (_Coming soon…_)]()

[Demo video](https://www.youtube.com/watch?v=lXWVmbs5O8A)

* Ember + Polymer + Material Design
* Ember-Flow
* Web Components
  * Extend the browser itself
  * Encapsulation
  * Declarative
  * True reusability/portability
* Web Animations API
* Core Animated Pages
* Demonstration:
  * [github.com/blangslet/treasure-hunt](https://github.com/blangslet/treasure-hunt)
  * [github.com/blangslet/ember.js-mobile-animations-gestures](https://github.com/blangslet/ember.js-mobile-animations-gestures)
* Dream Stack

### Building Custom Apps with Ember CLI

Brittany Storoz | [@brittanystoroz](https://twitter.com/@brittanystoroz) | [Mozilla](https://www.mozilla.org) | [Slides](http://brittanystoroz.github.io/presentations/embercli-fxos/#/) | [Video (_Coming soon…_)]()

* Firefox OS build tool
* Rec Room -> Ember CLI
* Use addons for Firefox OS development requirements.
  * Blueprints to generate the manifest.
  * Addon to install “Gaia” UI components. Lots of steps but all covered in Ember CLI docs.
  * Adding commands for validation and publishing.
    * `availableOptions` to set flags
* [github.com/mozilla/ember-cli-fxos](https://github.com/mozilla/ember-cli-fxos)

### Building Real-Time Applications with Ember

Steve Kinney | [@stevekinney](https://twitter.com/@stevekinney) | [Turing School](http://turing.io) | [Slides](http://www.slideshare.net/stevekinney/building-realtime-applications-in-emberjs) | [Video (_Coming soon…_)]()

*  Real-time applications
*  A story about WebSockets…
*  Fallback libraries: socket.io and Faye
*  Approaches
  1. In a controller
  2. In a service
  3. Socket.io
* [github.com/stevekinney/emberconf-chat](https://github.com/stevekinney/emberconf-chat)
* [github.com/stevekinney/emberconf-twitter-stream](https://github.com/stevekinney/emberconf-twitter-stream)

### Minitalks

Leah Silber | [@wifelette](https://twitter.com/@wifelette) | [Tilde](http://www.tilde.io) | [Video (_Coming soon…_)]()

#### Bill Heaton, [@pixelhandler](https://twitter.com/@pixelhandler)
* [Measure Performance with the User Timing API](http://pixelhandler.com/posts/measuring-performance-with-user-timing-api-in-an-ember-application)
* Start measuring now and analyzing as you gain a better understanding of the appropriate statistical approach.

#### Mitch Lloyd, [@too_mitch](https://twitter.com/@too_mitch)
* Bring Ember to Your Server Rendered Application
* [:addon ember-islands](https://github.com/mitchlloyd/ember-islands)

#### Liz Baillie, [@infinite_math](https://twitter.com/@infinite_math)
* Flatiron School
* Ember Testing with Chemistry Dog
* Jumped in with the goal of becoming the Ember testing expert

#### Michael Nutt, [@michaeln3](https://twitter.com/michaeln3)
* [Crossfilter](http://square.github.io/crossfilter/) project by, Mike Bostock, the creator of D3.js
* C++ -> Emscripten -> asm.js -> Require in ES6 module
* [:addon ember-cli-emscripten](https://github.com/movableink/ember-cli-emscripten)

#### Katie Gengler, [@katiegengler](https://twitter.com/katiegengler)
* [Ember Observer](http://emberobserver.com) for rating and reviewing addons
* [github.com/emberobserver](https://github.com/emberobserver/client)

#### Erik Bryn, [@ebryn](https://twitter.com/@ebryn)
* CSS is hard.
* Automatically namespace it.
* [:addon ember-component-css](https://github.com/ebryn/ember-component-css)

### Physical Design

Edward Faulkner | [@eaf4](https://twitter.com/@eaf4) | [braveleaf](https://braveleaf.com) | [Slides (Coming soon…]() | [Video (_Coming soon…_)]()

* [:addon liquid-fire](https://github.com/ef4/liquid-fire)
* [Demonstration](https://github.com/ef4/physical-design-demo)
  * Grab the EmberConf website with wget
  * Turn it into an Ember app
  * Define the start and end states
  * Start adding animations
  * As long as the elements remain, the page can be refactored
  * Switch from Velocity to Web Animations API!
* [miguelcobain.github.io/ember-paper](miguelcobain.github.io/ember-paper) (Opportunity to contribute!)

### Closing Keynote: Coming Soon!

Chris Eppstein | [@chriseppstein](https://twitter.com/@chriseppstein) | [LinkedIn](https://www.linkedin.com) | [Slides](http://www.slideshare.net/chriseppstein/ember-closing-keynote) | [Video (_Coming soon…_)]()

* Announcing: [Sass Eyeglass](https://github.com/sass-eyeglass/eyeglass)
* Eyeglass is the JS equivalent of Compass
* Libsass is a C++ implementation of the sass compiler
* “Autoprefixer is awesome. Use that.”
* “Come for the technology. Stay for the <3 <3 <3.”
* Pulp Fiction, Marsellus Wallace: Fuck pride.
* Fight Club, Tyler Durden: You are not your OSS contributions.
* How to compete without negativity?
* What does it mean to “win”? Why does it matter?
* Find a job you love and you'll never work a day in your life.
* Do what you do because you love it.

## Miscellanea

Special thanks to [Emanuele Tozzato](https://twitter.com/@mekdigital) for showing a few of us around Portland while we discussed Ember.
