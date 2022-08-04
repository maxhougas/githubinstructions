## Config
- echo "https://<uname>:<PAT>@github.com" > ~/.git-credentials : save credentials in PLAINTEXT. This will also log your PAT in your shell history. Use an editor to do this.
- git config --global user.name "<uname>" : store user name in ~/.gitconfig.
- git config --global user.email "<email>" : store email in ~/.gitconfig.

## From Remote
- git clone <url> : create a local copy of of remote repository in a sub-folder of current folder.
- git fetch <url> : 
