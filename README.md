# Plover Talk

### For the Ottawa Python Authors meetup group

#### Presentation date: Thursday, January 28th, 2016. 7:30 p.m. EST for 30-45 minutes.

### Summary Blurb

Ottawa Python: How to Write Over 200 Words Per Minute.—Ted Morin

*This talk will be live-captioned for the deaf or hard-of-hearing.* Plover is free software written in Python that enables you to type on a computer at over 200 words per minute. Plover brings machine stenography, an art older than computers, into everyone's hands.

Plover's current lead developer, Ted Morin, will talk about why Plover was created, how it works, and explain the role stenography might have in the modern world, as it moves beyond transcription and into the hands of hackers.

### Topics

## Introduction

Today I'd like to talk about a technology that consumes much of my life now, even though I've only known about it for a year and a half. This technology is stenography, a shorthand system that allows people to type at over 225 words per minute, on par with human speech. I'm talking about it here right now because the software I use is written in Python. I'm going to talk to you about a few things tonight: what stenography was, what changed it into what it is today, and where it might be going, and the role that Python has played in making it all possible.

## What is Stenography, in the first place?

Stenography is a system of writing that aims to decrease the length required to express language. You may have heard of written shorthand systems like Gregg and Pitman, which is used by journalists to take written notes quickly. The stenography that I'm talking about, machine stenography, is based off the same theory as written shorthand. Basically, it's a system that optimizes for English, mainly phonetically, in order to increase output speed of transcription. With machine stenography in particular, the stenograph allows you to chord keys, meaning you  The means that instead of writing out the letters of a word, say "nauseous", you produce the sound. Stenography might allow you to stroke the word as "N-AW-SHS" or "NAW/SHOUS". The word "particular" is 12 letters, but can be stroked in stenography with 6 keys, all hit at once, "PLARL".

## How fast is it actually?

Here are some average speeds in terms of words per minute.

Handwriting 25WPM < Hunt and Pecker 40WPM < Touch typist 80WPM < Casual Speech 160WPM < Practical Speech Recognition 180WPM < Stenography 225WPM

These of course are averages, the top typist in the world, Sean Wrona, types at 170 words per minute on average with a QWERTY keyboard. The top stenographer in the world, Mark Kislingbury, writes at 360 words per minute on average.

225WPM is not a speed limit with stenography, but rather a good baseline, as it is the required speed for an individual to be certified for court reporting the United States. Some students stop around 180 words per minute mark and do non-realtime jobs that aren't as dependent on speed. Many people surpass this 225 minimum, like the captioner who is writing for us today, Mirabai Knight, who writes at an average of 260WPM. The stenography speed world record holder, Mark Kislingbury, writes at 360WPM.

So this is to say that for most people, stenography can increase your writing speed from 2 to 4 times its current speed, faster than human speech.

## What *was* steno?

Let's talk a little bit about the history of machine stenography. To use stenography, you need 3 things:

- Hardware to input the shorthand
- Software to handle the input from the hardware and convert it into plain English
- Education in order to learn the system and get faster

Just under a decade ago, all three of these things were only available in proprietary form. It cost, in US dollars, about one to four thousand dollars for the hardware, a thousand dollars yearly subscription for the software, and thousands for a college education, which can take 1 to 7 years.

The proprietary software solutions were created for the purpose of transcription, and as such the software ended up being a walled-garden sandbox where you can write into a document, like an enhanced Microsoft Word. That means that you are limited to only using steno to collect text.

- History of steno

  + OSP & Knight, Lifton, and Fisher saving the day / changing my life as a programmer and typing enthusiast
    - Mirabai graduated from school, became a CART, wanted to make steno free. Met Lifton who lived in the same building, looking for Python tutoring. Turned into development sessions for what would become Plover. Lifton became the lead developer, and brought Plover to life. Lifton stepped down to work on CrowdSupply, Hesky Fisher got into it because he was in a relationship with a stenographer-in-training. He's mainly stepped down and into developer emeritus.
    - I started learning in August 2014, once I got NKRO working on my ErgoDox. Progress went well until I realized that my hardware was not very ideal, plus school was very busy. Then, after getting a new, lighter-switched ErgoDox, I continued my learning. I hit 100 words per minute about a year in, and now I'm hovering around 130 words per minute, though in bursts I hit speeds averaging 180 words per minute. I started developing Plover when I found myself with a little more free time.
  + Stenography has existed as shorthand for thousands of years. You may have heard of journalists using Pittman, Teeline, or Gregg shorthand. These were written using phonetic based shortcuts instead of spelling. Machine shorthand, created with a Stenotype, is a similar system, but uses keys to form the phonetic representation instead of lines.
  + The first stenotypes were conceived of in the 1800s, with a patent in 1879. These stenotypes would punch letters into a paper strip, each line representing a phonetic, a word, or a phrase.
- Speed (TypeRacer)
  + QWERTY typists average about 40 words per minute, but naturally fast typists will usually hover around 80 words per minute to 120 words per minute. The truly exceptional, such as Sean Wrona, writes with an average speed of about 170 words per minute.
  + Court reporters must reach an average of 225 words per minute in order to get certified.
  + The creator of
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
  + wxPython has been difficult
- Caveats: emoji, keyboard suppression
  + Emoji's often have the same "start" and it made the functionality of emoji hard. Basically, say you are writing "New York". In steno that's "new" then "york". Two strokes. As you output, "new" will be written, then when you input "york", it will backspace back the "new" and output "New York". Plover tries to identify the common beginnings of the output to save on keystrokes. With emoji, it would identify a common beginning, even though that's simply because emoji tend to be longer than a byte. It would then attempt to output half an emoji (as in the case of moej kat 2). The fix was to properly handle emoji.

#### Unsolved problems/call for help

- Conceptual solution to holding down modifiers
  + Shift/Control-click.
- GitHub issues:
  + Customizable key layout; make it easier to port to new languages, layouts.
  + New UI framework; wxPython has issues.
  + Conversion to Python 3
  + Open to new coders and learners. Artwork also welcome.
