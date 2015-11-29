# Plover Talk

### For the Ottawa Python Authors meetup group

#### Presentation date: Thursday, January 28th, 2016. 7:30 p.m. EST for 30-45 minutes.

## TODO:

- Everything
- Write summary blurb
- Enumerate possible topics
- Decide on format
- Consider live components/audience participation

### Summary Blurb

Summary is required to tell people what the presentation will be about on the website. Need to know if Mirabai is available in order to tell whether or not we will have captioning.

Ottawa Python: Typing over 225 words per minute.—Ted Morin

*This event will talk will be live captioned for the deaf or hard of hearing.* Plover is free software that enables you to type on a computer at over 200 words per minute. Plover brings machine stenography, an art older than computers, into everyone's hands.

Plover's current lead developer, Ted Morin, will talk about why Plover was created, how it works, and explain the role stenography might have in the modern world.

### Topics

Just writing some ideas down on what I *could* talk about. This crowd tends to lean a little more technical, but often the topics described aren't as foreign as stenography. I figure that the crowd will probably want to know how the system works technically, but will especially be curious about the typing speeds and the benefits to them.

#### Non-technical

- History of steno; the usual spiel
  + OSP & Knight, Lifton, and Fisher saving the day / changing my life as a programmer and typing enthusiast
  + Stenography has existed as shorthand for thousands of years. You may have heard of journalists using Pittman, Teeline, or Gregg shorthand. These were written using phonetic based shortcuts instead of spelling. Machine shorthand, created with a Stenotype, is a similar system, but uses keys to form the phonetic representation instead of lines.
  + The first stenotypes were conceived of in the 1800s, with a patent in 1879. These stenotypes would punch letters into a paper strip, each line representing a phonetic, a word, or a phrase.
- Speed (TypeRacer)
  + QWERTY typists average about 40 words per minute, but naturally fast typists will usually hover around 80 words per minute to 120 words per minute. The truly exceptional, such as Sean Wrona, writes with an average speed of about 170 words per minutes.
  + Court reporters must reach an average of 225 words per minute in order to get certified.
  + The world record stenographer, Mark Kislingbury writes at about 360 words per minute.
- Accessibility
- Programming
- Layout
- Basic theory/demo
- My history
  + Often people rebute steno, citing the failure of Dvorak or Colemak. The systems really aren't comparable, and I'd like to try to emphasize that by explaining that I've learned Dvorak, Colemak, Workman, and (still use) Norman. Steno is just a completely different beast.

#### Pythonic!!

- High-level diagram of the system:
  + Machine --> Interpreter --> Orthography rules --> OS Layer
- Technologies: wxPython, pySerial, hid interfaces
- Caveats: emoji, keyboard suppression

#### Unsolved problems/call for help

- Conceptual solution to holding down modifiers
- GitHub issues: customizable key layout, new UI framework, conversion to Python 3, open to new coders for simple things like documentation.
