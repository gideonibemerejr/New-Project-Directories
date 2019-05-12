# Scaffold

This README is for macOS only.

## Introduction

Scaffold  is a way to add some shell scripts and a few aliases to create simple new project directories through the terminal. Each Scaffold flow creates directories to organize creativity. For every new project, Scaffold will use the following structure:

1. Assets -- with Photos, Typography, and Inspirations as subdirectories
2. Design -- for the UI/UX files
*3. Code -- for the programming files*
4. Proofs -- drafts sent out for review
5. Delivered -- final files/deliverables accepted by the client.
   - Writing `code`? The Dev flow creates two deliverables folders: `01_Design` and `02_Code` 

*Not a developer? Utilize the Design flow. There will not be a "Code" directory*

If you are not comfortable with the macOS command line, check out the [Application](https://github.com/gideonibemerejr/New-Project-Directories/blob/master/Scaffold_README.md) that does the same, but with a neat User Interface.

- **Attention:** Below, `<text>` is used as a place holder. Change this portion of the code however deemed fit. **Without the brackets.**

## Setting up a <root> in the Home Directory

If you already have one set up, great! You can move straight to [New App](#new-app-directory-script) or [New Design](#new-design-directory-script). Already have the scripts set up as well? Skip down to [Add Alias](#add-alias) to make a command that will run your script and make your directory structure.

First you will want to set up your Home directory with a root directory to host your project(s). Try running `$ mkdir ~/<dirname>` in your terminal of choice. I'm using <a href="https://www.hyper.is" target="_blank">Hyper</a> and <a href="https://ohmyz.sh" target="_blank">oh-my-zsh</a>.



```
$ mkdir ~/<filename>
```

Here we tell the computer to create a directory `<dirname>` in the home directory using `~/.`. You will want to do this again if you are going to be making directories for both Design and Development.

Inside the `~/Dev` directory I made an additional directory called Apps. You can do so by running:
`$ mkdir ~/Dev/Apps`

## New App Directory Script

Next we will make our script for the new app project. This will be the script that the computer will run through to create the directories.

1. Make sure you are in your Home `~/` directory by running `$ cd ~`

2. Once you are inside of the Home directory run:
   ```
   $ touch .newapp.sh && code .newapp.sh
   ```
   You can run the command for the code editor of your choice. Here I am using VS Code.
3. In your code editor insert the following code in your `.newapp.sh` file:

   ```
   #! /bin/bash

   echo What is the App project\'s name? ***REMINDER*** !No Spaces!

   read projectname

   mkdir -p ~/Dev/App/$projectname/{01_Assets/{Photography,Inspiration,Typography},02_Design,03_Code,04_Proofs,05_Delivered/{01_Design,02_Code}}
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

1. If you started with the App structure above, this will be the same. We're just changing a few names. If not, make sure you are in your Home `~/` directory by running `$ cd ~`

2. Once you are inside of the Home directory run:
   ```
   $ touch .newdesign.sh && code .newdesign.sh
   ```
   You can run the command for the code editor of your choice. Here I am using VS Code.
3. In your code editor insert the following code in your `.newdesign.sh` file:

   ```
   #! /bin/bash

   echo What is the Design project\'s name? ***REMINDER*** !No Spaces!

   read projectname

   mkdir -p ~/Design/$projectname/{01_Assets/{Photography,Inspiration,Typography},02_Design,03_Proofs,04_Delivered/{01_Design,02_Code}}
   ```

   Lets go over what's happening here.

   First we use `#! /bin/bash` to let our shell know what type of interpreter to run. Then we use `echo ...` to prompt user input with a reminder to not use spaces when creating directories in the terminal. Next, the computer will run `read projectname` that will **read** the user input and cache (save) it in a variable called **projectname**.

   Last, we run `mkdir` using curly brackets `{}` to create multiple subdirectories at any given level. Inside my `~/Design` directory the variable `$projectname` is being used to create a directory based on the value I cached (saved) earlier.

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

4. Next you'll need to save the file and change some preferences to allow terminal access. For this you will need to open a Finder window.
5. Navigate to your Home directory and press Command + Shift + . (Period or full stop). to see the hidden files. (When we saved the .newsoftware.sh file the "." in front createse a hidden file)
6. Once you see the file, right click or Control + Click and select "Get Info"
7. At the very bottom of the window that opens look for the following:

   <img style="padding: 20px;" src="https://imgur.com/zF3XjHc.png" width="400">

8. Click the lock icon. If you have a password on your computer it will ask you to enter it in order to unlock the permissions, otherwise it will just unlock.
9. Once unlocked, go back to your terminal and run `$ chmod 700 ~/.newdesign.sh`
10. This will change the file into an executable file.
11. In your terminal you can now run `$ ./.newdesign.sh`. You should be prompted with the message:

    ```
    What is the Design project's name? ***REMINDER*** !No Spaces!

    ```

## Add Alias

Last step! We need to make a quick command type so we can make these directories quickly. Depending on your terminal, you may have to open different files. For the Terminal app that comes with macOS [Follow this guide](#macOS-Terminal-Setup). For oh-my-zsh users, here we go.

1. Make sure you are inside the Home directory.
2. Once you are inside of the Home directory run:
   ```
   $ ls -a
   ```
   The `-a` flag will show you all the _hidden_ files. We're looking for `.zshrc`.
3. Now you will need to open the `.zshrc` file in your code editor. For me it was `$ code .zshrc`
4. Scroll to the bottom of the `.zshrc` file and you should see comments like this describing your "alias" area:
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
6. Save the file and Quit your terminal app.
7. Try and run:

   ```
   $ newapp

   ```

   or

   ```
   $ newdesign
   ```

You should be prompted with the message from earlier.

### macOS Terminal Setup

For the Terminal app, it is very similar to oh-my-zsh. We are just adding `alias` code lines to a different file.

1. Make sure you are inside the Home directory.
2. Once you are inside of the Home directory run:
   ```
   $ ls -a
   ```
   The `-a` flag will show you all the _hidden_ files. We're looking for `.bash_profile`.
3. In the case that you do not have a `.bash_profile` you will need to create one. In your `$ ~/` directory run:
   ```
   $ touch .bash_profile
   ```
4. Now you will need to open the `.bash_profile` file in your code editor. For me it was `$ code .bash_profile`
5. Create the following `alias` lines:
   ```
   alias newapp="~/.newapp.sh"
   alias newdesign="~/.newdesign.sh"
   ```
6. Save the file and Quit your terminal app.
7. Try and run:

   ```
   $ newapp

   ```

   or

   ```
   $ newdesign
   ```

You should be prompted with the message from earlier.

Remember you can always use the finder to delete any practice directories you make! Want some more command line practice? Remove any practice runs of using the Terminal!
