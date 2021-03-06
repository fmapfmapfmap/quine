Quine
=====

This is just me waxing nostalgic and throwing together some code for playing with graphics.

I reserve the right to get bored and go do something else that actually makes money.

A couple of shader toys:

```
$ toy -F shaders/examples/generators.frag
```

![screenshot of generators](https://raw.githubusercontent.com/wiki/ekmett/quine/generators.png)

```
$ toy -F shaders/examples/dodecahedron.frag
```

![screenshot of a dodecahedron](https://raw.githubusercontent.com/wiki/ekmett/quine/dodecahedron.png)

```
$ toy -F shaders/examples/chains.frag
```

![screenshot of chains](https://raw.githubusercontent.com/wiki/ekmett/quine/chains.png)


Now I need to make things fast.

Usage Instructions
==================

You can start up the process with just

```
$ toy
```

Resolution Settings
-------------------

Full-screen can be accessed on a mac with `Cmd-Enter`, or you can start there with `-f`

```
$ toy -f
```

Due to a bug in SDL 2.0.3 on OSX when rendering through Cocoa, this currently has to use the "fullscreen via desktop" method
otherwise I can't let you return to the desktop.

If you want to use native fullscreen then you can get coarser resolutions that run much faster (due to the lack of upsampling) with

```
$ toy -f -n -x 1024 -y 768
```

Retina rendering supported via `-r`, but figuring out the device scaling factor is currently not, I'll guess 2.0 as it is the default, but
you can play with the ratio with `-s`.

```
$ toy -r -s 2.0
```

Mac "Deferred Updates"
----------------------

On a Mac the compositior carefully helpfully batches up all the frame updates. This rather sharply caps the frame rate.

You can disable this with

```
$ sudo defaults write /Library/Preferences/com.apple.windowserver Compositor -dict deferredUpdates 0
```

but you'll probably need to restart.

To re-enable it:

```
$ sudo defaults write /Library/Preferences/com.apple.windowserver Compositor -dict deferredUpdates 1
```

Not being a Mac developer, I don't know how to do this in a less invasive manner. Suggestions are welcome.

Profiling
---------

By default `ekg` will start on port 5616, and you can connect to monitor the rendering process.

You can run `quine -M` to also have the browser pop open to the page on startup. (On a mac)

Opening the `quine.frame` chart will give you a handy FPS meter (which is now also in the title for the window).


Contact Information
-------------------

Contributions and bug reports are welcome!

Please feel free to contact me through github or on the #haskell and #haskell-game IRC channels on irc.freenode.net.

Build bot spam from this project goes to #haskell-lens.

-Edward Kmett
