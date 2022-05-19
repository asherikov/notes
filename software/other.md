Get links from an html file
===========================
    lynx -dump -listonly "<file>" | grep '<mask>' | awk '{print $2}' | sort | uniq > list
    lynx -dump -listonly "<file>" | grep '<mask>' | cut -f 3- -d ' ' | sort | uniq > list



Recursive downloading
=====================
    wget -w 1 -e robots=off -r -c -nH -d --no-parent --restrict-file-names=nocontrol -A <extensions> --reject-regex <mask> <url>



Ignore mismatching keys when connecting with ssh
================================================
    -o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=no



SSH per host configuration
==========================
    IdentitiesOnly yes  # do not send all identities
    Host something.com
        IdentityFile ~/.ssh/id_rsa
        Port 5399
    Host other-github
        Hostname=github.com
        IdentityFile=~/.ssh/other_id_rsa



Remote X server
===============
On the client:
    export DISPLAY=10.10.10.1:0

On the server:
    xhost +inet:10.10.10.2



HDMI output in X
================
    xrandr --output HDMI3 --auto --right-of LVDS1
    xrandr --output HDMI3 --off



Man to text
===========
    man ls | col -b



RSS feeds from youtube (works after removal of the old API, 05.2015)
====================================================================
    youtube.com/feeds/videos.xml?user=xxxxxx
    youtube.com/feeds/videos.xml?channel_id=xxxxxx

    see http://stackoverflow.com/questions/29752447/how-to-get-a-youtube-channel-rss-feed-after-2015-april-20-without-v3-api



Prevent creation of 'fontconfig' folder in the home directory
=============================================================
    http://forums.debian.net/viewtopic.php?t=87548

    edit <cachedir> parameter in /usr/local/etc/fonts/fonts.conf (/etc/fonts/fonts.conf)
