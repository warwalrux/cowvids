# cowvids -- Python wrapper for gnu cowsay.
the python script cowshow takes one argument: '-s/--script'.

## script files
a cow script is a file that contains a YaML formatted list of scenes.

## scenes

each item in the list is an object with a duration, and either a character and line of dialog, or a text string.

### character scenes
A character scene will invoke cowsay to print a cowfile with a line
of dialogue. 

example scene:
- character: "moofasa"
  line: "remember"
  duration: "1"

the above definition will show moofasa saying "remember" for 1 second.

### text scenes

- text: "this is some text on the screen"
  duration: "1"

the above definition will show the text listed wrapped at 80 characters.

## Extending cowsay with more cowfiles

There are more cowfiles and an explanation of how to create more cowfiles here:
* https://github.com/paulkaefer/cowsay-files

