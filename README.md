# Organizing and Creating New Project Directories

## Introduction
This serves as a way to add some Shell Scripts and a few aliases to create simple new project directories that contains all necessary folders for organized creativity. If you are not comfortable with the macOS command line, check out this [App](link) that does the same, but with a neat User Interface.

**Attention:** Below I use  `<dirname>` as a place holder. You should be changing this portion of code to whatever your directory name will be.


## Setting up your Home Directory

If you already have one set up, great! You can move straight to [New Site](#new-site-or-software-directory-script) or [New Design](#new-design-directory-script). Already have the scripts set up as well? Skip on down to [Add Alias](#add-alias) to make a command that will run your script and build your directory structure.

First you will want to set up your Home directory with a root directory to host your project(s). Try running the following:
```
$ mkdir ~/<filename>
```

Here we tell the computer to create a directory  `<dirname>` in the home directory using `~/.`. You will want to do this again if you are going to be making directories for both Design and Development.

Thats it for this step. Keep going!


## New Site or Software Directory Script




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
[Add Alias](#add-alias)
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