---
title: 'Monophonic 53edo Pitch Input Prototype'
media_order: 53edo_nanopad.jpg
date: '07-06-2020 19:25'
taxonomy:
    tag:
        - 53edo
        - DMI
twittercardoptions: summary
articleenabled: false
musiceventenabled: false
orgaenabled: false
orga:
    ratingValue: 2.5
orgaratingenabled: false
eventenabled: false
personenabled: false
restaurantenabled: false
restaurant:
    priceRange: $
---

For several years I have been dreaming of alternatives to 12edo (edo = Equal Division of the Octave)
temperaments that would allow for more harmonic expressivity as well as simply more in tune chords,
as I've found the thirds on 12edo keyboard instruments to be really quite harsh, especially when
using a harmonically rich sound such as a sawtooth waveform. My earlier digital musical instruments
have tried to cope with this by banishing quantised pitch altogether in a similar way to fretless
string instruments (disregarding the guide and resonance provided by the open strings). But maybe using a more fine-grained grid like 53edo will provide a way to theorise
around pitch in a more open way and through that open up to new ideas and musical opportunities.

## Proving It Technically Works

[plugin:youtube](https://www.youtube.com/watch?v=ZkfwQGc83XA)

Yay, it works! It's not the easiest instrument I've ever played, my brain has not incorporated the grips yet, which is good because now that I've proven it works I'm going to start changing stuff. I'll just explain how it works first.

## 53edo

[In a previous blog post I introduce 53edo](https://eriknatanael.com/blog/how_to_get_better_pitches_53edo_part1) and some of its benefits and challenges. 53edo has been
known about for a long time (Chinese music theorist Ching Fang (78–37 BCE), Nicholas Mercator
(c. 1620–1687), Isaac Newton (1642 - 1727), RHM Bosanquet made a keyboard for it in 1872-3 etc), but
has an unwieldy number of notes for a mechanical/acoustic instrument. Too many strings to tune and
too expensive to produce instruments with so many parts. (As an aside, 53edo has seen some use in
Turkish music and I need to do more research into how the Turkish instruments make use of it.)

## Pitch Input Method

An idea started to form that digital technology might make this large nunmber of pitches easier to
handle. Taking inspiration both from keyed wind instruments I figured that fingers are quite good at
manipulating a number of on/off switches. The most efficient way to get many values out of a number
of switches is by treating them as a binary number. With a binary number, the maximum number that
can be written is (2^n)-1 where n is the number of bits (in this case switches/buttons). With one
button per finger of one hand we therefore can represent values between 0 and 31, exactly a 53edo
perfect fifth.

The note input on this prototype therefore works like a binary number using the first 5 buttons,
each of them adding 1, 2, 4, 8, or 16 to the total note value. In addition to this there is a button
that adds 31 which is one less than the 32 that would have made it continuation of the binary
number, but since 31 is a perfect fifth it creates a nice symmetry that makes it easier to play. The
octave buttons also trigger and hold the note.

## Some 7th Chords

[plugin:youtube](https://youtu.be/f-1F1lptvqY)

I'm playing the 7th chords with a 7th going from a 7/4 minor harmonic 7th to a 15/8 downmajor seventh. I think these all sound quite nice and useable, but with different qualities. The minor chord seems more sensitive to the perfect fifth between the minor 3rd to the minor 7th than the major chords fifth between the major 3rd and the major 7th.

## Where To Go From Here

The nanoPAD is not great for the purpose I'm using it for since I need to press really quite hard to get the pads to register as on so the next step will be to build a paper prototype using capacitive sensors that require no force to activate. I'm also evaluating including extra optional buttons to make certain things easier to play, or rather I'm having my computer crunch the numbers on what buttons make certain things (such as scales, chords and melodies in 5-limit-ish subsets) take less finger movement to play.