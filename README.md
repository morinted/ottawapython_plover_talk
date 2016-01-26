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

Steno was probably one of the most proprietary technologies in the world, and it got that way because of its niche use and lower popularity, along with a few monopolizing companies in charge. All that changed, though, when a geek learned steno. Mirabai Knight graduated from a court reporting school in March 2007, and was fed up with the whole system. She had this technology that allowed her to express ideas effortlessly at uninmaginable speeds, but was unable to use it for most of her life, with software that was severly lacking in features. You can read through all the way back to 2008 where Mirabai had conceived and named what would be "Plover". She wanted an open source steno program to solve all the problems that the other software didn't.

But, she couldn't code. Whoops. So an apartment ad, a little chance, and a dash of fate later, Mirabai actually met an MIT graduate who was willing to teach her Python. Joshua Lifton started to teach Mirabai Python, but as he soon found out, Mirabai wasn't totally interested in learning to code, but rather just how to code a single program. So, they started to code Plover together, and given a little bit more time, Mirabai decided that coding wasn't really her thing, and Joshua started developing the application on his own.

Within a little bit of time, Plover was born. Plover was unique because it didn't require a steno machine, but rather just any NKRO keyboard. It was a very simple application and over many years, Plover grew.

# What is steno today?

Today, Plover is cross platform, working on Windows, OSX, and Linux. It allows you to send use modifiers, like control, Alt, and the Windows key. It works with many proprietary steno machines, which use serial communication. It supports two different dictionary formats, including the industry standard open format, which is a modification of Microsoft's RTF.

After Joshua Lifton was unable to work anymore on the program due to his need to focus on Crowd Supply, a crowd funding platform which boasts a high funding success rate. He also started working on the Stenosaurus, an open source steno machine that will be funded through Crowd Supply, sometime in 2016. After Josh left the project, Hesky Fisher, an engineer at Google, started to work on it. Hesky made a big push in adding steno machine support, improving the cross platform functionality, and much more in his time as lead developer. He started to distance away from the project as Josh did to pursue other projects.

# My stenography experience

I started learning stenography in August 2014, once I got NKRO working on my ErgoDox. Progress went well until I realized that my hardware was not at all ideal (mainly due to the heavy actuation force on my keyboard's keys), and school was very busy. Then, after getting a new, lighter-switched ErgoDox, I continued my learning. I hit 100 words per minute about a year in, and now I'm hovering around 130 words per minute, though in bursts I hit around 180 words per minute. I started developing Plover when I found myself with a little more free time and the need for certain features. Eventually I became Plover's lead developer, but I consider myself more as the lead maintainer.

# What is the good for?

## Accessibility

CART is used to help deaf or hard of hearing individuals -- Mirabai Knight captions lectures, conventions, or interactions for people.

## Programming

I am using steno to program now, full time in JavaScript, Java, and Python. It works great with Markdown. At the worst, it's about as fast as regular typing, at best you can do multiple symbols at once. Basically, because of the phonetic system, you never need to move off the "home row" for any symbol, really any word. So most symbols are as easy as writing a syllable or a word. It is not incredibly faster than normal typing, but it's definitely more ergonomic → and comments and documentation are trivially easy.

# How does it work?

Stenography works by shortening English to as short as possible so that you can express as much as you can with as few keys as possible. I like to think about it as "thinking with portals" → think-ing w portal-s → thig w porls

## Layout

The layout is split into 3 parts, `STKPWHR\*`, `AOEU`, and `\*FRPBLGTSDZ`. The left fingers handle the starting sound of the word, the thumbs handle the vowel sound, and the right hand handles the ending sound. Press all the keys at once to make a chord, and when the chord is released, the word appears on the screen. You can see some simple phonetic examples like cat or Ted: ST*K*PWHR*A*OEUFRPBLG*T*SDZ → "KAT" → "cat". S*T*KPWHRAO*E*UFRPBLGTS*D*Z → "TED" → "Ted". There are also chords for the missing letters on the beginning side, and many ending sounds. Here we see PH being selected, which translates to M: STK*P*W*H*RA*OE*UF*R*PBLGTSDZ which makes "MOER" → "mother"

There's no single way to write on steno, theories tend to be very personal and different people will find different theories easier than others. Some theories are light on memory, but require more strokes, such as Phoenix. These tend to be very phonetic based, as long as you can speak it, you can write it. Some are more memory heavy, like Mark Kislingbury's Magnum theory. Plover ships with a hybrid theory based off of StenED, a sort of middle of the line theory that is easy enough to learn but is still efficient.

## Code

Plover takes strokes as input, processes the strokes based on a dictionary and orthographic rules, then outputs emulated keyboard keys.

The input comes in the form of some sort of steno machine. You have the choice of a computer keyboard, particularly one with NKRO, or a steno machine. There are many custom steno machines made by the open source community, including the Stenoboard and the SOFT/HRUF. These can communicate in NKRO or in serial protocols.

When using the NKRO interface, we must suppress all keys that come in from the keyboard, so that the running program only receives the translation. For this, we catch all the keys necessary for steno (`1-0, QAWSEDRFCVTGYHBNUJIKOLP;`) and some others so that there are no accidental key presses. This creates a problem → if you are running an NKRO setup, you can't share your computer with other people. Also, a funny effect of the system is that on OSX, we can't suppress or detect keyboard input in OSX password fields, due to anti-keylogging measures. Thankfully, these issues are solved by using a serial input. Once you are using a serial protocol, you can still steno into a password field, and others are able to use the keyboard as normal, without any steno logic getting in the way. What this means is, effectively, when I'm using my steno machine in a computer, others can still use keyboards. This comes in useful, particularly when pair programming. That covers the input to Plover.

Next, the stroke gets processed through the user's dictionary configuration. There are quite a few rules that are involved with dictionaries, but the bulk of it ends up being:

- The dictionary is key-value system where the stroke is the key, and the translation is the output.
- There is no nesting, the dictionary is a flat object. Plover's is represented in JSON.
- Each an entry's key can be a sequence of strokes, as separated by slashes.
- The output is a string, which can contain literal characters, special Plover operators, or commands.
  - The string is literally just the string, most of the time this is what people want. If I want to define a stroke for "Ottawa Python" as a phrase, I write in the strokes and the output, e.g. `"OT/WA/PAO*EUT/*OPB": "Ottawa Python".`
  - You can also tell Plover exactly which keys to hit, including modifiers and special keys. If I want to do a simple control-c, I can define `{#Control_L(c)}`
  - Plover supports certain grammar and logic modifiers, in case you'd like a stroke to be a suffix or prefix, or if you'd like to make the next word capital, or the last word capital. These are just special characters inside curly braces. Like if I wanted to define a suffix like "awesomistically", I could do `"SPHEUFBG": "{^awesomistically}"`, then make any word like: cattawesomistically, Teddawesomistically, and Pythonnawesomistically. You can see that some letters got doubled there, that's thanks to Plover's built-in orthography rules.

The orthography rules are mainly a set of regex replaces to allow the suffix and prefix system to work well, and this makes it more powerful that many of the proprietary systems on the market.

Finally, the output stage. At this point, we use an operating system-specific implementation to simulate a keyboard pressing all the keys that Plover does. On OS X, this means using Quartz event APIs, on Linux we deal with XLib, and on Windows we use SendKeys. There are some difficulties when dealing with the three operating systems. Particularly, modifier keys sort of behave differently across the systems, as do keycodes. Making sure that our emulation is effective on all programs has been a great challenge. On Linux, we initially had trouble suppressing the input, so Plover would actually send backspaces to remove all the QWERTY keys that were hit. That's been fixed recently, but was a problem for over 5 years. On Windows, the Windows key wasn't implemented, and certain programs didn't accept Plover's input, such as pidgin and 10 fast fingers. This change isn't committed to master yet. On OSX, we always send key code 0 along with a Unicode string. This presents a problem for any legacy applications that don't handle the string, they just see a bunch of key presses to the "A" key. Furthermore, on OSX our command keys fall back to QWERTY key codes, so non-US layouts don't work for commands. For a while, Plover didn't properly support extended Unicode, and that has only recently been fixed on most systems. Linux is stuck to produce only what is defined in X lib, so it cannot do arbitrary keys yet. Windows and Mac had a problem where they wouldn't backspace emojis correctly, treating them as two characters when in reality they were just one. Now that's all fixed, but man, you learn more about Unicode than you ever wanted to know. Apparently all this Unicode stuff has been fixed in Plover 3, but we're still on Python 2.7 in Plover.

# Where is steno going?

So by now you might be wondering what the deal is. You know where steno has come from, you know how it works, you know what it can do. But, where is it going? Is court reporting a real job anymore?

Pretty valid questions, and definitely once that the Open Steno Project concerns itself with. The OpenStenoProject is Mirabai's umbrella organization over all that is open steno software, hardware, and learning materials. It contains Plover and some other projects, as well.

As for the future of stenography, it's in the hands of hackers like you and me now. Stenography has great speed, and many people care about that for different reasons. For people like me, it's probably a little more selfish, I want to type fast, I want to code, I want to avoid RSI from programming as a career, I want to be the best at TypeRacer, I want to do it as a hobby, I want to take notes quickly, I want to write documentation quicker, I want to avoid typos, I don't want to have to think about spelling, I want to do everything more quickly on my computer. I fit into this category, and I feel like a lot of you might. If you are curious about learning steno, don't be afraid to get involved in the online community, you can message the Google Group that we have, our Discord server, or even my personal inbox. I don't think there's such thing as a dumb question, and if you ask something that's been asked before we'll just point you in the right direction.

But there are more noble reasons for stenography to be pushed into the modern world. Yes, court reporting still exists, and it is actually the most reliable form of transcription. A human performs better today than any recording system. A human tends to be more reliable than microphones and computers for the purpose of recording depositions. Effectively, the text output that I stenographer makes is cheap to store, quick to search, and consistent in its quality. Voice recognition solutions often have issues with context or especially with handling multiple speakers in the court settings. I'm all for technology taking over realtime transcriptions, but it is really not there yet and probably won't be for a while.

But stenography has some other uses that might be beneficial for society. One of those is CART (communication access realtime translation) for accessibility purposes. Mirabai has acted as a CART provider for years, as she captions lectures and events for people who need it. Realtime transcription is necessary for individuals who are deaf or hard of hearing. In Canada, we have mandatory captioning of all television, including life events, meaning that there is always someone providing CART, and the providers are stenographers. In the modern age, we face a huge issue where most YouTube videos are posted without transcription, meaning the deaf cannot view a lot of content. YouTube has automatic transcription which is laughable at best. There are many free efforts to caption YouTube videos, but stenography could help alleviate this problem.

Anyone who cannot speak could also use stenography to communicate → if you cannot speak, learn steno and then use a text-to-speech program, and you write a conversional pace, much unlike the solutions that exist today.

There's a lot of use for stenography, just as there's a lot of use for typing. At the end of the day, stenography is a technology that I believe in. I think there's huge value in being able to communicate at high speeds with little effort, and I'm hopeful for what the enthusiast community will bring to the steno scene.

Lately there's been a lot of activity popping up on the Plover steno Google Group, with people trying to think of alternative layouts, alternative systems, some orthographic instead of phonetic, different layouts, different languages. There are so many ideas going around. I'm still sold on plain old stenography, as it has a century of history and vetting to back it up, and it's very exciting to see creative minds tackle issues and try to improve the problem that is typing.

As lead developer of Plover, I still have lots of problems that take up my free time when I'm not at school, work, or with family. There are some things that still bug me as I steno all my text and code.

These are some features that aren't yet in Plover:

- Currently, there's no way to hold down a modifier, and so you cannot do things like shift or control click, meaning often when I'm doing file management or using Photoshop, I'll find myself needing both my keyboard and my steno machine out.
- Plover has its layout hard coded, meaning that to change the steno layout or the number of keys, you need to modify the source code and rebuild Plover. This is a huge barrier to using stenography in other languages, and it's a high priority to making Plover useful internationally.
- We are using wxPython classic as a our UI, and this proves really difficult whenever we try to do user interface work that is non-trivial in Plover. It would be ideal to move over to someone like QT but that's a huge development effort.
- As mentioned previously, our code base is written for Python 2.7, and that's kind of a bummer because Python 3 is a much better language to work with.
- Plover doesn't look great, has a general lack of artwork and UX.
