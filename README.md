# znax
ZNAX: Ranked 5/36 at #CPCRetroDev 2015


# ZNAX / [Shinra](http://pulko.mandy.pagesperso-orange.fr/shinra/)

### Fifth ranked at [#CPCRetroDev 2015 Game Creation Contest](http://cpcretrodev.byterealms.com/contest-en/cpcretrodev-2015/)

This is the source code for the game ZNAX, by [Shinra](http://pulko.mandy.pagesperso-orange.fr/shinra/). 

This game was developed specifically for participating in [#CPCRetroDev 2015 Game Creation Contest](http://cpcretrodev.byterealms.com/contest-en/cpcretrodev-2015/).

We will be very happy to receive any doubt or suggestion you had. Contact us. 

## Requirements

The development was done on the Haiku operating system, but any UNIX/Linux-style system should do.

The following tools are needed:
* vasm (z80 oldstyle) and vlink
* GNU Make
* cpcfs from the [cpcsdk](https://github.com/cpcsdk) project (only for the DSK version)
* [2cdt](https://github.com/ralferoo/cpctools/tree/master/2cdt/2cdt) by Kevin thacker (only for the tape version)
* ACE emulator for the "make emu" target (but you can manually run the game in another emulator)
* exoraw from [exomizer 2](http://hem.bredband.net/magli143/exo/)
* png2crtc from [cpcsdk](https://github.com/cpcsdk)
* UNIX-compatible rm (for make clean)
* pdflatex with the memoir class package (for compiling the user manual)

## How to compile

To compile the game:

```
cd code
make
```

The default target will generate both the DSK and CDT files. The makefile automates everything and declares all the dependencies (unless I missed some), so changes to the sources will be picked
automatically. This includes changes to the PNG files, which will be automatically converted to SCR, then crunched. The only exception is the music, which needs to be recompiled to the proper target address with Arkos Tracker. There is currently no tool available to relocate Arkos Tracker songs.

The target "emu" will run the ACE emulator preset to run the game (with fast drives enabled). This is convenient to quickly test it during development. "make ../ZNAX.dsk" and "make ../ZNAX.cdt" will
do what you expect. This version of the makefile does not include any rules for sending the files to a real CPC disk or making snapshots.

To compile the manual:

```
cd man
pdflatex manual.latex
```

This will generate a PDF file for the user manual.

Note that the git history is included if you're curious how things evolved. Unfortunately I started using git for this project way later than I should have, so a lot of the history is not present and the first commit imports an already quite complete version of the game.

## Credits

* Original concept and game rules by Nick Kouvaris/Lightforce
* Code and music by Adrien Destugues ( [PulkoMandy](http://www.pouet.net/user.php?who=20122) / [Shinra](http://pulko.mandy.pagesperso-orange.fr/shinra/) )
* Graphics by Cédric Quetier ( [CeD](https://demozoo.org/sceners/29539/) / [Condense](http://norecess.cpcscene.net/) )
* Music player by Julien Névo ( [Targhan](http://www.julien-nevo.com/) / [Arkos](http://www.cpcwiki.eu/index.php/Arkos) )
* Exomizer decompression routine by [Metalbrain](https://www.msx.org/es/users/metalbrain)
