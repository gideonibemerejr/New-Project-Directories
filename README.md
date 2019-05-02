# Organizing and Creating New Project Directories
System Requirements for v1.0: macOS only.

## Introduction
This serves as a way to add some Shell Scripts and a few aliases to create simple new project directories that contains all necessary folders for organized creativity. We will be taking in a single variable, the project title, to name each root folder we create using the script(s). The directory structure uses the following structure: 
1. Assets -- with Photos, Typography, and Inspirations as subdirectories
2. Design -- for the UI/UX files
3. Code -- for the programming files
4. Proofs -- drafts sent out for review
5. Delivered -- Final files/ Deliverables for the Client.

If you are not comfortable with the macOS command line, check out this [App](link) that does the same, but with a neat User Interface.

**Attention:** Below I use  `<>` with text in between as a place holder. You should be changing this portion of the code to whatever you want to name it be.


## Setting up your Home Directory

If you already have one set up, great! You can move straight to [New Site](#new-site-or-software-directory-script) or [New Design](#new-design-directory-script). Already have the scripts set up as well? Skip on down to [Add Alias](#add-alias) to make a command that will run your script and build your directory structure.

First you will want to set up your Home directory with a root directory to host your project(s). Try running `$ mkdir ~/<filename>` in your terminal of choice. I'm using 
<a href="https://www.hyper.is" target="_blank">Hyper</a> and 
<a href="https://ohmyz.sh" target="_blank">oh-my-zsh</a>.
```
$ mkdir ~/<filename>
```

Here we tell the computer to create a directory  `<dirname>` in the home directory using `~/.`. You will want to do this again if you are going to be making directories for both Design and Development.

Thats it for this step. Keep going!


## New Site or Software Directory Script
Next we will make our script for the new software or website project. This will be the script that the computer will run through to create the directories.

1. Make sure you are in your Home `~/`  directory by running `$ cd ~`
   
2. Once you are inside of the Home directory run:
   ```
   $ touch .newsoftware.sh && code .newsoftware.sh
   ``` 
   You can run the command for the code editor of your choice. Here I am using VS Code.
3. In your code editor insert the following code in your `.newsoftware.sh` file: 
    ```
    #! /bin/bash

    echo What is the Software project\'s name? ***REMINDER*** !No Spaces!
    
    read projectname
    
    mkdir -p ~/Dev/Software/$projectname/{01_Assets/{Photography,Inspiration,Typography},02_Design,03_Code,04_Proofs,05_Delivered/{01_Design,02_Code}}
    ```
    Lets go over what's happening here. 
    
    First we use `#! /bin/bash` to let our shell know what type of interpreter to run. Then we use `echo ...` to prompt user input with a reminder to not use spaces when creating directories in the terminal. Next, the computer will run `read projectname` that will **read** the user input and cache (save) it in a variable called **projectname**. 
    
    Last, we run `mkdir` using curly brackets `{}` to create multiple subdirectories at any given level. Here the variable `$projectname` is being used to create a directory and subdirectories in my `~/Dev/Software` directory

    Once created the directory tree will look like this:
   ```
   ├── 01_Assets
   │   ├── Inspiration
   │   ├── Photography
   │   └── Typography
   ├── 02_Design
   ├── 03_Code
   ├── 04_Proofs
   └── 05_Delivered
   ```
4. Next you'll need to save the file and change some preferences to allow terminal access. For this you will need to open a Finder window. 
5. Navigate to your Home directory and press Command + Shift + . (Period or full stop). to see the hidden files. (When we saved the .newsoftware.sh file the "." in front createse a hidden file)
6. Once you see the file, right click or Control + Click and select "Get Info"
7. At the very bottom of the window that opens look for the following: 
   
    <img style="padding: 20px;" src="https://imgur.com/zF3XjHc.png" width="400">
8. Click the lock icon. If you have a password on your computer it will ask you to enter it in order to unlock the permissions, otherwise it will just unlock.
9. Once unlocked, go back to your terminal and run `$ chmod 700 ~/.newsoftware.sh`
10. This will change the file into an executable file.
11. In your terminal you can now run `$ ./.newsoftware.sh`. You should be prompted to enter a project name.

Next you can [Add an Alias](#add-alias) to create a command to quickly initilize this script each time you want to create a new project directory structure.


## New Design Directory Script

```
├── 01_Assets
│   ├── Inspiration
│   ├── Photography
│   └── Typography
├── 02_Design
├── 03_Proofs
└── 04_Delivered
```

## Add Alias 
```
alias newsoftware="~/.newsite.sh"
alias newdesign="~/.newdesign.sh"
```

https://www.youtube.com/watch?v=GcZOaEivf_c