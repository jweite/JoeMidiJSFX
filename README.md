# JoeMidiJSFX

This is a collection of JSFX I wrote as part of my Reaper-based live rig.

**JoeMidiProgramChangeCloner** was written to allow a single MIDI program change message (as issued by a controller keyboard) to change the presets of *all* of the FX in a Reaper FX Chain.  

The FX in a Reaper FX chain can be configured to change their preset upon receipt of a MIDI program change message, but each FX must listen on a different channel (or only the first one receives the program change).  This plugin, placed before the other FX in the chain, duplicates any program change messages it receives onto a contiguous range of other MIDI channels.

To use this as intended, the presets of all the FX in the chain must align 1:1.  The idea here is to create a preset that spans all the FX in the chain which can be picked with a single button push.  It effectively lets me extend my VSTi's with all the other FX I have.

To do so I need to create perfectly parallel preset lists in each FX.  I'll name them identically to help me keep them aligned. A preset needs to be created even if all it does is bypass the FX.  It's a pain, but it works.

**JoeMidi_multichan_filter** is a simple channel-based midi filter.  Unlike others I've seen (MidiTool...) it lets me pick a range of channels to let pass.

I have several multitimbral VSTi's in my live rig that can assign different sounds to different midi channels (ie M1 combis).  Reaper only gives me the option of all or single channel.  To use these effectively (without devoting a whole interface to them) I need to be able to set Reaper to All Midi Channels, but then filter down to a subset before my VSTi.  This JSFX allows for this.

**JoeMidi_RotaryControl** maps keypresses of the lower 2 white keys on my 88 key controller to control change messages suitable for changing the VB3's rotary simulator speed.  A = slow, B = fast.
