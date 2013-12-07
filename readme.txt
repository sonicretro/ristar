DISCLAIMER:
Any and all content presented in this repository is presented for informational and educational purposes only.
Commercial usage is expressly prohibited. Sonic Retro claims no ownership of any code in these repositories.
You assume any and all responsibility for using this content responsibly. Sonic Retro claims no responsibiliy or warranty.

I started disassembling Ristar on 7 December 2009 to get the DAC samples out. Part of the process I used that time involved disassembling a lot of code; probably unnecessarily. Now I have decided to complete that disassembly process and identify critical points (decompression routines, palette loads, etc.). Now that I have enough known, I am releasing this early Ristar disassembly in hopes that interested people will expand it into a complete one. I will be happy to help when I can, but it won't be a primary project for me (at least not now).

The .idb files require IDA 5.5.

As far as I know, Ristar uses two compression formats: Nemesis and Star. We all know Nemesis compression; Star is a Ristar-specific compression first cracked and named by drx. His Win32 decompressor is at http://drx.pl/stuff/StarDec.rar. The sub8A9E_unc.bin/sub8A9E_unc.idb file are uncompressed versions of a subroutine compressed with Star (and it is the only such routine I have found so far).

Indirect jumps have comments saying DONE on them to mark that I have processed the indirect jump. For jumps to the values of registers, this may have bene premature. In the event more code is disassembled, it would be nice to keep this system so we know what's been done and what's not.

Controller input and palette loading are generally done in one go (the routine is appropriately named). The palette is usually cached inline at $FFFFEF00.

SMPS-related stuff should have an SMPS_ prefix to separate them from the main program code. If I forgot to put this on something, please add it =P

Please don't use enumerations to make variable labels; I cannot use the X key to do a crossreference list on these labels (trust me, crossreference lists are very useful for research).

There are quite a few bad offsets in the disassembly thanks to IDA assuming longwords within the memory range are offsets. Please remove them if they are wrong (this happens especially with palettes and compressed art).

Watch the TODOs, and if you're not sure of something I marked, ask me,

In any case, enjoy, and happy hacking!
Pietro Gagliardi (andlabs)
26 July 2010

Also, a butt.
