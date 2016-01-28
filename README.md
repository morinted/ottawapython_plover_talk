# Plover Talk

### For the Ottawa Python Authors meetup group

#### Presentation date: Thursday, January 28th, 2016. 7:30 p.m. EST for 30-45 minutes.

### Summary Blurb

Ottawa Python: How to Write Over 200 Words Per Minute.—Ted Morin

*This talk will be live-captioned for the deaf or hard-of-hearing.* Plover is free software written in Python that enables you to type on a computer at over 200 words per minute. Plover brings machine stenography, an art older than computers, into everyone's hands.

Plover's current lead developer, Ted Morin, will talk about why Plover was created, how it works, and explain the role stenography might have in the modern world, as it moves beyond transcription and into the hands of hackers.

### Topics

## Introduction

The up there is a steno machine. It's a special keyboard-kinda thing that plays a little bit more like a piano. You hit a bunch of keys at once to form a chord, and out comes full words, sentences, symbols, whatever.

I've only known about stenography for about a year and a half, but it has greatly impacted my life. Stenography that allows people to write on a computer at over 225 words per minute, on par with human speech. I'm here right now because Plover, the free steno software, is written in Python.

---

## Who, you?

I should introduce myself. My name is Ted Morin, I'm a fourth year software engineering student at the University of Ottawa → meaning I've been taught Java. I split my time between school and working for a start up in the Wellington West area, Clearwater Clinical. Clearwater makes high-tech solutions to expensive and outdated technology in the medical field. There I use JavaScript, consisting of mainly React and Redux, to build web portals for their software products.

I'm a big fan of JavaScript, but don't tell anyone because they tend to yell at me for loving such a...special language.

I've used Python for what I'd consider a while, way before JavaScript because things like Node didn't exist at the time. It was my first scripting language, first language I was using through a command-line. I used it a lot at home whenever I had to work through a math problem or build a quick web scraper, its simplicity lets you focus on the problem at hand instead of classes and semicolons. It's really quite a novel language, and I didn't appreciate it fully until I started noticing the differences between it and Java or JavaScript. I think my favorite Python feature is optional named parameters. I think that should be in every language, it's just too convenient.

So I'm a software developer, and I use stenography to write all my code.

---

## Table of contents

Here's what I'm going to talk about today, written by a very confused individual:

- Plover, duh, that's the title, Ted.
  - ELI5 steno plz
  - Speed, what, where‽
  - How the heck did steno happen?
  - Hello, Python talk? 😕
  - Whoa, teach me mister Ted
  - Noice tauk m8, qu'est-ce que c'est, la future de sténographie?

I'm going to talk to you about Plover, open source stenography software written in Python. To do that, I need to define what stenography is, and part of that is discussing why it's so fast. We'll go over how Plover came to be, talk a little bit about the Python code behind it, and just a tad of the theory and physical layout. After, I'll close with some thoughts about where I think steno will be in the future.

---

## What is Stenography, in the first place?

Stenography is a system of writing that aims to decrease the length required to express language. You may have heard of written shorthand systems like Gregg and Pitman, which are used by journalists to take written notes quickly. The stenography that I'm talking about, machine stenography, is based off the same theory as written shorthand. Basically, it's a system that optimizes for English, mainly phonetically, in order to increase output speed of transcription. With machine stenography in particular, the stenograph allows you to chord keys, that means that instead of writing out the letters of a word you produce the sound. This means that you don't really have to think about spelling anomalies. You can write "nauseous" and "cautious" and "conscious" by sound alone, effectively "naw", "caw", and "con" followed by "shs". Through other rules, we can phonetically shorten a word. Like "particular", we can sort of drop most of the word and sound out "p-lar", and by extension "particularly", which is 12 letters, it can be written in one stroke, which is given by the phonetic input "p-lar-l".

Stenography is much faster than regular typing.

---

## How fast is it actually?

Here are some average speeds in terms of words per minute.

Handwriting 25WPM < Hunt and Pecker 40WPM < Touch typist 80WPM < Casual Speech 160WPM < Practical Speech Recognition 180WPM < Stenography 225WPM

These of course are averages, the top typist in the world, Sean Wrona, types at 170 words per minute on average with a QWERTY keyboard. The top stenographer in the world, Mark Kislingbury, writes at 360 words per minute on average.

225WPM is not a speed limit with stenography, but rather a good baseline, as it is the required speed for an individual to be certified for court reporting the United States. Some students stop around 180 words per minute mark and do non-realtime jobs that aren't as dependent on speed. Many people surpass this 225 minimum, like the captioner who is writing for us today, Mirabai Knight, who writes at an average of 260WPM. The stenography speed world record holder, Mark Kislingbury, writes at 360WPM.

So this is to say that for most people, stenography can increase your writing speed from 2 to 4 times its current speed, faster than human speech.

---

## What *was* steno?

Let's talk a little bit about learning machine stenography about a decade ago. To do steno, you need 3 things:

- Hardware to input the shorthand
- Software to handle the input from the hardware and convert it into plain English
- Education in order to learn the system and get faster

Just under a decade ago, all three of these things were only available in proprietary form. It cost, in US dollars, about one to four thousand dollars for the hardware, a thousand dollars yearly subscription for the software, and thousands for a college education, which can take 1 to 7 years.

The proprietary software solutions were created for the purposes of creating printed official court transcripts, and as such the software ended up being a walled-garden sandbox where you can only write into a document, like an enhanced Microsoft Word. That means that you are limited to only using steno to collect text.

Steno was probably one of the most proprietary technologies in the world, and it got that way because of its niche use and lower popularity,  leading it to be a market with very few companies in charge. All that changed, though, when a geek learned steno.

---

Mirabai Knight is, as I mentioned, a geek. Here, I've collected some pictures as proof. She's captioning this talk today. She graduated from a court reporting school in March 2007, and was fed up with the whole system. She had this technology that allowed her to express ideas effortlessly at previously unattainable speeds, but was unable to use it for most of her everyday life, with software that was severely lacking in features. You can read through all the way back to 2008 where Mirabai had conceived and named what would be "Plover". She wanted an open source steno program to solve all the problems that the other software didn't.

But, she couldn't code. Whoops. So an elevator ad, a little chance, and a dash of fate later, Mirabai actually met a freelance software engineer with a PhD from theMIT media lab who was willing to teach her Python.

---

Joshua Lifton started to teach Mirabai Python, but as he soon found out, Mirabai wasn't totally interested in learning to code, but rather just how to code a single program. So, they started to code Plover together, and given a little bit more time, Mirabai decided that coding wasn't really her thing, and Joshua started developing the application on his own.

And so, Plover was born!

---

Oh wait, that's not software, those are Plover birds. Where did Dolores go...

---

Plover was unique because it didn't require a steno machine, but rather just any NKRO keyboard. It was a very simple application and over many years, Plover grew.

After a few years of development, Joshua Lifton was unable to work anymore on Plover due to his need to focus on Crowd Supply, a crowd funding platform based out or Portland which boasts a high funding success rate. Before he was done with programming Plover, though, he committed to design and release an open hardware partner to Plover: the Stenosaurus.

---

The Stenosaurus is still in the works, but it has a blog where you can follow along on its development. It is a beautiful piece of hardware but will be hundreds of dollars instead of thousands like the steno machines currently on the market.

So, without a developer, is Plover doomed? Well, no. After Josh left, another developer found himself interested in steno.

---

Hesky Fisher, who works as an engineer at Google, took over. Hesky made a big push in adding steno machine protocol support, vastly improving the cross platform functionality, and much more in his time as lead developer. He was super productive and still hangs around as a wiseman among the open steno community.

Once people started to notice Hesky's absence, there was a clear need for a new developer. I'm no MIT graduate, heck I'm not even a uOttawa graduate yet, but just this past summer I found myself taking on the torch of Plover's lead dev.

Now, Plover is at a pretty great place that fills in a huge gap that existed just 6 years ago:

Plover is cross platform, working on Linux, Windows, and OSX. It allows you to use modifiers, like control, Alt, and the Windows key. It works with many steno machine protocols, which run over serial. The best part is: it's free, and that means people can modify it and improve it and all the users benefit.

Software is free, hardware is being freed. The last big block in you learning steno is well... learning it.

---

## Learning

That's where Zack Brown comes in. He is a technical writer who has worked at Google and with the Linux Foundation. He took interest in learning steno and reached out to Mirabai. In exchange for lessons on stenography, he was to document them and write a free textbook for anyone to learn steno. That textbook exists today online for free as "[Learn Plover!](https://sites.google.com/site/ploverdoc/home)" and on Amazon as a physical book on-demand.

---

Also coming down the pipeline for free steno education is Steno Arcade, a collection of free steno minigames. This is being created by ForAllToPlay, which I'll quote from their site, "is a game studio that designs and develops video games that are accessible to people with visual, hearing, physical, & cognitive disabilities."

They have a [working demo](https://steamcommunity.com/sharedfiles/filedetails/?id=581831873&searchtext=steno+hero) posted to Steam Greenlight for StenoHero, a lyric typing game with crowd feedback.

Now, as for how I ended up where I am, I'd like to tell you about my stenography experience.

---

# My stenography experience

I had heard about steno, and as a keyboard layout switcher and TypeRacing hobbiest, it appealed to me, no questions asked. The hardware felt like a barrier, but luckily I had an ErgoDox, which I later reprogrammed with NKRO. In August 2014, I started reading through Mirabai's blog and Learn Plover! to start my journey.

Progress went well until I realized that my hardware was not at all ideal (mainly due to the heavy actuation force on my ErgoDox's keys), and school was very busy. Then, after getting a new, lighter-switched ErgoDox, I continued my learning. I hit 100 words per minute about a year in. I received this Tréal machine while working on Plover, and now I'm hovering around 130 words per minute, though in bursts I hit around 180 words per minute.

---

Here's a speed graph of my 2500 TypeRaces. You can see it comes and goes in waves. I've come a long way from 10 words per minute.

So, okay, it's fast, it's free, what is steno good for?

---

# What is it good for?

## Accessibility

Accessibility is very important, and captioning of broadcast television is mandatory in North America. Realtime captioning is used to help deaf or hard of hearing individuals -- Mirabai Knight, captioning live tonight, also captions lectures and conventions.

In the modern age, we face a huge issue where most YouTube videos are posted without transcription, meaning the deaf cannot view a lot of content. YouTube has automatic transcription which is laughable at best. There are many free efforts to caption YouTube videos, but stenography could help alleviate this problem.

Anyone who cannot speak could also use stenography to communicate → if you cannot speak, learn steno and then use a text-to-speech program, and you can write at a conversional pace.

The speed offered by stenography is the only equivalent to regular communication that currently exists and is reliable.

Steno is also good for, well, programming.

---

## Programming

I am using steno to program now, full time in JavaScript, Java, and Python. It works great with Markdown. At the worst, it's about as fast as regular keyboard for coding, and at best you can do multiple words, symbols, or structures at once. Basically, because of the phonetic system, you never need to move off the "home row" for any symbol, really any word. So most symbols are as easy as writing a syllable or a word. It's much more ergonomic, I don't need to look at the keyboard ever, and comments and documentation are trivially easy. I'm going to show you now a FizzBuzz.

Has everyone here heard of FizzBuzz? FizzBuzz is an interview question, and it is used to test basic coding capability. I'm sure that my coworkers and friends can attest that I'm way too obsessed with FizzBuzz. FizzBuzz is a program that prints out the numbers 1 through 100, except if the number is divisible by 3, then it prints Fizz, or if it's divisible by 5, then it prints Buzz, or if it's divisible by both 3 and 5, it prints out FizzBuzz. Let's write a quick recursive FizzBuzz so you can get a feel for coding in steno.

```python
def number_to_fizzbuzz(number):
    string = '%s%s' % ('Fizz' if number % 3 == 0 else '',
                        'Buzz' if number % 5 == 0 else '')
    return string if string else number

def calculate_fizzbuzz(start, end, list=[]):
    if start > end:
        return list
    return calculate_fizzbuzz(start + 1,
                              end,
                              list + [number_to_fizz_buzz(start)])

for fb in calculate_fizzbuzz(start=1, end=100):
    print(fb)
```

There's a fizzbuzz. Okay, cool, it works. Now how does it do that? I'll talk a little bit about the theory behind machine shorthand.

---

# How does it work?

Stenography works by shortening English to as short as possible so that you can express as much as you can with as few keys as possible. I like to think about it as "thinking with portals" → think-ing w portal-s → thig w porls.

---

## Layout

The layout is split into 3 parts, `STKPWHR\*`, `AOEU`, and `\*FRPBLGTSDZ`. The left fingers handle the starting sound of the word, the thumbs handle the vowel sound, and the right hand handles the ending sound. Press all the keys at once to make a chord, and when the chord is released, the word appears on the screen. You can see some simple phonetic examples like cat or Ted: ST*K*PWHR*A*OEUFRPBLG*T*SDZ → "KAT" → "cat". S*T*KPWHRAO*E*UFRPBLGTS*D*Z → "TED" → "Ted". There are also chords for the missing letters on the beginning side, and many ending sounds. Here we see PH being selected, which translates to M: STK*P*W*H*RA*OE*UF*R*PBLGTSDZ which makes "MOER" → "mother"

There's no single way to write on steno, theories tend to be very personal and different people will find different theories easier than others. Some theories are light on memory, but require more strokes, such as Phoenix. These tend to be very phonetic based, as long as you can speak it, you can write it. Some are more memory heavy, like Mark Kislingbury's Magnum theory. Plover ships with a hybrid theory based off of StenED, a sort of middle of the line theory that is easy enough to learn but is still efficient.

---

## Code

Now we'll talk about how Plover, the Python program, actually works.

Plover takes strokes as input, processes the strokes based on a dictionary and orthographic rules, then outputs emulated keyboard keys.

---

The input comes in the form of some sort of steno machine. You have the choice of a computer keyboard, particularly one with NKRO, or a steno machine. There are many custom steno machines made by the open source community, including the Stenoboard and the SOFT/HRUF. These can communicate in NKRO or in serial protocols. Prices for steno machines pictured, in USD: 70-100 for the gaming keyboard, 100-250 for the 3D printed machines, 5000 for the Infinity Ergonomic, and the breadboard machine made by Charles Shattuck?... priceless.

---

When using the NKRO interface, we must suppress all keys that come in from the keyboard, so that the running program only receives the translation. For this, we catch all the keys necessary for steno (`1-0, QAWSEDRFCVTGYHBNUJIKOLP;`) and some others so that there are no accidental key presses. This creates a problem → if you are running an NKRO setup, you can't share your computer with other people. Also, a funny effect of the system is that on OSX, we can't suppress or detect keyboard input in OSX password fields, due to anti-keylogging measures. Thankfully, these issues are solved by using a serial input. Once you are using a serial protocol, you can still steno into a password field, and others are able to use the keyboard as normal, without any steno logic getting in the way. What this means is, effectively, when I'm using my steno machine in a computer, others can still use keyboards. This comes in useful, particularly when pair programming. That covers the input to Plover.

---

Next, the stroke gets processed through the user's dictionary configuration. There are quite a few rules that are involved with dictionaries, but the bulk of it ends up being:

- The dictionary is key-value system where the stroke is the key, and the translation is the output.
- There is no nesting, the dictionary is a flat object. Plover's is represented in JSON.
- Each an entry's key can be a sequence of strokes, as separated by slashes.
- The output is a string, which can contain literal characters, special Plover operators, or commands.
  - The string is literally just the string, most of the time this is what people want. If I want to define a stroke for "Ottawa Python" as a phrase, I write in the strokes and the output, e.g. `"OT/WA/PAO*EUT/*OPB": "Ottawa Python".`
  - You can also tell Plover exactly which keys to hit, including modifiers and special keys. If I want to do a simple control-c, I can define `{#Control_L(c)}`
  - Plover supports certain grammar and logic modifiers, in case you'd like a stroke to be a suffix or prefix, or if you'd like to make the next word capital, or the last word capital. These are just special characters inside curly braces. Like if I wanted to define a suffix like "awesomistically", I could do `"SPHEUFBG": "{^awesomistically}"`, then make any word like: cattawesomistically, Teddawesomistically, and Pythonnawesomistically. You can see that some letters got doubled there, that's thanks to Plover's built-in orthography rules.

The orthography rules are mainly a set of regex replaces to allow the suffix and prefix system to work well, and this makes it more powerful that many of the proprietary systems on the market.

---

Finally, the output stage. At this point, we use an operating system-specific implementation to simulate a keyboard pressing all the keys that Plover does. On OS X, this means using Quartz event APIs, on Linux we deal with XLib, and on Windows we use SendKeys. There are some difficulties when dealing with the three operating systems. Particularly, modifier keys sort of behave differently across the systems, as do keycodes. Making sure that our emulation is effective on all programs has been a great challenge. On Linux, we initially had trouble suppressing the input, so Plover would actually send backspaces to remove all the QWERTY keys that were hit. That's been fixed recently, but was a problem for over 5 years.

On Windows, the Windows key wasn't implemented, and certain programs didn't accept Plover's input, such as pidgin and 10 fast fingers. This change isn't committed to master yet.

On OSX, we always send key code 0 along with a Unicode string. This presents a problem for any legacy applications that don't handle the string, they just see a bunch of key presses to the "A" key. Furthermore, on OSX our command keys fall back to QWERTY key codes, so non-US layouts don't work for commands. For a while, Plover didn't properly support extended Unicode, and that has only recently been fixed on most systems. Linux is stuck to produce only what is defined in X lib, so it cannot do arbitrary keys yet.

---

We also had some problem with full unicode support, which fully manifested with emoji. We weren't able to backspace emojis correctly, treating them as two characters when in reality they were just one. Now that's all fixed, but man, you learn more about Unicode than you ever wanted to know. Apparently all this Unicode stuff has been fixed in Plover 3, but we're still on Python 2.7 in Plover.

Which brings up the point, this software is not finished.

---

There are still a lot of problems that take up my free time when I'm not at school, work, or with family.

There a few big tasks to figure out and implement with Plover. I've had the amazing company of Benoit-Pierre on GitHub, and together with the community we've been looking at some of these lingering issues.

- Our code base is written for Python 2.7, and that's kind of a bummer because Python 3 is a much better language to work with. I'm not actually sold on this as a valid use of time, maybe some of you could inform me why we should jump to 3.x
- Currently, there's no way to "hold down" a modifier, and so you cannot do things like shift or control click, meaning often when I'm doing file management or using Photoshop, I'll find myself needing both my keyboard and my steno machine out.
- Plover has its layout hard coded, meaning that to change the steno layout or the number of keys, you need to modify the source code and rebuild Plover. This is a huge barrier to using stenography in other languages, and it's a high priority to making Plover useful internationally.
- We are using wxPython classic as a our UI, and this proves really difficult whenever we try to do user interface work that is non-trivial in Plover. It would be ideal to move over to someone like QT but that's a huge development effort.
- Plover doesn't look that great, and we only have the one Dolores, as cherished as she is.

---

# Where is steno going?

So by now you might be wondering what the deal is. You know where steno has come from, you know how it works, you know what it can do. But, where is it going? Is court reporting a real job anymore?

Pretty valid questions, and definitely once that the Open Steno Project concerns itself with.

---

The OpenStenoProject is Mirabai's umbrella organization over all that is open steno software, hardware, and learning materials. It contains Plover and some other projects, as well.

As for the future of stenography, it's in the hands of hackers like you and me now. Stenography has great speed, and many people care about that for different reasons. For people like me, it's probably a little more selfish, I want to type fast, I want to code, I want to avoid RSI from programming as a career, I want to be the best at TypeRacer, I want to do it as a hobby, I want to take notes quickly, I want to write documentation quicker, I want to avoid typos, I don't want to have to think about spelling, I want to do everything more quickly on my computer. I fit into this category, and I feel like a lot of you might.

---

If you are curious about learning steno, don't be afraid to get involved in the online community. I don't think there's such thing as a dumb question, just questions that should be Googled first.

I'll leave with some links, there's the Plover Blog that you can see all of Plover's history in as well as keep up with Plover news. Aloft.nu is the realtime website that we've been using today to caption these slides, also created by a Plover community member. There is Stenodict, a website I created to share stenographic dictionaries between stenographers. The Google Group and Discord server are there in case you want to get in touch.

I'd like to thank everyone for coming today, and thank you so much for your attention. I hope that I've been entertaining enough for you, and that you were able to learn, at the very least, some neat trivia. I would like to thank Ian Ward for, as always, setting up the Python Authors Meetup, and for Shopify for generously hosting us in their outstanding office. It's been great talking here tonight, I've been Ted Morin and I hope to have some great chats with you later!
