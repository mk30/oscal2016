title: Solving Problems with Command Line Tools
author:
  name: Marina Kukso
  twitter: marinakukso
  url: http://kukso.space
controls: true

--

#Solving Problems with Command Line Tools

##Marina Kukso

--

#why?

> myth of "few good programs for linux"

> don't get caught doing computer work!

> command line tools give you superpowers (even if you're "not a programmer")

--

#youtube-dl

##download youtube videos!

> `youtube-dl 'https://www.youtube.com/watch?v=PFGa1JeTI8A'`

###tips

* get the latest version from github
* use ' ' around url
* use **-o output.mp4** to dl to a specific file name
* can dl playlists!
* if fails, will resume from failure point 

--

#where to get and how to use

package managers (apt, homebrew)

> apt-cache search *keyword*

> sudo apt-get install *program*


man pages

--

#imagemagick

* `convert` - convert one file type to another; does not overwrite

> `convert cat.png cat.jpg`

* `resize` - resize one or many files based on a variety of options

> `convert cat.png -resize 500 smallcat.png`

> `convert cat.png -resize 50% smallcat.png`

> `convert cat.png -resize x500 smallcat.png`

---

#imagemagick part 2

* `identify` - dimensions of an image

> `identify cat.png`

* batch operations
* effects: rotate, implode, etc.

huge variety of options. explore documentation for more info
than you'd ever want.

--

#ffmpeg/libav-tools

##video manipulation tools

libav is a fork of ffmpeg.
use whichever one your package manager has.

###key features

* video compression
* trim videos
* convert between many many file types

> `ffmpeg -i video.mp4 video.avi`

--

#sox

##audio file manipulation tool

rec

trim, split files, repeat, combine audio

silence: add silence, trim at silence

works on .wav, not .mp3 (but mplayer does mp3 to wav)

man page has fun examples: search 'chime'

--

#sox: examples

record to file: `rec sample.wav`

concatenate audio: `sox a.wav b.wav ab.wav`

superimpose audio: `sox -m music.wav voice.wav fullsong.wav`

record for 30sec: `rec interview.wav trim 0 30`

basic trim syntax: `sox input.wav output.wav trim <start> <duration>`

remove first ten seconds: `sox song.wav trimmedsong.wav 10`

--

#byzanz

##record your desktop to a gif

* available on apt (check your distro)
* default recording length is 10 sec. can change with **-d**
* takes over your prompt, so run it in bg

![](testcropsm.gif)

--

#gifsicle

##make your own gifs

* combine multiple images into a gif
* specify order, speed, size, and more
* "explode" gifs into constituent frames

![](test2cropsm.gif)

--

#flite and espeak

##text to speech

both are on apt and both take input from standard in

> `echo hello | flite`

> `echo hello | espeak`

--

# combine programs

download only audio from a youtube video:

`youtube-dl --extract-audio --audio-format wav 'https://www.youtube.com/watch?v=PFGa1JeTI8A'`

rename the file: `mv somelongyoutubename.wav song.wav`

cut the first 15 seconds: `sox song.wav trimmedsong.wav 15`

test whether you trimmed enough: `mplayer trimmedsong.wav`

convert to mp3: `avconv -i trimmedsong.wav trimmedsong.mp3`

--

#chain programs with pipes


###example: who makes the most commits to a repository?

git log | grep ^Author: | sed -r 's/^Author: //; s/ <[^>]+>//' | sort | uniq -c | sort -nr

--

#scripts

##"wait a minute, i bet i can script this"

computers are good & fast at some kinds of work 

scripts can be inline or saved in files

###example

> generate medium & thumbnail size photos for website

--

#search strategy

##"wait a minute, i bet there's a command line tool for this"

> "linux command line image resize" => convert

> "linux convert mkv to mp4" => avconv/ffmpeg

> "extract audio from mp4 linux" => mplayer and vlc

> "mp3 to wav linux" => avconv/ffmpeg

--

#command line tools on npm

to install and run these programs, you must install node.js and npm

###examples:

torrent-mount: `torrent-mount 'magnet:?xt=urn:btih:ba1e...'`

airpaste: share with a peer on the same network

> send a file: `airpaste < movie.avi`

> receive a file: `airpaste > movie.avi`

tslide: slideshow from markdown file

--

###to conclude:
command line tools are powerful, but addiction is possible.
it's turtles all the way down.

##![](xkcd.png)

--

#further learning 

* http://cyber.wizard.institute
* inspiration for this talk: http://www.pgbovine.net/scripting.htm 
* https://www.linux.com/learn/how-resize-rename-sort-and-proof-photos-command-line 
* https://github.com/tldr-pages/tldr/blob/master/pages/common/ffmpeg.md
* http://www.linuxandlife.com/2012/07/some-small-tricks-with-ffmpeg.html
* http://www.catswhocode.com/blog/19-ffmpeg-commands-for-all-needs
* http://www.thegeekstuff.com/2009/05/sound-exchange-sox-15-examples-to-manipulate-audio-files/
* [sox and silence](http://digitalcardboard.com/blog/2009/08/25/the-sox-of-silence/)

--

#further learning: unix and bash
   

###intro to unix & bash
* video: https://www.youtube.com/watch?v=BhPRiSLmxis&feature=youtu.be&t=4m30s
* video notes: https://github.com/cyberwizardinstitute/workshops/blob/master/unix.markdown

###_the linux command line_ by william shotts
* full text: http://linuxcommand.org/tlcl.php
* chapter on scripts: http://linuxcommand.org/lc3_writing_shell_scripts.php

--

#further learning: node and npm

* installing node & npm
    * specific to ubuntu: https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server
    * pro-tip for ubuntu: https://www.digitalocean.com/community/questions/ubuntu-repo-nodejs-require-symlink-to-node-to-use-forever
    * pro-tip for all npm users: https://docs.npmjs.com/getting-started/fixing-npm-permissions
