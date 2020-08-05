# st - simple terminal
st is a simple terminal emulator for X which sucks less.

This fork is a maintained version of st intended for use in my
[dotfiles](https://github.com/bossley9/dotfiles). You can view the source
hosted [by suckless on their servers](https://git.suckless.org/st).

## Table of Contents
1. [Installation](#installation)
2. [Running](#running)
3. [Configuration](#configuration)
4. [Patches](#patches)

## Installation <a name="installation"></a>
In order to build dwm you need the Xlib header files.

This fork also makes use of the `envsubst` package to insert system environment variables
into the configuation. The template file named is `template.config.h` for visibility. If you 
are unable to use this package, or do not intend on using this build of dwm with my 
dotfiles, I have also included the compiled version of my header configuration as `config.h`.

Building with `envsubst`:

    envsubst < template.config.h > config.h
    sudo make clean install

Building without `envsubst`:

    sudo make clean install

## Running <a name="running"></a>
If you did not install st with make clean install, you must compile
the st terminfo entry with the following command:

    tic -sx st.info

See the man page for additional details.

## Configuration <a name="configuration"></a>
The configuration of st is done by creating a custom config.h
and (re)compiling the source code.

For more information on configuration, Suckless tools, and how st works, 
read [the readme](https://git.suckless.org/st/file/README.html).

## Patches <a name="patches"></a>
To apply patches to suckless tools, download patches from the suckless website (or make your
own) and run the following command, making sure to specify the file being changed as 
`template.config.h` instead of the standard `config.def.h`.
```
patch --merge -i patchName.diff
```

Below is a list of popular patches I have included in my st build.

- [alpha 0.8.2](https://st.suckless.org/patches/alpha)
