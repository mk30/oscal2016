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

##suite of powerful image manipulation tools

###key features

* `convert` - convert one file type to another; does not overwrite
* `resize` - resize one or many files based on a variety of options
* `identify` - dimensions of an image
* batch operations
* effects: rotate, implode, etc.

huge variety of options. explore documentation for more info
than you'd ever want.

[](add example construction here)

--

#ffmpeg/libav-tools

##video manipulation tools

libav is a fork of ffmpeg.
use whichever one your package manager has.

###key features

* video compression
* trim videos
* convert between many many file types

[](add example construction here)

--

#sox

##audio file manipulation tool

###key features

* rec
* trim, repeat, combine audio
* man page has fun examples: search 'chime'
* works on .wav, not .mp3 (but mplayer does mp3 to wav)

[](add example construction here)

--

#byzanz

##record your desktop to a gif

* available on apt (check your distro)
* default recording length is 10 sec. can change with **-d**
* takes over your prompt, so run it in bg

![](testcrop.gif)

[](fix gif - currently too big)

--

#gifsicle

##make your own gifs

* combine multiple images into a gif
* specify order, speed, size, and more
* "explode" gifs into constituent frames

![](test2crop.gif)

[](gif is too big)
[](maybe put in bird example?)

--


#flite and espeak

##text to speech

both are on apt and both take input from standard in

> `echo hello | flite`

> `echo hello | espeak`

--

#chain programs with pipes

git log | grep ^Author: | sed -r 's/^Author: //; s/ <[^>]+>//' | sort | uniq -c | sort -nr

use:
/home/marina/dev/cyberwizard/site/cyberwizardinstitute.github.io

[](eg: avconv input.mkv | 
eg: youtube-dl 'https://www.youtube.com/watch?v=PFGa1JeTI8A'
| avconv -i pipe:0 pipe:1 | )

--

#scripts

##"wait a minute, i bet i can script this"

computers are good & fast at some kinds of work 

scripts can be inline or saved in files

###examples

> moving photos to website server
[](insert actual script here)

> automating your duck feeder

> organizing photos

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

> web-torrent

> torrent-mount

> airpaste

> tslide

[](add sample constructions for the above. add airpaste
recipient code)

--

###to conclude:
command line tools are powerful, but addiction is possible.
it's turtles all the way down.

##![](xkcd.png)

--

#further learning 

* inspiration for this talk: http://www.pgbovine.net/scripting.htm 
* https://www.linux.com/learn/how-resize-rename-sort-and-proof-photos-command-line 
* installing node & npm
    * specific to ubuntu: https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server
    * pro-tip for ubuntu: https://www.digitalocean.com/community/questions/ubuntu-repo-nodejs-require-symlink-to-node-to-use-forever
    * pro-tip for all npm users: https://docs.npmjs.com/getting-started/fixing-npm-permissions

--

#further learning: unix and bash
   

###intro to unix & bash
* video: https://www.youtube.com/watch?v=BhPRiSLmxis&feature=youtu.be&t=4m30s
* video notes: https://github.com/cyberwizardinstitute/workshops/blob/master/unix.markdown

###_the linux command line_ by william shotts
* full text: http://linuxcommand.org/tlcl.php
* chapter on scripts: http://linuxcommand.org/lc3_writing_shell_scripts.php
