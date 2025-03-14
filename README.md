# Yabasic Games

This repository contains new games written in the Yabasic implementation of the Basic language, as well as some modifications of older Basic games to work within Yabasic.

The games in this repository are primarily in the style of "economic simulation" type games.

This repository accompanies [Programming a Basic Game](https://charlesstudy.temple.edu/event/14200746) workshop for the [Electronic Faire](https://sites.temple.edu/efaire/) 2025 at Temple University's Charles Library.

[Slides to accompany my workshop](https://docs.google.com/presentation/d/1zZ4FVsBcjpZPdGgco8aE0CsfcyuVwuOoBaO6PkX0xXU/edit?usp=sharing)

## Yabasic Resources

[Download Yabasic](https://2484.de/yabasic/)

**[Yabasic Reference Manual](https://2484.de/yabasic/yabasic.htm)**

[TutorialsPoint Online Ya Basic Compiler](https://www.tutorialspoint.com/execute_basic_online.php)

## The Games

### Catanite

This is a simple economic simulation game inspired by Star Trader and Dope Wars/Drug Wars.

### Cyberhoss

This is a cybernetic *hoss*-racing gambling game inspired by [Quibble Race](https://ufo50.miraheze.org/wiki/Quibble_Race) in the games collection UFO 50.

### Gobi

This is a desert travel survival adventure game, and the second time I've programmed this game. It is in the style of the game Oregon Trail. I programmed the first version of Gobi as a web-based game and now ported it to Basic. It was originally inspired by an unknown Shareware game that I had on a CD-Rom of hundreds of Mac games in the mid-90s, now lost to time and memory.

### Hamurabi

This is a light port of the original 1973 version of Hamurabi published in Basic Computer Games. Detailed notes at the end of this document. The source code for the original was published by David Ahl.

## Not Games

### Hunt

This is not a game but a lifting of the source code comments/remarks from Oregon Trail and then an attempt to write a modern version of the hunting simulation algorithm in Yabasic.

### Pig

Not much of a game. This is an extremely simple simulation of the dice game Pig, for one player! The goal was to teach how to set up a recurring game loop.

### Pirate Name

Not a game! Pretty much a "Hello World" program to introduce Yabasic to an audience.

### Randos

Also not a game. This demonstrates random number generation.

## References

* [Basic Computer Games](http://vintage-basic.net/games.html) by David Ahl
* [McCracken, Harry. “Fifty Years of BASIC, the Programming Language That Made Computers Personal.” TIME, 29 Apr. 2014, https://time.com/69316/basic/.](https://time.com/69316/basic/)
* [Birth of Basic. Directed by Mike Murray and Dan Rockmore, Dartmouth](https://www.youtube.com/watch?v=WYPNjSoDrqw)
* [People’s Computer Company. What to Do After You Hit Return (1975). 1975. Internet Archive, http://archive.org/details/Whattodoafteryouhitreturn.](https://archive.org/details/Whattodoafteryouhitreturn/mode/2up)
* [“Star Trader.” Wikipedia, 16 Feb. 2025. Wikipedia, https://en.wikipedia.org/w/index.php?title=Star_Trader&oldid=1275966462.](https://en.wikipedia.org/wiki/Star_Trader)
* [Porting 47 Year Old Basic code from The Oregon Trail](https://leetusman.com/nosebook/oregon-comments)
* [Explorations in TinyBasic](https://leetusman.com/nosebook/tiny-basic)

## Notes on Hamurabi in 2025: 57 years and growing

King of Sumeria or The Sumer Game was originally written by Doug Dyment in the Focal language for DEC computers in 1968. 

> The game consists of ten rounds wherein the player, as the ancient Babylonian king Hammurabi, manages how much of their grain to spend on crops for the next round, feeding their people, and purchasing additional land, while dealing with random variations in crop yields and plagues. The Sumer Game was inspired by The Sumerian Game, a much more in-depth text-based economic simulation intended for children, developed from 1964 to 1966 by designer and elementary school teacher Mabel Addis and IBM programmer William McKay. 

Around 1971 David Ahl ported the game to DEC BASIC, and then published it in his classic type-in program book 101 BASIC COMPUTER GAMES in 1973 and in expanded form in Microsoft BASIC in 1978 for BASIC Computer Games.

## Translating Hamurabi between BASIC implementations

I was able to translate Hamurabi from its original code in BASIC Computer Games to Yabasic with only minor changes needed. 

These were:

* I added more spacing for better formatting in the print around variables in PRINT lines with concatenation, and changed all semicolon separators to commas.
* Any line with a conditional and implied goto jump needed an explicit `GOTO` and `ENDIF` functions added. For example: `if L<7 THEN 565' needed to be changed to `IF L<7 THEN GOTO 565 ENDIF` in Yabasic.
* `RND(1)` is translated to `ran()` in Yabasic.
* After some tests with various BASIC emulators I believe `PRINT CHR$(7)` produces a bell sound, so I translated line 990 to `bell` in Yabasic, however I couldn't get this to produce sound on my computer.

