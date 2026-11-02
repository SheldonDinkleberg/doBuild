# doBuild
I don't really like cmake. I don't have anything against it, but it feels like overkill when my projects rarely grow to more than half a dozen files.
To solve this "issue", I wrote this little bash script, which I've been using on my linux machine for the last year or so.
As with many "self made quality of life" programming projects, I've added functionality over time so some of the code may form "sedimentary layers" as I learned more and more about bash throughout.

I should specify that this script has been written on Linux, so it might take some tweaking to get running on windows or mac.

If you have any issues with it, please feel free to leave a comment on this here webzone or send me an email: sheldondinkleberg@zohomail.com

I hope y'all find as much use from it as I've gotten!

## Usage
Once downloaded, create a project directory and place the script inside. doBuild can be executed with the "--setup" flag to create all necessary sub directories as well as the all important "buildList.txt" file. 

After setup is complete, place source files in the SRC folder, then add each of them (in the order which you want them to compile) to buildList.txt. Once you invoke doBuild (either with ./doBuild, or by placing the bash script into a directory on your $PATH), the program will be compiled with the output place in the BIN folder.

What I've done on my system is link the file to a directory on my shell's $PATH. This has two benefits:
#1: I can execute the program without it having to be in each project directory
#2: As I update the script with new functionality and fix things I don't have to remember to replace it in each project
#3: I save milliseconds of my finite human life by typing "doBuild" instead of "./doBuild"

## Helpful diddles
If you have a desired executable output name, you can either use the -o flag OR place the name behind a "@" symbol (by default) in your buildlist.txt. For example @reallyCoolProgram being in your buildList will name the resulting executable "reallyCoolProgram".
It's doesn't even have to be the first line of the buildList.txt... so that's fun!

You can also add anything (such as project specific linkers or GCC flags) to buildList.txt on a line which starts with an octothorpe (#). Everything following the octothorpe will be added to the final GCC execution, so if you'd like to link raylib you can simply include "#-raylib" in your buildList.txt

Because the math linker is a pretty common parameter, it gets a special flag: "-lm" will include the required flag in the final GCC execution.

If for some reason you also want to delete all the resulting object files (.o) you can use the -c flag to clean those up after  compilation is complete!
