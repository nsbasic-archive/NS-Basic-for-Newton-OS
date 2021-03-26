# MacOS Resources Files Notes

In order to be able to save the MacOS resource files, which contain the information of each file, like the name of the file, the name of the application with which the file was created but also a lot of other information (those who played with ResEdit remember it). It is necessary to separate the MacOS files into two parts, one will contain the "Mac resources" information and the other the raw file. This is the only way to be able to exchange files in MacOS format (from before MacOSX) on Github without having any loss.
The method used is the one described by Mason Mark, in his Dash-Board for Newton OS archive (https://github.com/masonmark/Dash-Board-for-Newton-OS)

- To separate the resources:
In a terminal (OSX) you go to the folder containing the Mac files.
You enter the command:

``` SplitForks . ```

And that's it, 
If you list the files with the command: ls -la, you will see the resource files of your files, they all start with ._FileName.

But before you can push these files to GitHub, you have to tell GitHub not to exclude the resource files (i.e. those starting with ._*). To do this, you must create a gitignore file containing at least the following command line:

``` #Preserve the MasOS resource files
!._*
```
You can also use the .gitignore file at the root of this project as an example.

- To rebuild the files in MacOS format when you get the files from GitHub. 
Idem, you place yourself in the folder containing the files (resssources + raw files) and you enter the command : 

``` /System/Library/CoreServices/FixupResourceForks . 
```

Et voilà :-)
