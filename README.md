# Scaffold

This README is for macOS only.

## Introduction

Scaffold adds shell scripts and a few aliases to create a set of directories for new projects. Each Scaffold flow creates directories to organize creativity. For every new project, Scaffold will use the following structure:

1. Assets -- with Photos, Typography, and Inspirations as subdirectories
2. Design -- for the UI/UX and design files
***3. Code -- for the programming files***
4. Proofs -- drafts sent out for review
5. Delivered -- final files/deliverables accepted by the client.
   - Writing `code`? The Dev flow creates two deliverables folders: `01_Design` and `02_Code` 

*Not a developer? Or not writing code this time? Utilize the Design flow. It omits the "Code" directory*

If you are not comfortable with the macOS command line, check out the [Application](https://github.com/gideonibemerejr/New-Project-Directories/blob/master/Scaffold_README.md) that does the same, but with a neat User Interface.

- **Attention:** Below, `<text>` is used as a place holder. Change this portion of the code however deemed fit. **Without the brackets.**

## Setting up a root in the Home Directory

Already set up? Great! Move straight to [New App](#new-app-directory-script) or [New Design](#new-design-directory-script). Already have the scripts set up as well? Skip down to [Add Alias](#add-alias) to make a command that will run a script and make your directory structure.

First, set up your Home directory with a root directory to host your project(s). Try running `$ mkdir ~/<dirname>` in any terminal. We use <a href="https://www.hyper.is" target="_blank">Hyper</a> and <a href="https://ohmyz.sh" target="_blank">oh-my-zsh</a>.

```
$ mkdir ~/<filename>
```

Create a directory `<dirname>` in the home directory using `~/.`. Do this once for Design and once for Development.

*Optional:* Inside the `~/Dev` directory make an additional directory called Apps. Do this by running:
`$ mkdir ~/Dev/Apps`

## New App Directory Script

Write a script that will create the new app project. This will be the script that the computer will run through to create the directories.

1. Move into the Home `~/` directory by running `$ cd ~`

2. Once inside of the Home directory run:
   ```
   $ touch .newapp.sh && code .newapp.sh
   ```
   This is the command for [VS Code](https://code.visualstudio.com/). Change to editor of choice.
   
3. Write the following code in the `.newapp.sh` file:

   ```
   #! /bin/bash

   echo What is the App project\'s name? ***REMINDER*** !No Spaces!

   read projectname

   mkdir -p ~/Dev/Apps/$projectname/{01_Assets/{Photography,Inspiration,Typography},02_Design,03_Code,04_Proofs,05_Delivered/{01_Design,02_Code}}
   ```

Lets go over what's happening here.

First, `#! /bin/bash` to lets the shell know what type of interpreter to run. Then `echo ...` prompts the user for input with a reminder to not use spaces when creating directories here. Next, the computer will run `read projectname`. This will **read** the user input and cache it in a variable called **projectname**.

Lastly, `mkdir` using curly brackets `{}` to create multiple subdirectories at any given level. Here the variable `$projectname` is being used to create a directory and subdirectories in `~/Dev/Apps`.

   The directory tree will look like this:

   ```
   ├── 01_Assets
   │   ├── Inspiration
   │   ├── Photography
   │   └── Typography
   ├── 02_Design
   ├── 03_Code
   ├── 04_Proofs
   └── 05_Delivered
       ├── 01_Design
       └── 02_Code
   ```

4. Next, save the file and change some preferences to allow terminal access. For this,  open a Finder window.
5. Navigate to the Home directory and press Command + Shift + . to see the hidden files. (When the .newapp.sh file was saved the "." in front creates it as a hidden file)
6. Right click or Control + Click the file and select "Get Info"
7. At the very bottom of the window look for the following (it may be necessary to scroll):

   <img style="padding: 20px;" src="https://imgur.com/zF3XjHc.png" width="400">

8. Click the lock icon. Got a password? Your machine will prompt you to enter it in order to unlock the permissions, otherwise it will just unlock.
9. Once unlocked, go back to the terminal and run `$ chmod 700 ~/.newapp.sh`
10. This will change the file into an executable file.
11. In the terminal run `$ ./.newapp.sh`. Voila!

Next [add an alias](#add-alias) to create a command to quickly initilize this script.

## New Design Directory Script

1. Started with the Dev flow above? This is basically the same, barring the different file names and total number of files. For users that have skipped down for the Design flow only, navigate to the Home `~/` directory by running `$ cd ~`

2. Once inside the Home directory run:
   ```
   $ touch .newdesign.sh && code .newdesign.sh
   ```
   This is the command for [VS Code](https://code.visualstudio.com/). Change to editor of choice.
   
3. Write the following code in the `.newdesign.sh` file:

   ```
   #! /bin/bash

   echo What is the Design project\'s name? ***REMINDER*** !No Spaces!

   read projectname

   mkdir -p ~/Design/$projectname/{01_Assets/{Photography,Inspiration,Typography},02_Design,03_Proofs,04_Delivered}
   ```

   
Lets go over what's happening here.

First, `#! /bin/bash` to lets the shell know what type of interpreter to run. Then `echo ...` prompts the user for input with a reminder to not use spaces when creating directories here. Next, the computer will run `read projectname`. This will **read** the user input and cache it in a variable called **projectname**.

Lastly, `mkdir` using curly brackets `{}` to create multiple subdirectories at any given level. Here the variable `$projectname` is being used to create a directory and subdirectories in `~/Design`.


   Once created the directory tree will look like this:

   ```
   ├── 01_Assets
   │   ├── Inspiration
   │   ├── Photography
   │   └── Typography
   ├── 02_Design
   ├── 03_Proofs
   └── 04_Delivered
   ```

4. Next, save the file and change some preferences to allow terminal access. For this,  open a Finder window.
5. Navigate to the Home directory and press Command + Shift + . to see the hidden files. (When the .newapp.sh file was saved the "." in front creates it as a hidden file)
6. Right click or Control + Click the file and select "Get Info"
7. At the very bottom of the window look for the following (it may be necessary to scroll):

   <img style="padding: 20px;" src="https://imgur.com/zF3XjHc.png" width="400">

8. Click the lock icon. Got a password? Your machine will prompt you to enter it in order to unlock the permissions, otherwise it will just unlock.
9. Once unlocked, go back to the terminal and run `$ chmod 700 ~/.newapp.sh`
10. This will change the file into an executable file.
11. In the terminal run `$ ./.newdesign.sh`. There should be a prompt:

    ```
    What is the Design project's name? ***REMINDER*** !No Spaces!

    ```

## Add Alias

Last step! Make a quick command to make these directories quickly when needed. Depending on the terminal there are different files to open. For the Terminal app that comes with macOS [Follow this guide](#macOS-Terminal-Setup). For oh-my-zsh users:

1. Navigate to the Home directory.
2. Inside the Home directory run:
   ```
   $ ls -a
   ```
   The `-a` flag will show the _hidden_ files.
3. Open the `.zshrc` file:  `$ code .zshrc`
4. Scroll to the bottom of the `.zshrc` file to the comments:
   ```
   # Set personal aliases, overriding those provided by oh-my-zsh libs,
   # plugins, and themes. Aliases can be placed here, though oh-my-zsh
   # users are encouraged to define aliases within the ZSH_CUSTOM folder.
   # For a full list of active aliases, run `alias`.
   #
   # Example aliases
   #
   # alias ohmyzsh="mate ~/.oh-my-zsh"
   # alias zshconfig="mate ~/.zshrc"
   ```
5. Create the following `alias` lines:
   ```
   alias newapp="~/.newapp.sh"
   alias newdesign="~/.newdesign.sh"
   ```
6. Save the file and restart the Terminal app.
7. Try and run:

   ```
   $ newapp

   ```

   or

   ```
   $ newdesign
   ```

Voila x2!

### macOS Terminal Setup

For the Terminal app, it is very similar to oh-my-zsh. Just `alias` code lines to a different file.

1. Navigate to the Home directory.
2. Inside the Home directory run:
   ```
   $ ls -a
   ```
   The `-a` flag will show the _hidden_ files. Find `.bash_profile`.
3. No `.bash_profile` file? Create one by navigating to the home directory: `$ ~/` then run:
   ```
   $ touch .bash_profile
   ```
4. Open the `.bash_profile` file in the code editor: `$ code .bash_profile`
5. Create the following `alias` lines:
   ```
   alias newapp="~/.newapp.sh"
   alias newdesign="~/.newdesign.sh"
   ```
6. Save the file and Quit the Terminal app.
7. Try and run:

   ```
   $ newapp

   ```

   or

   ```
   $ newdesign
   ```
Voila!



*Version 1.0 ESROSN® c/o Gideon Ibemere, Jr*
