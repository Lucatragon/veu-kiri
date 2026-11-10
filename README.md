Introducing **Veu Kiri**, my little project for a while.

Veu Kiri is a special program licensed under **VFL2**. 

Right now, this Readme looks a bit bland, yes I know I gotta fix that.

However, I can't write Readme's to save my life, so XD

Anywhos. 

WHAT IS VEU KIRI?
----------------------------------------------------------
Veu Kiri is a special little program that I am making for three reasons.
1. I want to.
2. I would like a way to make audio smaller (under the guise that I might not be able to do much other than prove "quality versus quantity"), and
3. I feel like OGG, MP3, WAV, etc etc are super bloated and unneccessary for true day-to-day listening. Yes - even Opus and Vorbis. I remember when assetys used to be incredibly small, I remember when my dad showed me a videogame that was 96 KB on disk (.kkrieger) and being astonished that my daily-driven SSD to hell and back could probably load 1 700 copies of this game ***in RAM***.

And so I thought, "what the hell?" Why are games so big now? Why is audio especially massive? Note: Minecraft Java Edition thanks to Microslop™️ has recommended specifications of 16 GB of RAM ***itself*** and an Intel Core i5 12th Gen. That means my daily-driver laptop's CPU alone isn't up to specifications. 

*"Oh, well I'm playing it on [whatever fucking hardware you have] and I'm not getting lag!~"* Yeah sure, you might not be... but even if you aren't actually getting any lag at that hardware... those minimum and recommended specifications for a 3 dimensional block sandbox game with dirt blocks that are ***4096 cubic pixels in size,*** *are* ***fucking ridiculous*** regardless of what they are, compared to a first person shooter that is as big as a player's average save file in most post-2014 indie games, that also has enemies, ammunition collection, ACTUAL AUDIO, for hell's sake. 


### I've wanted to see a change for a long while now, and there hasn't been one. So I'm making one, and that's where Kiri comes in.

And I'm starting with audio.

Kiri in and of itself is my take at what audio could be. It uses structural analysis using local tools and drivers on your computer and CPU formulas to work virtually seamlessly, streaming assets of songs directly into RAM and using the rest of the song as a time-based grid-based execution array. This means that audio files that use the same instruments but are different in structure and form could be virtually 20% different in file size, at a maximum. This also means that a pure-white noise and sine wave "432 Hz meditation music" track that is 60 minutes long, could use less bytes of both RAM and storage, than Bloody Mary by Lady Gaga. The event data itself could be 3x less than an actual song, if not more of a reduction, regardless of the fact that 60 minutes is about 16 times longer than Bloody Mary, if and only if you optimize the track.

Could. I keep using that word, because Kiri is not finished yet. 

Then, I'll start on the actual programming itself, changing the way programming is even defined in the dictionary, because it's high time we have ease of access built into our programs where 9 times out of 10 the one looking at your code has no idea what they are looking at.

Kiri itself is just the audio. But, the audio *what*?
* The audio stack
* The audio driver itself (soon)
* The entire system that makes sound itself possible to computers and digital machinery.

I will be utilizing ALSA for the Linux version, WASAPI for the Windows version, and CoreAudio for the Macintosh version.

As of right now, it will utilize compatibility with ``.wav`` files and it will also utilize Ruby as a language. The frontend will be coded in Ruby, the backend will be later coded in C. Formatting a ``.kso`` (Kiri Sound Output) file will come later in this Readme.

Also as of right now, it will be programmed in such a way that it serves as a watchdog on your system. You will need to open .kso files directly in the player, which is an application. 

### The best way for me to describe a .kso file's format is Sprunki, or Incredibox.
Every ``.kso`` file consists of the following bytes: ``kso!H``, ``!I``, ``!C``, and ``!K``. These could be in their abbreviated form, or in their long form, ``!Header``, ``!Information``, ``!Chart``, and ``!Kill``.

* ``!Header`` is the header of text and other stuff, basic metadata before ``!Information`` needs to load.
* ``!Information`` is the tab where everything in terms of instrument data and chart data is in place. Basically, "is it something ``!Chart`` needs to know?"
* ``!Chart`` is the guts of the song, but it is normally the smallest of the data headers (other than of course ``!Header``). It stores song data, where and how instruments sing or play, and could even cook pizza if you asked it nicely! (spoiler alert, it doesn't. I tried) :(
* ``!Kill`` is the last bit of the song, nothing after it, and its job is to end the song data. It's basically our ``EOF`` if you will.

Here's an example file:

```
kso!Header
    Lady Gaga | Bloody Mary | 00000000
!Information
    Instrument Clarinet : 0007A6A6A7E8F88E777BE0787D6897DFEBDFED98DD0D7F7EE0F0D7E80D7D... : wC
    Instrument Flute    : 00AAFE85DD93AA210E34665A68BE716E9D00FEDE6A7A88D99E77765F441B... : wF
    Factor 4, Section 4, Time 4 4, Speed 120, Offset 200
    F0 wC, F1 wF, F2 wC, F3 wF
    F0 bb 3, 000 fff
!Chart {
F0  000  000  000  000  000  000  000  000
F1  0000 0000 0000 0000 0000 0000 0000 0000
F2  0000 0000 0000 0000 0000 0000 0000 0000
F3  0000 0000 0000 0000 0000 0000 0000 0000

    000  000  000  000  000  000  000  000
    0000 0000 0000 0000 0000 0000 0000 0000
    0000 0000 0000 0000 0000 0000 0000 0000
    0000 0000 0000 0000 0000 0000 0000 0000

    000  000  000  000  000  000  000  000
    0000 0000 0000 0000 0000 0000 0000 0000
    0000 0000 0000 0000 0000 0000 0000 0000
    0000 0000 0000 0000 0000 0000 0000 0000

    000  000  000  000  000  000  000  000
    0000 0000 0000 0000 0000 0000 0000 0000
    0000 0000 0000 0000 0000 0000 0000 0000
    0000 0000 0000 0000 0000 0000 0000 0000
}
!Kill
```

### So first, a few things
--------------------------------------------------------
1. Is that it? 
    Yup, that is. That's 2 measures, 4 seconds, at 120 bpm, and each note is separated into 4 segments (The equivalent of '1-y-and-a-2-y-and-a-3-y-and-a-4-y-and-a'). For those who don't want to count, ***four segments right now, right here, is only 180 bytes per second.***
2. What do the zeroes mean?
       Basically, this:
   ```
   000 000 000 000 000 000 000 000 000 000 000 000 000 000
    |_ A single segment of data.
       Stores a hexadecimal, in this case, 000 to fff (lowercase).

   000 000 000 000...
   |_______________|_ A group, or a measure, assuming Section is 4, and not something else like 2, 6, 8,
                      or up to 64. A Section of 8 is the same as saying that "the most complexity in my
                      song is going to be eighth notes."
   ```
3. Is there a limit to how long a song can be? No, not at all!
4. Is there a limit to how many instruments there can be at a time? Yes, there is a limit of 16 channels at a single time, and of those 16 channels, each one can only have 36 instruments loaded at all, one instrument at a time. That is 576 instruments in total, thankfully I don't believe anyone will ever hit that limit.
5. Was there another way to compress as well? Yes! Actually, here:

Inside of a ``.kso`` file, we have:
```
000 000 000 000 000 000 000 000
```
How should we fix this? Because right now it uses a lot of data just sitting there...

Why don't we find out where the line of text ends and add a counter to tell us how many ``000``s there are? So like:
```
000x8
```
And there we have it. We went from 31 bytes down to 5. Note, each set, or row of data, needs 8 measures of code, we can't just say ``000x97373`` and expect it to know what we're saying. ``.ksn`` files would take care of that. Note, they can't be read by Kiri's DAW, but they can be read by Kiri's audio player.

So let's implement it. 
```
kso!Header
    Lady Gaga | Bloody Mary | 00000000
!Information
    Instrument Clarinet : 0007A6A6A7E8F88E777BE0787D6897DFEBDFED98DD0D7F7EE0F0D7E80D7D... : wC
    Instrument Flute    : 00AAFE85DD93AA210E34665A68BE716E9D00FEDE6A7A88D99E77765F441B... : wF
    Factor 4, Section 4, Time 4 4, Speed 120, Offset 200
    F0 wC, F1 wF, F2 wC, F3 wF
    F0 bb 3, 000 fff
!Chart {
F0  000 x8
F1  0000x8
F2  0000x8
F3  0000x8

    000 x8
    0000x8
    0000x8
    0000x8

    000 x8
    0000x8
    0000x8
    0000x8

    000 x8
    0000x8
    0000x8
    0000x8
}
!Kill
```

There we have it. It went all the way from about ``0.176 KBps`` down to a staggering ``0.044 KBps``. For the kilobits nerds, that's ``356 kbps`` now compared to back when we had a massive ``1404 kbps``...

And yet, it's readable. And that's what I feel we need more of: readable code.

And yet, it's hearable, we can distinguish all of the notes (which is right now empty space), perfectly fine. 

Opus and Vorbis couldn't do 4kbps if they wanted to: ``libopus`` only supports a 4kbps mess and ``libvorbis`` only supports 8kbps.

Inside of Kiri's DAW, will be a checkbox option to export in the compressed version of ``.kso`` which is ``.ksoc``, or to just export as a ``.kso`` in the first place. 

That is it for this README. There will be more stuff. 
