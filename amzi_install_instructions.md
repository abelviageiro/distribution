##Amzi! Prolog + Logic Server Installation Instructions

###Command Line Tools

Uncompress the distribution files into a directory, say *amzi*.  That will create an *apls* sub directory.  For example:

```
amzi
  apls
    bin
    abin
    . . .
```

The listener is in the bin directory, called *alis(.exe)*.  You can run it from there.

Alternatively, to use the command line tools, you might want to create an environment variable AMZI_DIR that points to the *apls* directory of the installation.  (Don’t point it elsewhere, some internal functions use it if it’s defined and expect it to point to the *apls* directory.)

And put the AMZI_DIR/bin directory on the PATH.

###IDE

Download the amzi_eclipse_plugin.

If you created an *amzi* directory, as above, then create an *amzi/ide* directory, and in it download and install a copy of Eclipse, such as the one for Java development.

Use the Eclipse tools to add the plug-in.  It’s in the help menu, under install new software.  You’ll need to point it to the directory where you unzipped the plug-in.

NOTE that it is important, especially on a Unix environments, that the relative position of the directories be as follows.  This is how the Eclipse plugin finds Amzi! if it can’t access an AMZI_DIR environment variable.  (Which it often can’t, for example, on the Mac.)

```
amzi
  ide
    eclipse(.app/.exe)
  apls
    bin
    . . .
```
If you are using an existing copy of Eclipse on your machine, then you should move the *apls* directory next to it in the same relative position as above.

MAC Users -- It's best to unzip the apls directory in the Applications/eclipse directory so that the structure looks like:
```
Applications/eclipse/ide/eclipse.app
Applications/eclipse/apls/
```

NOTE that the uninstall may not work as expected.  While, on the one hand, it works, you can uninstall, and then install a new version, on the other hand it leaves the old amzi plug-ins (5 of them) still in the Eclipse.app plugin directory, although it does remove the feature.  It also leaves them in the artifact.xml file.  ISSUE — if someone wants to work on this, that would be great.





