Avatar
======

This project is simply a convenient way to build all of [AvatarJS](https://avatar-js.java.net/) - the
build process is fairly complex and tedious, and it all *could* be automated.  This process does that.  

### What It Does

 * Uses git submodules for the various interdependent projects that make up Avatar
 * Includes a setup script which
    * Makes sure the submodules are checked out and up-to-date
    * Sanity checks that the versions of Java and Python are usable
    * Makes sure testng is installed and can be found

### Prerequisites

 * You need to have the following things installed and on the path
    * NodeJS - the setup script is run using `!#/usr/bin/env node`
    * Maven (tested with 3.2.1, may work with 3.1 or 3.0) - for fetching testng - not required if version 6.8.8 is already under `~/.m2`
    * Java - must be 1.8 and contain the Nashorn Javascript engine
    * Python - Per avatar's build instructions, must be 2.7.x
    * Ant - in order to build Avatar
    * Git - in order to initialize submodules
    * the venerable unix command `which`

### Running it

Just clone this repository, cd into the directory and run `./setup`

The `setup` script takes a couple of optional arguments:

  * `-y` or `--clobber` - overwrite `$HOME/.avatar-js.properties`, which Avatar's build scripts depend on to find various projects.  If that file exists and you do not pass this argument, the script will tell you that and exit
  * `-t` or `--test` - run the tests after building (takes a while)

### Status

Definitely works on Linux, should work on Mac OS, might work on Windows if run from cygwin.

