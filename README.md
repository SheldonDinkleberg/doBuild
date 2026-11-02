# doBuild
I don't really like cmake. I don't have anything against it, but it feels like overkill when my projects rarely grow to more than half a dozen files.
To solve this "issue", I wrote this little bash script, which I've been using on my linux machine for the last year or so.
As with many "self made quality of life" programming projects, I've added functionality over time so some of the code may form "sedimentary layers" as I learned more and more about bash throughout.

If you have any issues with it, please feel free to leave a comment on this here webzone or send me an email: sheldondinkleberg@zohomail.com

I hope y'all find as much use from it as I've gotten!

## Usage
Once downloaded, create a project directory and place the script inside. doBuild can be executed with the "--setup" flag to create all necessary sub directories as well as the all important "buildList.txt" file. 

After setup is complete, place source files in the SRC folder, then add each of them (in the order which you want them to compile) to buildList.txt. Once you invoke doBuild (either with ./doBuild, or by placing the bash script into a directory on your $PATH), the program will be compiled with the output place in the BIN folder.

