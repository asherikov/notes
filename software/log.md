2024-03
=======

Voice calls
-----------

### ejabberd

- `ejabberd` (<https://github.com/processone/docker-ejabberd/>,
  <https://www.process-one.net/blog/how-to-set-up-ejabberd-video-voice-calling/>)
  includes STUN/TURN functionality, but the whole stack seem to be stagnating
  and modern XMPP desktop clients lack VOIP support
  <https://xmpp.org/software/?platform=windows>.

### snikket

- <https://snikket.org/app/learn/>, no desktop client.

### mumble

- Looks good.


2024-02
=======

`make` alternatives
-------------------

- <https://github.com/casey/just>: looks interesting, but lacks `.DEFAULT`
  target.
- <https://github.com/go-task/task>: too verbose.


mpv
---

- Migrate from `mplayer` to `mpv`: no issues with OSD and flac seeking in
  FreeBSD.


nushell
-------

- https://www.nushell.sh/, looks clean, doesn't seem to be worth the migration
  effort.


fluxbox
-------

- Replace toolbar with tint2, not maintained but looks better and has decent
  battery indicator.
- `xterm` -> `alacritty`, looks and feels better:
    - does not add trailing whitespaces when selecting multiple lines;
    - supports URLs.


Wayland
-------

- Touchpad is too sensitive, needs tuning.
- Most compositors are tiled.
- `labwc` is ok, but has issues with integration of workspaces into bars
  (https://github.com/labwc/labwc/issues/881): no workspace list, names, and
  window filtering.
- `foot` terminal emulator is good, but atomatic word selection needs tuning.
  `alacritty` seems to be unstable.
- `sfwbar` is good, but does not integrate well with `labwc` as described
  above.


NixOS
-----

- Requires internet connection during installation. Cannot pickup WiFi
  connections (graphical installer).


rss2email
---------

- Replace deprecated `rawdog` by `rss2email` to fetch rss feeds, looks good.
