# MyIP

A small GUI app built with Rye-fyne that opens a window, shows your external IP address (via [ifconfig.me](https://ifconfig.me)) and offers a button to copy it to the clipboard. The IP refreshes automatically every minute.

## Project Local Rye

To build local Rye with Fyne GUI libraries, you need to define `RYE_HOME` and `RYE_FYNE_HOME` env variables. It helps if you add the base Rye executable or `rye/bin/` folder to your path. In `rye/bin` folder is a main `rye` binary and `l.rye` script, which we will be using.

```bash
export RYE_HOME=/path/to/rye
export RYE_FYNE_HOME=/path/to/rye-fyne
export PATH=$PATH:/path/to/rye/bin
```

Then enter the `my-rye-utils/myip` folder.

### Build a local Rye with flags defined in lrye.mod

```bash
l.rye build-fyne
```

This will give you a `lrye` binary in this directory:

```bash
./lrye   # a Rye with Fyne GUI support
```

You can then run local scripts:

```bash
./lrye main.rye
./lrye .          # runs main.rye
```

In `rye/bin` folder (which you added to the path) there is also an `lrye` script that lets you run this local Rye binary without `./`:

```bash
lrye .
```

## Building a Single Binary

To build a standalone binary out of `main.rye` (with the script embedded):

```bash
l.rye build-fyne embed_main
```

You will get a `./main` binary that already includes `main.rye`. You can move `./main` to another location (without `main.rye`) and it will work.
