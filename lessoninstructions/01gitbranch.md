# LESSON 01: BRANCHES

### This lesson assumes you have successfully completed lesson 00.
- Check the section of ./00basicgit.txt labeled YOU SHOULD HAVE before continuing.

Navigate to your local test repository (C:\gitprojects\test) and open your gitbash shell from the right click menu.

## VERIFY LOCAL REPO

Ensure that your local repository is synced with your remote:<br/>
 Run "git pull".

### Your local repo should be in the [BASE STATE]

## CREATE NEW BRANCH

Run "git checkout -b [branch]" using "test" for [branch].
 This will create and switch to a branch named "test".

## ALTER FILE

Open ./helloworld.htm in your favorite editor.

Update line 7 of ./helloworld.htm by changing "  &lt;title>Document&lt;/title> to "  &lt;title>Hello World&lt;/title>".

Save the file.

Verify the changes work by opening ./helloworld in your favorite browser.
 You should see "Hello World" displayed on the active tab.

Run "git commit -m "'I have put my changes in a new branch'".

Run "git push origin [branch]". This will create [branch] in the remote and push your changes to it. Use "test" for [branch].

Return to your browser and verify that your new branch and changes have successfully landed at the remote repository.

## MERGE BRANCHES

Run "git checkout [branch name]" to switch back to "main". If you experience errors you may need to use "master" instead.
 Running "git branch" will show a list of branches.

Run "git pull" to ensure that your local main is synchronized with the remote main.

Run "git merge [branch]" to merge [branch] into main. Use "test" for [branch].

Run "git push" to push the newly merged main branch to the remote.

Return to your browser and verify that line 7 of helloworld.htm contains "Hello World".

## DELETE OLD BRANCHES

Run "git branch -d [branch]" to delete your local copy of [branch]. Use "test" for [branch name].

Run "git push origin --delete [branch]" to delete the remote copy of [branch]. Use "test" for [branch].

Return to your browser and verify that the remote "test" branch has been deleted.

## RESET TEST REPO

Alter line 7 of helloworld.htm back to "  &lt;title>Document&lt;/title>".

Run:
 "git commit -am 'undoing changes'"
 "git push"

## END LESSON 01
