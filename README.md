# cowvids -- Python wrapper for gnu cowsay and figlet.

CowVids is a python wrapper for cowsay and figlet that allows
users to create "movies" in bash with cowsay cowfiles and
figlet formatting. The input is a relatively simple YaML format
that makes cow movies easy to write and read!

once you're ready to run the script use the following arguments:

'-s/--script' 	-- cowscript to produce and play

'-d/--debug'	-- debug switch for testing scripts

## Running cowvid example:

```
# Debugging a cow script
./cowvid -s path/to/script.yml -d

#Playing a cow script
./cowvid -s path/to/script.yml -d
```


# Pre-Requisites:
Packages that must be installed to use this:
  * cowsay
  * figlet


# CowScript files
a CowScript is a file that contains a YaML formatted list of scenes.

## Scenes

Each item in the list is an object with a duration, and either a character and line of dialog, or a text string and a wrap width (and optionally formatting).

### Character scenes
A character scene will invoke cowsay to print a cowfile with a line
of dialogue. 

```
example scene:
- character: "moofasa"
  line: "remember"
  duration: "1"
```

the above definition will show moofasa saying "remember" for 1 second.

### Text scenes

#### Simple text scenes:
```
- text: "this is some text on the screen"
  duration: "5"
  wrap: "10"
```

The above will show the following:

```
this is so
me text on
 the scree
n
```

for 10 seconds

#### Ascii Formatted text scenes:
```
- text: "This is some text on the screen"
  format: "big"
  wrap: "80"
  duration "2"
```

the above definition will show the text listed wrapped at 80 characters.

## Extending cowsay with more cowfiles

There are more cowfiles and an explanation of how to create more cowfiles here:
* https://github.com/paulkaefer/cowsay-files

To use these cowfiles and potentially make even more cowfiles to use checkout Paul Kaefer's github above

```
cd /usr/share/cowsay/
git clone https://github.com/paulkaefer/cowsay-files
cp cowsay-files/cows/* cows/ 
```

Also be sure the check out his guide for creating new cowfiles.

Happy Movie making
