# Plover Talk

### For the Ottawa Python Authors meetup group

#### Presentation date: Thursday, January 28th, 2016. 7:30 p.m. EST for 30-45 minutes.

## TODO:

- Decide on format
- Consider live components/audience participation

### Summary Blurb

Summary is required to tell people what the presentation will be about on the website. Need to know if Mirabai is available in order to tell whether or not we will have captioning.

Ottawa Python: How to Write Over 200 Words Per Minute.—Ted Morin

*This talk will be live-captioned for the deaf or hard-of-hearing.* Plover is free software written in Python that enables you to type on a computer at over 200 words per minute. Plover brings machine stenography, an art older than computers, into everyone's hands.

Plover's current lead developer, Ted Morin, will talk about why Plover was created, how it works, and explain the role stenography might have in the modern world, as it moves beyond transcription and into the hands of hackers.

### Topics

Just writing some ideas down on what I *could* talk about. This crowd tends to lean a little more technical, but often the topics described aren't as foreign as stenography. I figure that the crowd will probably want to know how the system works technically, but will especially be curious about the typing speeds and the benefits to them.

#### Non-technical

- History of steno; the usual spiel
  + OSP & Knight, Lifton, and Fisher saving the day / changing my life as a programmer and typing enthusiast
    - Mirabai graduated from school, became a CART, wanted to make steno free. Met Lifton who lived in the same building, looking for Python tutoring. Turned into development sessions for what would become Plover. Lifton became the lead developer, and brought Plover to life. Lifton stepped down to work on CrowdSupply, Hesky Fisher got into it because he was in a relationship with a stenographer-in-training. He's mainly stepped down and into developer emeritus.
    - I started learning in August 2014, once I got NKRO working on my ErgoDox. Progress went well until I realized that my hardware was not very ideal, plus school was very busy. Then, after getting a new, lighter-switched ErgoDox, I continued my learning. I hit 100 words per minute about a year in, and now I'm hovering around 130 words per minute, though in bursts I hit speeds averaging 180 words per minute. I started developing Plover when I found myself with a little more free time.
  + Stenography has existed as shorthand for thousands of years. You may have heard of journalists using Pittman, Teeline, or Gregg shorthand. These were written using phonetic based shortcuts instead of spelling. Machine shorthand, created with a Stenotype, is a similar system, but uses keys to form the phonetic representation instead of lines.
  + The first stenotypes were conceived of in the 1800s, with a patent in 1879. These stenotypes would punch letters into a paper strip, each line representing a phonetic, a word, or a phrase.
- Speed (TypeRacer)
  + QWERTY typists average about 40 words per minute, but naturally fast typists will usually hover around 80 words per minute to 120 words per minute. The truly exceptional, such as Sean Wrona, writes with an average speed of about 170 words per minutes.
  + Court reporters must reach an average of 225 words per minute in order to get certified.
  + The current world-record-holding stenographer, Mark Kislingbury writes at about 360 words per minute.
- Accessibility
  + CART is used to help deaf or hard of hearing individuals -- Mirabai Knight captions lectures, conventions, or interactions for people.
- Programming
  + I am using steno to program now, full time in JavaScript, Java, and Python. It works great with Markdown. At the worst, it's about as fast as regular typing, at best you can do multiple symbols at once. Basically, because of the phonetic system, you never need to move off the "home row" for any symbol, really any word. So most symbols are as easy as writing a syllable or a word. It is not incredibly faster than normal typing, but it's definitely more ergonomic --> and comments and documentation are trivially easy.
- Layout
  + STKPWHRAOEUFRPBLGTSDZ. Press all the keys at once and the word appears. There are chords that combine to make the missing letters. In that list, for example ST*K*PWHR*A*OEUFRPBLG*T*SDZ --> "KAT" --> "cat". Or in the case of STK*P*W*H*RA*OE*UF*R*PBLGTSDZ which makes "MOER" --> "mother"
- Basic theory/demo
  + Some theories are light on memory, but require more strokes --> more phonetic-based. Syllable by syllable. (Phoenix). Some are more memory heavy, like the aforementioned Mark Kislingbury's Magnum theory. Plover ships with a hybrid theory that aims to fill the best of both theories.
- My history
  + Often people argue against steno, citing the failure of Dvorak or Colemak. The systems really aren't comparable, and I'd like to try to emphasize that by explaining that I've learned Dvorak, Colemak, Workman, and (still use) Norman. Steno is just a completely different beast. Slow starts, hardware feels like a barrier, theory takes thought from new angles on English --> THIG W PORLS (thinking with portals)

#### Pythonic!!

- High-level diagram of the system:
  + Machine --> Interpreter --> Orthography rules --> OS Layer
  + Machine is NKRO --> suppression, detection
  + Machine is serial --> no suppression, think pair programming
- Technologies: wxPython, pySerial, hid interfaces
- Caveats: emoji, keyboard suppression

#### Unsolved problems/call for help

- Conceptual solution to holding down modifiers
- GitHub issues:
  + Customizable key layout; make it easier to port to new languages, layouts.
  + New UI framework; wxPython has issues.
  + Conversion to Python 3
  + Open to new coders and learners. Artwork also welcome.
