##Installation Instructions

###Command Line Tools

Uncompress the distribution files into a directory, say *amzi*.  That will create an *apls* sub directory.  For example:

```
amzi
  apls
    bin
    abin
    eclipse_plugin
    . . .
```

The listener is in the bin directory, called *alis(.exe)*.  You can run it from there.

Alternatively, to use the command line tools, you might want to create an environment variable:

AMZI_DIR that points to the *apls* directory of the installation.  (Don’t point it elsewhere, some internal functions use it if it’s defined and expect it to point to the *apls* directory.)

And put the AMZI_DIR/bin directory on the PATH.

###IDE

If you created an *amzi* directory, as above, then create an *amzi/ide* directory, and in it download and install a copy of Eclipse, such as the one for Java development.

Use the Eclipse tools to add a plug-in, picking the one from the *apls/eclipse_plugin* directory.

NOTE that it is important, especially on a Unix environments, that the relative position of the directories be as follows.  This is how the Eclipse plugin finds Amzi! if it can’t access an AMZI_DIR environment variable.  (Which is often can’t, for example, on the Mac.)

```
amzi
  ide
    eclipse(.app/.exe)
  apls
    bin
    . . .
```
If you are using an existing copy of Eclipse on your machine, then you should move the *apls* directory next to it in the same relative position as above.




