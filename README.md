These are code and resources I am using to try out the "10 PRINT" Commodore-64
program using assembly language.  Also known as "threadbare".  See the book,
http://10print.org/

Everything I add is public domain.  Licenses of all the other stuff confuses me.

I am too new to all of this to write detailed instructions, but this is a rough
outline of how to get it to work:

# Install VICE

Install VICE on ubuntu. http://www.viceteam.org/
Sorry, I can't remember exactly how I did it.  It's not quite straight-forward,
due to licensing issues, I think.
After installing VICE, you can run C64 emulator with command line

    x64

You can run a compiled assembly program, such as threadbare.prg by:

    x64 threadbare.prg

# INSTALL ACME crossassembler
This, too, is not straightforward for a novice like me.  Basically, unzip,
put stuff in correct locations, and create environment variable, as described
on their site: http://www.esw-heim.tu-clausthal.de/~marco/smorbrod/acme/

# Use text editor to create a .a assembly language file for acme to compile

The first program I used was from stackexchange and actually worked and gave me
some useful info on how to adapt 10 PRINT for the compiler.  That border
flashing program can be found here:
http://stackoverflow.com/a/8266211/868718

To compile the program:

    acme flash.a  # or whatever you name the program.
    
The assembly program tells the compiler to create the file keycomp.prg

# Run the .prg file
You can run a .prg file with vice command line:

    x64 keycomp.prg
    
The keycomp.prg runs by itself.  If you want to run the "10 print" or 
"threadbare" program, you need to:

    acme 10print.a
    x64 10print.prg
    
Then, at the READY prompt, type

SYS 4096
