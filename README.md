# dys
 A program for highlighting keywords in the output of a terminal command

## Preserving colors

When using `dys` it helps to understand the following about how colors and pipes work. In a nutshell colors are special characters that are interpreted by the terminal program (I.e. the tty). Let's use the following command as an example `gcc` which will produce the following error message (Note the colors). If we write this to a file as `gcc|cat` we only get the text. 
Why does this happen? And WHO is responsible for making this happen?  Well, as it turns out there is the `isatty()` which gives a program information about where it's output ends up. So `gcc` basically checks if it is printing to a terminal and only if it detects a terminal will it output a the special color characters.



To fool a command (for instance `gcc`) into thingking that it is actually writing to a terminal and not a pipe `dys` comes with the `dysfool`. If we repeat the `gcc|cat` test but now as `dysfool gcc|cat` we get the following

Note that `dysfool` also moves the standard error to the standard output. 
