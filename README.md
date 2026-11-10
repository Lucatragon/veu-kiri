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

And so I thought, "what the hell?" Why are games so big now? Note: Minecraft Java Edition thanks to Microslop™️ has recommended specifications of 16 GB of RAM ***itself*** and an Intel Core i5 12th Gen. That means my daily-driver laptop's CPU alone isn't up to specifications. 

*"Oh, well I'm playing it on [whatever fucking hardware you have] and I'm not getting lag!~"* Yeah sure, you might not be... but even if you aren't actually getting any lag at that hardware... those minimum and recommended specifications for a 3 dimensional block sandbox game with dirt blocks that are ***4096 cubic pixels in size,*** *are* ***fucking ridiculous*** regardless of what they are, compared to a first person shooter that is as big as a player's average save file in most post-2014 indie games, that also has enemies, ammunition collection, ACTUAL AUDIO, for hell's sake. 


### I've wanted to see a change for a long while now, and there hasn't been one. So I'm making one, and that's where Kiri comes in.

And I'm starting with audio.

Kiri in and of itself is my take at what audio could be. It uses structural analysis using local tools and drivers on your computer and CPU formulas to work virtually seamlessly, streaming assets of songs directly into RAM and using the rest of the song as a time-based grid-based execution array. This means that audio files that use the same instruments but are different in structure and form could be virtually 20% different in file size, at a maximum. This also means that a pure-white noise and sine wave "432 Hz meditation music" track that is 60 minutes long, could use less bytes of both RAM and storage, than Bloody Mary by Lady Gaga. The event data itself could be 3x less than an actual song, if not more, regardless of the fact that 60 minutes is about 16 times longer than Bloody Mary.

Could. I keep using that word, because Kiri is not finished yet. 

Then, I'll start on the actual programming itself, changing the way programming is even defined in the dictionary, because it's high time we have ease of access built into our programs where 9 times out of 10 the one looking at your code has no idea what they are looking at.

Kiri itself is just the audio. But, the audio *what*?
* The audio stack
* The audio driver itself (soon)
* The entire system that makes sound itself possible to computers and digital machinery.

I will be utilizing ALSA for the Linux version, WASAPI for the Windows version, and CoreAudio for the Macintosh version.

As of right now, it will utilize WAV compatibility and it will also utilize Ruby as a language. The frontend will be coded in Ruby, the backend will be later coded in C. Formatting a .kso (Kiri Sound Output) file will come later in this Readme.

Also as of right now, it will be programmed in such a way that it serves as a watchdog on your system. You will need to open .kso files directly in the player, which is an application. 

### The best way for me to describe a .kso file's format is Sprunki, or Incredibox.
Every .kso file consists of the following bytes: kso!H, !I, !C, and !K. These could be in their abbreviated form, or in their long form, !Header, !Information, !Chart, and !Kill. 

Here's an example file:

```
kso!Header
    Lady Gaga | Bloody Mary | 00000000
!Information
    Instrument Clarinet : 0007A6A6A7E8F88E777BE0787D6897DFEBDFED98DD0D7F7EE0F0D7E80D7D... : wC
    Instrument Flute    : 00AAFE85DD93AA210E34665A68BE716E9D00FEDE6A7A88D99E77765F441B... : wF
    Factor 4, Section 4, Speed 120, Offset 200
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
