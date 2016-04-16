# multiburn
CD/DVD mass production

The following Multiburn Manual was from a saved copied of the now defunct https://www.ilikejam.org/blog/multiburn/multiburn-manual.html webpage.

# Multiburn Manual

multiburn version 1.64 (C) 2004-2008 David Stark

Program to burn one data set to multiple CD/DVD burners, ejecting each written 
disc when recording has finished, and restarting the burn process when new 
writable media is inserted.

### BURN COMMANDS:
Disc image:

`multiburn <disc type> -i <image> [options] <device> [device] ...`
  
TOC/Cue file: 

`multiburn <disc type> -t <TOC file> [options] <device> [device] ...`
  
Clone disc: 

`multiburn <disc type> -c <read device> [options] <device> [device] ...`
  
Data: 
`multiburn <disc type> -d <directory or file> [options] <device> [device] ...`

Audio Directory: 

`multiburn --audiocd -a <directory> [options] <device> [device] ...`

Singe audio file: 

`multiburn --audiocd -s <audio file> [options] <device> [device] ...`


### INFORMATION COMMANDS:
Help:

`multiburn --help`

Software Check:

`multiburn --setup`

### OPTIONS:
```
--dummy : Perform all actions, but do not write to the media.
--keep : Retain the scratch directory on exit.
--eject : Eject the drives before starting the first burn.
-r <speed> : Specify the write speed (default 24x).
-o <scratch directory> : Specify a scratch directory (default ./.multiburn).
-p <post-gap> : Specify audio CD track pre-gap (default is 0).

<disc type> : One of --dvd|--audiocd|--datacd
<device> : A CD or DVD burner device which cdrecord/cdrdao understands.
           See 'man cdrecord' for details, or run 'multiburn --scan'
<image> : The image (ISO9660, usually) to be burned.
<TOC file> : The TOC or cue file to be used for audio CDs. See 'man cdrdao' for details.
<directory or file> : File or directory to burn as disc contents.
<directory> : Directory of audio files. Non audio files are skipped.
<read device> : Device to read as the image / data source.
<speed> : The burning speed, e.g. a value of 12 will burn at 12x CD playing speed.
<scratch directory> : The temp directory used by multiburn. Default is ./.multiburn
<post-gap> : The length of gap between tracks on an audio CD.
             Format is mm:ss:ff (min:sec:frames). Default is no gap
```
**NB: Do Ctrl-C to terminate when recording is finished.**

MPlayer 1.0pre8, or later is required if audio conversion is to be performed. Previous versions of MPlayer used a slightly different syntax to the current version, and will not work.

### Credits:

The code is mine, but the following people have been indespensable in testing releases, suggesting features, and generally getting things moving. Cheers!
- Catalin Boiangiu:  
Inspired and tested proper DVD support as well as numerous command line options to make multiburn more usable in production
- Gabriele Tassoni:  
Inspired usability changes to jmultiburn (currently unavailable due to the large change in syntax in current releases of multiburn, unfortunately)
- Jason Lyons:  
Discovered audio decoding bugs
- William Vaughn:  
Feature request and testing for cdrdao / TOC file burning
- [homey](http://www.linuxquestions.org/questions/member.php?u=77716):  
Testing of the very first revisions
- [Avian00](http://www.linuxquestions.org/questions/member.php?u=30840):  
Started the whole thing off on [this LQ thread](http://www.linuxquestions.org/questions/showthread.php?s=&threadid=209957) 
