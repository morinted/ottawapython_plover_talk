# Plover Talk

### For the Ottawa Python Authors meetup group

#### Presentation date: Thursday, January 28th, 2016. 7:30 p.m. EST for 30-45 minutes.

### Summary Blurb

Ottawa Python: How to Write Over 200 Words Per Minute.—Ted Morin

*This talk will be live-captioned for the deaf or hard-of-hearing.* Plover is free software written in Python that enables you to type on a computer at over 200 words per minute. Plover brings machine stenography, an art older than computers, into everyone's hands.

Plover's current lead developer, Ted Morin, will talk about why Plover was created, how it works, and explain the role stenography might have in the modern world, as it moves beyond transcription and into the hands of hackers.

### Topics

## Splash with Stanley Writing on Machine

Hi everyone, today I'm going to be talking about the technology that is being used to write in this GIF. Today's talk is being captioned live, with Mirabai Knight on the other end of a Skype call. As I talk, she's taking down everything I am saying and it is being live streamed through a website called Aloft. Mirabai is a real person, so please don't ask her if she's speech recognition software, because she's much more accurate than that. Also, sometimes she writes back. You can follow along the slides and captions on your personal computer at OpenSteno.org/pygotham2016

---

## Who, you?

I'm Ted Morin, @morinted on Twitter and GitHub. I'm currently finishing up my software engineering  undergraduate at the University of Ottawa in Ontario, Canada. I split my time between school and working for a high-tech medical start up, Clearwater Clinical. There I use JavaScript, consisting of mainly React and Redux, to build web applications for their products.

I'm actually a big fan of JavaScript, which really doesn't give me many brownie points with die hard Pythonistas.

I've used Python for what I'd consider a while, way before JavaScript because things like Node didn't exist at the time. It was my first scripting language, first language I was using through a command-line. I used it a lot at home whenever I had to work through a math problem or build a quick web scraper.

In my free time I lead development for Plover, though I'm lucky to work with members of the community who are smarter and more experienced than me.

So--I'm a software developer, but I use a steno machine to write all my code.


## Introduction

These are steno machines. They're similar to a computer keyboard in size, but you write on them a little bit more like you play a piano. You hit a bunch of keys to form a chord, then release all the keys at once, and out comes full words, sentences, symbols, whatever.

I've known about stenography for two years now, and I'm excited to get the chance to share it with you today.

Stenography allows people to write on a computer at over 225 words per minute, on par with human speech. I'm here right now because Plover, the first free steno software, is written in Python.

---

I'm going to start us off with a quick demo video I made to show the difference between writing with a steno machine versus a Qwerty keyboard. I'm playing a free game on Steam called Steno Arcade, which was created by an accessibility-focused gaming company in partnership with Open Steno, and was recently successfully crowdfunded. In the game, you write the lyrics to a song as the singer sings them for a high score. Go download it when you get home.

I want to show you what it looks like to write on a steno machine, and you can see the contrast in my hand movement, effort, and game accuracy. Please note that I'm not the fasted typist nor stenographer by far.

---

## Table of contents

Here's what I'm going to talk about today:

### Plover

- What is **Stenography**
- How fast do we *need* to type
- Steno layout and basics
- History of Open Steno
- Isn't this a Python conference when are you going to talk about Python?
- Future of steno (and you)

My goal today is to tell you about Plover, open source stenography software written in Python. To do that, I need to define what stenography is and why its high speed is so useful. I'll also try to convey in simple terms a little bit of the mental process that a stenographer goes through when writing, in a method I call Thinking with Portals. We'll go over how Plover and Open Steno came to be, then talk a little bit about the Python program behind it. Finally, I'll close with some thoughts about where I think steno will be in the future.

---

## What is Stenography, in the first place?

Stenography is a system of writing that aims to decrease the amount of effort required to express language. You may have heard of written shorthand systems like Gregg and Pitman, which were commonly used by journalists, students, and court reporters to take written notes quickly.

---

The stenography that I'm talking about, machine stenography, is based off the same theory as written shorthand. Basically, it's a system that optimizes for English, mainly phonetically, in order to increase output speed of transcription. With machine stenography in particular, the stenograph allows you to chord keys, that means that instead of writing out the letters of a word you produce the sound. This vintage-style paper tape shows what a machine stenographer might have written before instant computer stenography existed. The stenographers of the last century would produce this ticker tape output as people spoke, and then later would transcribe what the machine produced. This ticker tape clearly reads: "you should be able to read these short words". Nowadays, translation is instant, as you can clearly see by the captions being produced overhead.

For the actual layout, the system works in a declarative way. The keys you press get read by the software, left to write like on the steno paper here. The left hand is the beginning consonant, the blue keys, the thumb keys at the bottom make up the vowel sounds, and the right hand makes up the ending consonant.

For missing letters, they are achieved by hitting combinations of other keys that generally don't conflict phonetically. For example, the "L" sound can start a word by pressing the "HR" keys, because words don't start with LR or HL

---

As I've hinted, stenography in English is a phonetic system. For English in particular, we have the case where phonetics are rather simple and spelling often just plain doesn't make sense.

With a phonetic system, you don't really have to think about spelling. Think of these phonetically similar words, "nauseous" and "cautious" and "conscious". They are all spelled differently, but have the same sound ending. In steno, you write these all with the same suffix, and only the prefix changes, effectively "naw", "caw", and "con" followed by "shs".

Through other rules, we can phonetically shorten a word. Like "particular", we can sort of drop most of the word and sound out "p-lar" which isn't a real word, and by extension "particularly", which is 12 letters, it can be written in one stroke, which is given by the phonetic input "p-lar-l".

Stenography is much faster than regular typing.

---

## How fast is it actually?

Here are some average speeds in terms of words per minute.

Handwriting 25WPM < Hunt and Pecker 40WPM < Touch typist 80WPM < Casual Speech 160WPM < Practical Speech Recognition 180WPM < Stenography 225WPM

These, of course, are averages, the top typist in the world, Sean Wrona, types at 170 words per minute on average with a QWERTY keyboard. The top stenographer in the world, Mark Kislingbury, holds a world record at 360 words per minute, writing around 250 to 300 words per minute for extended periods of time.

So this is to say that for most people, stenography can increase your writing speed from 2 to 4 times its current speed, to a point faster than human speech.

---

# How does it work?

So how do we get from full words to phonetic systems? It's hard to describe, but while learning stenography you get a better grasp on the word startings and endings that you can encounter, as well as the vowel sounds. I'll take my example phrase, "Thinking with Portals". I see the -ing suffix, which is super common. "with" is a word that is used all the time, we'll just assign it "w". There's also the "-s" suffix present. Luckily the steno machine ends with an s key so you can pluralize almost any stroke. Finally, I'm going to drop unstressed vowels, and mix in a little bit of personal understanding. I think of this phonetically as written here, [*phonetically*] "thi-ing wi porals"

You end up with only three strokes, one per word, with the representation shown below. The number of keys you use in a stroke generally doesn't matter, since you move your whole hand up and down. So while "with" is just one key and "thinking" and "portals" is 5, there's not much difference in effort there.

---

# What is it good for?

## Accessibility

Accessibility is very important, and captioning of broadcast television is mandatory in North America. Realtime captioning is used to help deaf or hard of hearing individuals -- Mirabai Knight, captioning live tonight, also captions lectures and conventions. Currently two of her coworkers at White Coat Captioning, Norma Miller and Stanley Sakai, are captioning the WordCamp conference for deaf or hard of hearing individuals. 1 in 5 people report some kind of hearing loss. It's common for people to have hearing loss and not realize that they are missing out. It's also possible for hard-of-hearing individuals to not realize that captioning is a resource that they can be provided with. There are definitely points during this conference where I missed what was said and I can't imagine how difficult that must be if you are hard of hearing.

In the modern age, we face a huge issue where most YouTube videos are posted without transcription, meaning that many cannot view viral videos and important news. YouTube has automatic transcription which is laughable because even at 90% accuracy, you are making mistakes every sentence. There are many free efforts to caption YouTube videos, but it captioning is much quicker on a steno machine than a keyboard.

Another opportunity for steno to be useful for accessibility is people who don't speak. Anyone who doesn't speak but has full hand motor skills could use stenography to communicate with text to speech. They could hold conversations with stenography's great speed that rivals speech.

The speed offered by stenography is the only equivalent to speaking that currently exists and is reliable.

Steno is good for other purposes, anyone who types could benefit. It helps you get thoughts down and saves time and effort for your hands. It's great for chatting online as you can keep the pace of conversation up.

Steno is also good for, well, coding.

---

## Programming

I use steno to program now, full time in JavaScript, Java, and Python. It works great with Markdown. At the worst, it's about as fast as regular keyboard for coding, and at best you can do multiple words, symbols, or structures at once. Basically, because of the phonetic system, you never need to move off the "home row" for any symbol, really any word. So most symbols are as easy as writing a syllable or a word. It's much more ergonomic, I don't need to look at the keyboard ever, and comments and documentation are trivially easy. There's a video of me coding a fizzbuzz in JavaScript on the web, I write slowly in the video as I explain my thought process. On the right is Mirabai taking down some of Plover's source code. She's a faster stenographer than me so you can see what she came up with.

---

## Open Source Stenography

Let's talk a little bit about learning machine stenography about a decade ago. To learn stenography, you need 3 things:

- Hardware (input)
- Software (logic) to handle the input from the hardware and convert it into plain English
- Education (understanding) in order to learn the system and get faster

Just under a decade ago, all three of these things were only available in proprietary form.

---

It cost about one to four thousand dollars for the hardware, a thousand dollars yearly subscription for the software, and thousands for a college education, which can take 1 to 7 years.

The proprietary software solutions were created for the purposes of creating printed official court transcripts, and as such the software ended up being a walled-garden sandbox where you can only write into a document, like an enhanced Microsoft Word. That means that you are limited to only using steno to collect text.

Steno was probably one of the most proprietary technologies in the world, and it got that way because of its niche use, leading it to be a market with very few companies in charge. All that changed, though, when a geek learned steno.

---

Today steno is a very welcoming and fun community. The software to get started is free, there are free tutorials, text books, games, and practicing websites. The hardware price has also decreased by a magnitude, bringing it down to the hundreds instead of the thousands.

---

Mirabai Knight is, as I mentioned, a geek. Here, I've collected some pictures as proof. She's captioning this talk today. She graduated from a court reporting school in March 2007, and was fed up with the whole system. She had this technology that allowed her to express ideas effortlessly at previously unattainable speeds, but was unable to use it for most of her everyday life, with software that was severely lacking in features. You can read through the Plover Blog all the way back to 2008 when Mirabai had conceived what would one day be Plover. She wanted an open source steno program to solve all the problems that the other software didn't.

But, she couldn't code. Whoops. So an elevator ad, a little chance, and a dash of fate later, Mirabai actually met a freelance software engineer with a PhD from the MIT media lab who was willing to teach her Python.

---

Joshua Lifton started to teach Mirabai Python, but as he soon found out, Mirabai wasn't totally interested in learning to code, but rather just how to code a single program. So, they started to code a free steno engine together, and given a little bit more time, Mirabai decided that coding wasn't really her thing, and Joshua started developing the application on his own.

And so, Plover was born!

---

Plover is a species of bird. Why is it the name of a steno program? The way you write Plover on a steno machine is how many court reporters write "moreover". Moreover is a very court-ey word, and Mirabai wants Plover to be steno software for everyone, not just for court reporters.

The wing on the Plover bird Dolores is actually a steno machine, and the dark keys are the stroke for "Plover". 

Plover is unique because it doesn't require a steno machine, but rather just any keyboard that lets you register all keys at once. It was a very simple application and over many years, Plover grew. Josh eventually had to leave the ecosystem to focus on his company CrowdSupply, but before he did he announced the Stenosaurus.

---

The Stenosaurus is still in the works, but it has a blog where you can follow along on its development. It is a beautiful piece of hardware and will be hundreds of dollars instead of thousands like the steno machines currently on the market.

So, without a developer, is Plover doomed? Well, no. After Josh left, another developer found himself interested in steno.

---

Hesky Fisher, who works as an engineer at Google, took over. Hesky made a big push in adding steno machine protocol support, vastly improving the cross platform functionality, and much more in his time as lead developer. He was super productive and still hangs around as a wiseman among the open steno community.

Once people started to notice Hesky's absence, there was a clear need for a new developer. I'm no MIT graduate, heck I'm not even a uOttawa graduate yet, but last summer I found myself taking on the torch of Plover's lead dev.

Now, Plover is at a pretty great place that fills in a huge gap that existed just 6 years ago:

Plover is cross platform, working on Linux, Windows, and OSX. It allows you to use modifiers, like control, Alt, and the Windows key. It works with many steno machine protocols, which run over serial. The best part is: it's free, and that means people can modify it and improve it and all the users benefit.

Software is free, hardware is being freed. The last big block in you learning steno is well... learning it.

---

## Learning

That's where Zack Brown comes in. He is a technical writer who has worked at Google and with the Linux Foundation. He took interest in learning steno and reached out to Mirabai. In exchange for lessons on stenography, he was to document them and write a free textbook for anyone to learn steno. That textbook exists today online for free as "[Learn Plover!](https://sites.google.com/site/ploverdoc/home)" and on Amazon as a physical book on-demand.

---

# My stenography experience

I'm just going to take a moment to tell you about my personal journey with steno.

I had heard about steno on Hackernews, and as a keyboard layout switcher and TypeRacing hobbyist, it appealed to me, no questions asked. The hardware felt like a barrier, but luckily I had an ErgoDox, which with certain firmware supports NKRO. In August 2014, I started reading through Mirabai's blog and Learn Plover! to start my journey.

Progress has been pretty steady and as I've gotten more involved with steno I've gotten nicer hardware. I hit 100 words per minute about a year in. I received this Tréal machine while working on Plover, and now I'm hovering around 140 words per minute, though in bursts I hit around 180 words per minute.

---

Here's a speed graph of my 2700 TypeRaces. You can see it comes and goes in waves. I've come a long way from 10 words per minute.

---

## Code

Now we'll talk about how Plover, the Python program, actually works.

Plover takes strokes as input, processes the strokes based on a dictionary and orthographic rules, then outputs emulated keyboard keys.

I'll talk about how Plover has to deal with specialized hardware, steno logic, and then actually output something in order to functionally replace a keyboard.

---

The input comes in the form of some sort of steno machine. You have the choice of a computer keyboard, particularly one with NKRO, or a steno machine. There are many custom steno machines made by the open source community, including the Stenoboard and the SOFT/HRUF. These can communicate in NKRO or in serial protocols. Prices for steno machines pictured, in USD: 70-100 for the gaming keyboard, 100-250 for the 3D printed machines, 5000 for the Infinity Ergonomic, and the breadboard machine made by Charley?... priceless.

---

When using the NKRO interface, we must suppress all keys that come in from the keyboard, so that the running program only receives the translation. For this, we catch all the keys necessary for steno (`1-0, QAWSEDRFCVTGYHBNUJIKOLP;`) and some others so that there are no accidental key presses. This creates a problem → if you are running an NKRO setup, you can't share your computer with other people. Also, a funny effect of the system is that on OSX, we can't suppress or detect keyboard input in OSX password fields, due to anti-keylogging measures. Thankfully, these issues are solved by using a serial input. Once you are using a serial protocol, you can still steno into a password field, and others are able to use the keyboard as normal, without any steno logic getting in the way. What this means is, effectively, when I'm using my steno machine in a computer, others can still use keyboards. This comes in useful, particularly when pair programming. That covers the input to Plover.

---

Next, the stroke gets processed through the user's dictionary configuration. There are quite a few rules that are involved with dictionaries, but the bulk of it ends up being:

- The dictionary is key-value system where the stroke is the key, and the translation is the output.
- There is no nesting, the dictionary is a flat object. Plover's is represented in JSON.
- Each an entry's key can be a sequence of strokes, as separated by slashes.
- The output is a string, which can contain literal characters, special Plover operators, or commands.
  - The string is literally just the string, most of the time this is what people want.
  - You can also tell Plover exactly which keys to hit with a macro language. This language includes modifiers, special keys, and media keys. If I want to do a simple control-c, I can define `{#Control_L(c)}`
  - Plover supports certain grammar and logic modifiers, in case you'd like a stroke to be a suffix or prefix, or if you'd like to make the next word capital, or the last word capital. These are just special characters inside curly braces. Like if I wanted to define a suffix like "awesomistically", I could do `"SPHEUFBG": "{^awesomistically}"`, then make any word like: cattawesomistically, Teddawesomistically, and Pythonnawesomistically. You can see that some letters got doubled there, that's thanks to Plover's built-in orthography rules.

The orthography rules are mainly a set of regex replaces to allow the suffix and prefix system to work well, and this makes it more powerful than many of the proprietary systems on the market.

---

Finally, the output stage. At this point, we use an operating system-specific implementation to simulate a keyboard pressing all the keys that Plover does. On OS X, this means using Quartz event APIs, on Linux we deal with XLib, and on Windows we use SendKeys. There are some difficulties when dealing with the three operating systems. Particularly, modifier keys sort of behave differently across the systems, as do keycodes. Making sure that our emulation is effective on all programs has been a great challenge.

I'll list some shortcomings that have been fixed recently on each system:

- On Linux, we initially had trouble suppressing the input, so Plover would actually send backspaces to remove all the QWERTY keys that were hit.

- On Windows, the Windows key wasn't implemented, and certain programs didn't accept Plover's input, such as pidgin and 10 fast fingers.

- On OSX, we used to always send key code 0 along with a Unicode string. This presented a problem for any legacy applications that don't handle the string, they just see a bunch of key presses to the "A" key. Furthermore, on OSX our command keys fell back to QWERTY key codes, so non-US layouts didn't work for commands.

These problems weren't trivial to solve, and I think that the cross-platform output we have is really good now, we should probably break it out into a Python library.

---

We also had some problem with full unicode support, which fully manifested with emoji. We weren't able to backspace emojis correctly, treating them as two characters when in reality they were just one. Now that's all fixed, but man, you learn more about Unicode than you ever wanted to know. All this Unicode stuff has been fixed in Plover 3, but we're still on Python 2.7 in Plover, for now. Our most excellent contributor right now is working on porting Plover to Python 3 in a huge overhaul of the internals and UI.

---

# Where is steno going?

There are still a lot of problems that take up my free time when I'm not at school, work, or with family. There are over 50 issues open on GitHub right now, all of various sizes.

There a few big tasks to figure out and implement with Plover. I've had the amazing company of super-developer Benoit Pierre on GitHub, and together with the community we've been working through long time issues.

I feel great reward working on Plover, as it's probably one of the more diverse online communities I've seen. We get people from all over the world, many with little or no development skill but a great interest and passion for stenography. We get people who are looking to adapt Plover to their language's steno system, or to develop new steno systems for languages that don't have one. Or even using lexigraphical analysis to try and best the classic steno layout (which they haven't yet). I have fun meeting with and chatting the community.

So by now you might be wondering what the deal is. You know where steno has come from, you know how it works, you know what it can do. But, where is it going? Is court reporting a real job anymore?

Pretty valid questions, and definitely one that the Open Steno Project concerns itself with.

---

The OpenStenoProject is Mirabai's umbrella organization over all that is open steno software, hardware, and learning materials. It contains Plover and some other projects, as well.

As for the future of stenography, it's in the hands of hackers like you and me now. Stenography has great speed, and many people care about that for different reasons. For people like me, it's probably a little more selfish, I want to type fast, I want to code, I want to avoid RSI from programming as a career, I want to be the best at TypeRacer, I want to do it as a hobby, I want to take notes quickly, I want to write documentation quicker, I want to avoid typos, I don't want to have to think about spelling, I want to do everything more quickly on my computer. I fit into this category, and I feel like a lot of you might too.

---

If you are curious about learning steno, don't be afraid to get involved in the online community. I don't think there's such thing as a dumb question, just questions that should be Googled first.

I'll leave with some links, there's the Plover Blog that you can see all of Plover's history in as well as keep up with Plover news. Aloft.nu is the realtime website that we've been using today to caption these slides, also created by self-taught Plover stenographer Stanley Sakai. There is Stenodict, a website I created to share stenographic dictionaries between stenographers. The Google Group and Discord server are there in case you want to get in touch.

I'd like to thank everyone for coming today, and thank you so much for your attention. I hope that I've been entertaining enough for you, and that you were able to learn, at the very least, some neat trivia. It's been great talking here this afternoon. I'll stick around and you can play a little with the steno machines I brought to see what it's like. I've been Ted Morin and I hope to have some great chats with you later!

