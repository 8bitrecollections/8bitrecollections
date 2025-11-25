# 8 Bit Recollections
## Contact Information
If you want to reach out to me, my email address is 8bitrecollections@gmail.com.  No source code can be released yet.  I promise it's still not ready to consumption and testing.

## Current Update
2025-11-25: New database elements are loading into the GUI.  Looking at ways to index them for reference within the software so database reads will not be needed.  Adding a settings tab and database to house platform specific attributes.  Such as basic_feature_multiple_statements, basic_feature_multiple_statements_separator, basic_maximum_line_length.  This will allow the build code to understand how to optimize for target platform.  Vic20 holds 88 characters per line, C64 holds 80 characters per line.  TI 99 4/A does not support a colon between multiple commands.

## History And Design Goals
One of my first computers was a Commodore Vic 20 and later I owned a Commodore 64.  These systems launched my interest in computers and solidifed my IT career path.  For the last 10 years or so I found myself thinking of these old systems and wanting to develop games.  I wrote a few simple games in my teens and enjoyed tinkering and the technical challenges of these platforms.  Likewise, in my professional career I have always advocated for cross platform solutions.  As much as possible, one should write once and then deploy to all platforms.  This is accomplished by keeping the game design elements away from the low level hardware. I also know there are people out there with great games in their heads that do not and should not have to understand the hardware.  I cannot wait to see what they can design.

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

## Design Tool
This custom design tool allows for the building of games including graphic elements and 'rules'.  This is very much a work in progress and now that I have all 3 days exporting to BASIC, I will spend more time cleaning up the internals and UI.  Here is the current status:

![alt text](https://github.com/8bitrecollections/8bitrecollections/blob/main/screenshots/ui_design_tool.png "Title")

## Hello World Exports
The design tool has 3 games that load into the database and I will be completing all 3 so that they work as expected.  Game play will obviously require 100% machine language.

Commodore 64 games will work in base memory.  Vic 20 requires 16K expansion.  I really wanted the Vic20 to work with default memory, but it's just not enough to build a nice looking game in this manner.  It's easy enough to give it more memory in VICE and 16K cartridges are readily available on eBay.  It's my plan to allow this tool to build pure Petsci games and export identically, possibly this could fit into the base Vic.  It will be fun to try!

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
##### Splash Page
![alt text](https://github.com/8bitrecollections/8bitrecollections/blob/main/screenshots/comdr64_project0002_splash0001.png "Title")
##### Game Play
![alt text](https://github.com/8bitrecollections/8bitrecollections/blob/main/screenshots/comdr64_project0002_layout0001.png "Title")

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
