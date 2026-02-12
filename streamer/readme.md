# Streamer

Using mpv to stream and play music. Demo for standalone binaries and lrye, because mpv is not included in Rye by default.

## Project Local Rye

To build local Rye with added mpv player libraries, you need to define `RYE_HOME` env variable. It helps if you add the base Rye executable or `rye/bin/` folder to your path. In `rye/bin` folder is a `l.rye` script which we will be using.

```bash
export RYE_HOME=/path/to/rye
export PATH=$PATH:/home/jimez/Work/rye/bin
```

Then enter the `my-rye-utils/streamer` folder.

### Build a local Rye with flags defined in lrye.mod

```bash
l.rye build
```

This will give you a `lrye` binary in this directory:

```bash
./lrye   # a normal rye with specific flags, in this case also mpv library
```

```rye
x> lcp\ "mpv"
```

You can then run local scripts:

```bash
./lrye simple.rye
./lrye better.rye
./lrye .          # runs main.rye
```

In `rye/bin` folder (which you added to the path) there is also an `lrye` script that lets you run this local Rye binary without `./`:

```bash
lrye .
```

## Building a Single Binary

To build a binary out of `main.rye` (with embedding it):

```bash
l.rye build embed_main
```

You will get a `./main` binary that will already run `main.rye`. You can move `./main` to another location (without `main.rye`) and it will work.
