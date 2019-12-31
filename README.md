# slackbuilds
My personnal SlackBuilds and queues


## CLERK

Clerk is a command-line friendly MPD client using rofi or fzf

### Features:
Play random album/tracks
Add/Replace albums/songs
Filter lists by rating
Customizable hotkeys
Rofi and fzf interfaces
Optional tmux interface for fzf mode
Rate albums/tracks
Optionally store ratings in file tags

### Dependencies:
rofi (https://github.com/DaveDavenport/rofi)
fzf
tmux
perl-net-mpd
perl-data-messagepack
perl-data-section-simple
perl-file-slurper
perl-Config-Simple
perl-Try-Tiny
perl-ipc-run
perl-http-date

### Dependencies for the tagging_client:
metaflac (flac)
vorbiscomment (vorbis-tools)
mid3v2 (mutagen)

## To build the clerk package with sbopkg

### Clone SBo-git repo and add to your local repo :
- perl-data-messagepack
- perl-data-section-simple
- perl-file-slurper
- perl-http-tiny
- perl-inc-module-install
- perl-local-lib
- perl-net-mpd

### Build usefull queue files :
sqg -p avahi musepack-tools ncmpcpp rofi fzf perl-JSON-XS perl-file-slurper perl-data-messagepack perl-net-mpd

### Prerequisites :

Beware, in the queue, for avahi and google-go-lang :
- avahi : create avahi user and group before building
`# groupadd -g 214 avahi
# useradd -u 214 -g 214 -c Avahi -d /dev/null -s /bin/false avahi`
- google-go-lang : after the build put it in the path otherwise fzf will fail to build
`# export PATH=$PATH:"/usr/share/gocode"
# export GOPATH="$HOME"`




ZZIPLIB is activated in MPD and in the queue

ncmpcpp is in the queue even if optional for the real benefit of clerk

PYTHON3 is at yes when possible

The queue file is intended to bring the more options given. You'd better build the entire queue files
since they are called from each others.

Load clerk_full queue file
