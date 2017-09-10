# JoeMidiJSFX

This is a collection of JSFX I wrote as part of my Reaper-based live rig.

**JoeMidiProgramChangeCloner** was written to allow a single MIDI program change message (as issued by a controller keyboard) to change the presets of *all* of the FX in a Reaper FX Chain.  

The FX in a Reaper FX chain can be configured to change their preset upon receipt of a MIDI program change message, but each FX must listen on a different channel (or only the first one receives the program change).  This plugin, placed before the other FX in the chain, duplicates any program change messages it receives onto a contiguous range of other MIDI channels.

To use this as intended, the presets of all the FX in the chain must align 1:1.  The idea here is to create a preset that spans all the FX in the chain which can be picked with a single button push.  It effectively lets me extend my VSTi's with all the other FX I have.

To do so I need to create perfectly parallel preset lists in each FX.  I'll name them identically to help me keep them aligned. A preset needs to be created even if all it does is bypass the FX.  It's a pain, but it works.
