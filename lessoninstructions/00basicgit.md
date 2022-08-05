# LESSON 00: BASIC GIT

## INSTALLATION AND SETUP

If you are on Windows, follow the pictures in ../installgitwindows/installgithub.htm.
 Written instructions are in the mouseover text for each picture.

If you are on Linux, follow your heart.

Sign up for github. This should be fairly self-explanatory and no different than signing up for most other web services.

## CREATE A PAT

Navigate to your settings. This should be under the dropdown menu in the upper right that is your avatar.

On the left hand menu all the way at the bottom is an item called "Developer settings". Click it.

Once again on the bottom of the left hand menu is an option called "Personal access tokens". Click it.

In the upper right, click "Generate new token".

Write some kind of descriptive note like "Amazing super powers".

Set the expiration to "No expiration".

Check all checkboxes.

### DO NOT CONTINUE UNTIL YOU HAVE READ THROUGH!***

Click "Generate token" at the bottom.

You will be shown your personal access token. DO NOT SHOW THIS TO ANYONE.

Upon leaving or refreshing this page you will not be shown this token again; keep it somewhere safe.

### YOU MAY NOW CONTINUE

Using the avatar dropdown menu on the upper right select "Your repositories".

Click "New" in the upper right.

Name your repository "test" and give it a description. Optionally check the box to add a README file.

Click "Create repository" at the bottom.

If you chose to create a README file, you will be shown a list of files in your new repository (so far just README.md).
 Click the green code button to be presented with an HTTPS url.

If you chose not to create a README file the HTTPS url will be near the top of the page.

Your repository URL should follow the pattern "https://github.com/[url]/test.git"

Open your bash shell.

Navigate to the folder you would like to clone your repository to.
 NB: Cloning a repository will create a sub-folder.
 NB: Creating a root folder to store all or most of your github projects is recommended. These lessons will assume it is C:\gitprojects.

Run "git clone [url]".
 If you have problems with your url try removing .git from the end.

Cloning your repository will create a new folder called "test" (or whatever you named your repository).

Run "cd test"

### DEPRICATED
Use your favorite text editor to open "config". It may be easier to do this from the Windows GUI file explorer.
 You may have to enable view hidden files. It will be under the "View" menu near the top of the window. The option is a checkbox called "Hidden items". It is a good idea to also check "File name extensions".

Look for a line that starts with "url =". It sould be under the heading [remote "origin"].

Between "https://" and "github" insert the pattern [uname]:[PAT]@
 Your new line should look like "https://[uname]:[PAT]@github.com/[uname]/test.git".
### DEPRICATED

### DO NOT CONTINUE UNTIL YOU HAVE READ THROUGH

Run 'echo "https://[uname]:[PAT]@github.com" > ~/.git-credentials'. DO NOT SHOW THIS LINE TO ANYONE.
 On Windows this file is usually located at C:\Users\[uname]\.git-credentials.
 NB: This will store your credentials in PLAINTEXT!

### YOU MAY NOW CONTINUE

Save changes and close your editor.

Run "cd ..". You should be in the folder "C:\gitprojects\test".
 The gitbash shell will refer to this as "/c/gitprojects/test". The "pwd" command will print out your current directory (folder).

### DEPRICATED
Run "echo helloworld > hw.txt".
### DEPRICATED

Copy the file ./helloworld.htm into your local repository folder ("C:\gitprojects\test" OR "/c/gitprojects/test).

Run git config --global user.email "[email]".

Run git config --global user.name "[uname]".

Run "git add .".

Run 'git commit -m "I'm adding a file!"'.

Run "git push".

Refresh your browser window to verify that helloworld.htm was successfully pushed.

## YOU SHOULD HAVE

A folder "C:\gitprojects\test"

A folder "C:\gitprojects\test\.git"

A file "C:\gitprojects\test\helloworld.htm"

A remote repository "https://github.com/[uname]/test" CONTAINING:
 A file "helloworld.htm" which is a copy of ./helloworld.htm.

## This will be referred to as the [BASE STATE].
### Subsequent lessons will assume your repository conforms to this standard.

## END LESSON 00
