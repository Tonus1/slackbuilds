# My slackbuilds script
My personnal SlackBuilds and queues

## CLERK

Clerk is a command-line friendly MPD client using rofi or fzf.

I use it with ncmpcpp and tagging habilities. 

#### Features:
Play random album/tracks
Add/Replace albums/songs
Filter lists by rating
Customizable hotkeys
Rofi and fzf interfaces
Optional tmux interface for fzf mode
Rate albums/tracks
Optionally store ratings in file tags

#### Dependencies:
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

#### Dependencies for the tagging_client:
metaflac (flac)
vorbiscomment (vorbis-tools)
mid3v2 (mutagen)

### To build the clerk package with sbopkg

Notice that we will build ncmpcpp, mpd, rofi, fzf and mutagen. This presents the queue I use with the (perl modules) packages needed.

#### Clone SBo-git repo and add to your local repo :
- perl-data-messagepack
- perl-data-section-simple
- perl-file-slurper
- perl-http-tiny
- perl-inc-module-install
- perl-local-lib
- perl-net-mpd

#### Build usefull queue files :
`# sqg -p avahi musepack-tools ncmpcpp rofi fzf perl-JSON-XS perl-file-slurper perl-data-messagepack perl-net-mpd`

#### Prepare the build :

Beware, in the queue, for avahi and google-go-lang :
- avahi : create avahi user and group before building

`# groupadd -g 214 avahi`

`# useradd -u 214 -g 214 -c Avahi -d /dev/null -s /bin/false avahi`

- google-go-lang : after the build put it in the path otherwise fzf will fail to build

`# export PATH=$PATH:"/usr/share/gocode"`

`# export GOPATH="$HOME"`

#### Build options :

- ZZIPLIB is activated in MPD and in the queue
- PYTHON3 is at yes when possible
- The queue file is intended to bring the more options given. Most optional packages are present.
- The "clerk_full.sqf" queue is a concatenated version of the "--CLERK--.sqf"

#### Load clerk_full queue file
`# sbopkg -i clerk_full`

Please note I still have to finish the clerk.Slackbuild : just clone it's repo, add to path and launch

`clerk.pl -f`

