# LESSON 02: RESOLVING CONFLICTS

This lesson assumes you have a fork of my test repository. If you do not:<br/>
 Open a browser and navigate to "https://github.com/maxhougas/test".<br/>
 Click on the "Fork" button near the upper right and follow the on-screen instructions.

Clone the fork if you have not already.<br/>
 Open your git bash shell and navigate to your github folder (probably C:\projects).<br/>
 Run "git clone https://github.com/[uname]/[repo]" where [uname] is your github user name and [repo] is the name you gave to the fork of my test repo.

Run "cd [repo]".<br/>
Verify that line 7 of helloworld.htm contains "  &lt;title>Document&lt;/title>".<br/>
 If it does not, alter line 7 to "  &lt;title>Document&lt;/title>".<br/>
  Run "git add .".<br/>
  Run "git commit -m 'fixed line 7'".<br/>
  Run "git push".

NB: the series of commands "git add [file]" "git commit -m '[message]'" can be shortened.<br>
 ONLY IF [file] was the subject of a previous add, you may use "git commit -am 'message'" alone (note the -am).<br>
 THIS WILL FAIL WHEN YOU CHANGE FILES' NAMES.

## GENERATE A LOCAL CONFLICT

Run "git checkout -b conflict".

Alter line 7 to "  &lt;title>CONFLICT&lt;/title>" (whitespace should not matter).

Run "git commit -am 'generating conflict in branch conflict'".

Run "git checkout main".

Very that line 7 of helloworld.htm once again contains "  &lt;title>Document&lt;/title>".

Alter line 7 to "  &lt;title>MAIN&lt;/title>".

Run "git commit -am 'generating conflict in branch main'".

Run "git merge conflict".<br/>
 Git should inform you that there is a conflict that requires resolution.

## RESOLVE LOCAL CONFLICT

Running "git diff main conflict" will display the differences between the version of helloworld.htm in branch main and branch conflict.

The attempted merge also alters our file, helloworld.htm.<br/>
 Running "cat helloworld.htm" will also show where git has marked the difference in the helloworld.htm file.

Open helloworld.htm in your favorite editor.

Notice that line 7 has been replaced with the following:

```
<<<<<<< HEAD
  <title>main</title>
=======
  <title>conflict</title>
>>>>>>> conflict
```

"HEAD" refers to our current branch, "main"; "conflict" refers to the branch we attempted to merge, "conflict".

Replace the above text in your copy of helloworld.htm with "  &lt;title>Document&lt;/title>".

Save and exit.

Run "git commit -am 'resolved conflict'".

Run "git branch -d conflict".

Run "git push".

## GENERATE REMOTE CONFLICT

Ensure that your helloworld.htm is in it's original state.</br>
 I.e. line 7 contains "  &lt;title>Document&lt;/title>".

Run:<br/>
 "mkdir ../test2"<br/>
 "cd ../test2"

Run:
 "git init"<br/>
 "git remote add origin [url]"<br/>
 "git checkout -b main"<br/>
 "git pull origin main"<br/>
 "git push -u origin main"

You should now have helloworld.htm in test2.

Ensure that line 7 contains "  &lt;title>Document&lt;/title>".<br/>
 If it does not, change it to do so, then run:<br/>
  "git commit -am 'resetting helloworld.htm'"<br/>
  "git push"<br/>
  "cd ../test"<br/>
  "git pull"<br/>
  "cd ../test2"<br/>

Edit line 7 of helloworld.htm to "  &lt;title>test2&lt;/title>".<br/>
 Save and exit.

Run "git push".

Run "cd ../test".

Edit line 7 of helloworld.htm to read "  &lt;title>test&lt;/title>".

Run "git commit -am 'generating conflict in test'".

Run "git push".<br/>
 It should fail.

## RESOLVE REMOTE CONFLICT

Run "git pull --rebase".

Running "cat helloworld.htm" will show that conflicts have been logged.

```
<<<<<<< HEAD
  <title>test2</title>
=======
  <title>test</title>
>>>>>>> 95ba4b9 (generating conflict 1)
```

Open helloworld.htm in your favorite editor and replace the above with "  &lt;title>Document&lt;/title>".<br/>
 Save and exit.

Run:<br/>
 "git commit -am 'fixing conflict'".<br/>
 "git rebase --continue".

## RESOURCES

https://swcarpentry.github.io/git-novice/09-conflict/

https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts

## END LESSON 02
