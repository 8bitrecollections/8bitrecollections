# 8 Bit Recollections
## Contact Information
If you want to reach out to me, my email address is 8bitrecollections@gmail.com.  No source code can be released yet.  I promise it's still not ready to consumption and testing.

## History And Design Goals
One of my first computers was a Commodore Vic 20 and later I owned a Commodore 64.  They launched my interest in computers and solidifed my IT career path.  For the last 10 years or so I found myself thinking of these old systems and wanting to develop games.  I wrote a few simple games in my teens and enjoyed tinkering and the technical challenges of these platforms.  Likewise, in my professional career I have always advocated for cross platform solutions.  As much as possible, write once and then deploy to all platforms.  This is accomplished by keeping the game design elements away from the low level hardware.  Build the best possible game, have a tool that exports to the desired platform(s).  I also know there are people out there with great games in their heads that do not and should not have to understand the hardware.  I cannot wait to see what they can design.

Originally I played with the idea of building games and being able to export to for example Vic 20 and C64 from the same UI elements.  This just cannot happen reliably and automatically because of the major differences in resolution and platform features.  So I settled on the concept that allows you to select 22, 32, 40 and 80 columns and build elements at that scale and export to platforms.

I did not see any see any tools that work the way I wanted to build games, so I started working on my own.  I wanted the tool itself to be cross platform as well.  Building on GTK and Python, it works on all Linux platforms and Raspberry Pi already.  It should be trivial to get it running on Mac.  Possibly that other operating system will be supported at some point as well. :)

Designing in this manner, the game developer doesn't have to worry deeply about the under the hood issues and those are handled during the export process.  I also wanted it to work this way so that as you optimize the exporting process it would be possible to rebuild all of your previous games and have them work better immediately as well.  GUI and game play sit in a database.  The export tool reads the database and creates code that just works.

## Current Status
The design tool works on Linux and Pi and is continually improving.  The tool exports in a hello world manner in BASIC which then runs on vic20 and C64.   All that is exported is enough to render the screen and show basic animation of sprites.  No actual game play is working, BASIC is way too slow.  But conceptually it's cool to see this all working.

I will release all of this open source, but right now way much is broken to attempt allowing it to be shared.  I am still tinkering greatly and refactoring the schemas and backends almost daily

## In Progress
The design tool UI is working and to me allows for a good game building experience.  Lots of bugs remain, and the UI will be cleaned up greatly.  I will be working on exporting to actual hardware instead of VICE.  I now have a working Vic20 with 16K of RAM and my original C64 connected to a tube tv.  I'm excited to see this all running on hardware.

Next up for the export process will be creating data files on disk that contains the screens, sprites and positional data to be loaded into memory.  Thereafter the actual game play rules will be developed.  Time to re-learn 6502 assembly.  I submitted a simple game in machine language to Compute! in 1982, so I know it's in my head somewhere.

## Future
I have some games in my head that I want to write on these platforms, and once the tool matures-- will do so.

I also want to support other computers and learn them.  Ti 99 4/A, Ataris -- Bring them on. 

## Hello World Exports
The design tool has 3 games that load into the database and I will be completing all 3 so that they work as expected.  Game play will obviously require 100% machine language.

Commodore 64 games will work in base memory.  Vic 20 requires 16K expansion.  I really tinkered with the stock Vic20, but using as soon as you create your own character set, memory is almost already gone. 

I am constantly tinkering with bits and improving the screens.

### Hello World
This very basic game will just run an animation loop and test edge detection and UI animation.

#### Vic 20
##### Game Play
![alt text](https://github.com/8bitrecollections/8bitrecollections/blob/main/screenshots/comdrv20_project0001_layout0001.png "Title")
#### Commodore 64
##### Game Play
![alt text](https://github.com/8bitrecollections/8bitrecollections/blob/main/screenshots/comdr64_project0001_layout0001.png "Title")
### Food Fight
One of my favorite games, as far as I know this was never ported to the Commodore platforms.  I hope to add features as the tool matures and have a working game.

#### Vic 20
##### Splash Page
![alt text](https://github.com/8bitrecollections/8bitrecollections/blob/main/screenshots/comdrv20_project0002_splash0001.png "Title")
##### Game Play
![alt text](https://github.com/8bitrecollections/8bitrecollections/blob/main/screenshots/comdrv20_project0002_layout0001.png "Title")
#### Commodore 64

### Battlestar Galactica Space Alert
This is a game patterned after the old Mattel electronics handheld game that I enjoyed when I was young.  My orginal game is still sitting right here and works.
#### Vic 20
##### Splash Page
![alt text](https://github.com/8bitrecollections/8bitrecollections/blob/main/screenshots/comdrv20_project0003_splash0001.png "Title")
##### Game Play
![alt text](https://github.com/8bitrecollections/8bitrecollections/blob/main/screenshots/comdrv20_project0003_layout0001.png "Title")

#### Commodore 64
##### Splash Page
![alt text](https://github.com/8bitrecollections/8bitrecollections/blob/main/screenshots/comdr64_project0003_splash0001.png "Title")
##### Game Play
![alt text](https://github.com/8bitrecollections/8bitrecollections/blob/main/screenshots/comdr64_project0003_layout0001.png "Title")
