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

> command line tools give you superpowers (even if you're "not a programmer")

--

#youtube-dl

##download youtube videos!

> `youtube-dl 'https://www.youtube.com/watch?v=PFGa1JeTI8A'`

###pro-tips

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

--

#ffmpeg/libav-tools

##video manipulation tools

libav is a fork of ffmpeg.
use whichever one your package manager has.

###key features

* video compression
* trim videos
* convert between many many file types

--

#sox

##audio file manipulation tool

###key features

* rec
* trim, repeat, combine audio
* man page has fun examples: search 'chime'
* works on .wav, not .mp3 (but mplayer does mp3 to wav)

--

#gifsicle

##make your own gifs

###key features

* combine multiple images into a gif
* specify order, speed, size, and more
* "explode" gifs into constituent frames

--

#flite and espeak

##text to speech

both are on apt and both take input from standard in

> `echo hello | flite`

> `echo hello | espeak`

--

#chain programs with pipes

> **examples will be inserted here**

[](eg: avconv input.mkv | 
eg: youtube-dl 'https://www.youtube.com/watch?v=PFGa1JeTI8A'
| avconv -i pipe:0 pipe:1 | )

--

#search strategy

##looking for small command line tools vs large gui programs

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
