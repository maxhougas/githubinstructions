## Config
- echo "https://[uname]:[PAT]@github.com" > ~/.git-credentials : save credentials in <strong>PLAINTEXT</strong>. This will also log your PAT in your shell history. Use an editor to do this.
- git config --global user.name "[uname]" : store user name in ~/.gitconfig.
- git config --global user.email "[email]" : store email in ~/.gitconfig.

## Interacting with Remote
- curl -u [uname] https://api.github.com/user/repos -d '{"name":"[name]","private","[privacy]"}' : create remote repo on github.
- git clone [url] : create a local copy of of remote repository in a sub-folder of current folder.
- git pull [url] : update local repo to match remote repo; [url] is unnecessary if ./.git/config is set properly.
- git push [url] : update remote repo to match local repo; [url] is unnecessary if ./.git/config is set properly.
- git push origin --delete [branch] : delete [branch] in remote repo.

## Interacting with local
- git add [file] : sets [file] to be tracked by local repo and stages it for committing. This command is recursive.
- git commit -m '[message]' : commits staged files with commit message [message].
- git commit -am '[message]' : stages and commits all tracked files with commit message [message].
- git checkout [branch] : changes current branch to [branch].
- git checkout -b [branch] : creates [branch] and changes current branch to it.
- git branch : list branches.
- git branch -d [branch] : delete [branch] in local repo.
- git merge [branch] : merge [branch] into current branch.
- git diff [brancha] [branchb] : display differences between [brancha] and [branchb]. Remote repos can be referenced with origin.[branch].

