# MyTools
Tools that I need when I move to a new machine. Over the years I got used to a couple of tools that make my life easier. When you move from one machine o another either due to a job change, or machine upgrade you need to install setup all the tools that you were previously using. In this repo I will keep a list of my tools: names, install scripts so that I know what to put on a new machine.

# 1. SourceTree
# 2. TotalTerminal
# 3. kdiff3
# 4. Current git branch in terminal
Open the Terminal app and if the file ~/.bash_profile does not already exist create it with the following command.

touch ~/.bash_profile

Harry Cutts points out in the comments that you should be able to use the file ~/.bashrc instead to make this method applicable to Linux.

Open ~/.bash_profile in your favorite editor and add the following content to the bottom.

#Git branch in prompt.

parse_git_branch() {

    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'

}

export PS1="\u@\h \W\[\033[32m\]\$(parse_git_branch)\[\033[00m\] $ "
Notes:

Depending on configuration changes you may have made previously you may already have a PS1 variable being exported. In this case you will need to add \$(parse_git_branch) somewhere in the existing value.

The \[\033[32m\] parts set the color of the branch text. If you prefer another color check online for a reference on valid values.

The \ in \$(parse_git_branch) is important to ensure the function is called each time the prompt is displayed; without it, the displayed branch name would not be updated when, for example, checking out a different branch or moving in and out of a Git repository directory.

Now when you change to a directory that is within a Git repository, the prompt will be supplemented with the name of the current branch. When you switch branches the prompt will update accordingly.

If you are using an existing Terminal session, don’t forget to make the changes take effect by sourcing the file with the command source ~/.bash_profile.


# 5. Alcatraz.io
- CComment
- CocoaPods
- KSImageNamed
- OMColorSense
- VVDocumenter-Xcode
- XCommentWrap 

# 6. MOGenerator

