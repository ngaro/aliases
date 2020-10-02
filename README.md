# Shell aliases and functions
A list of aliases and functions that you can use in bash, zsh, ...

## Suggested installation

*   Fork this repo and clone it on your system. (We'll assume that it ends up at `/home/user/yourrepo`)
*   Create a empty file `personal_aliases` in `/home/user/yourrepo`. You don't have to track that file in git.
*   Add my repo as upstream:<br>`cd /home/user/yourrepo && git remote add upstream https://github.com/ngaro/aliases.git`
*   Add the line `export ALIASREPO=/home/user/yourrepo ; source $ALIASREPO/aliases`<br>at the end of the file `.bashrc` (or `.zshrc` when using zsh) in your homedir

Don't try to do it directly with `source /home/user/yourrepo/aliases` or your personal settings won't be parsed

## Adding/changing/removing aliases and functions

You can do this by adding and changing the file `personal_aliases`<br>
Do **not** do this in the `aliases` file otherwise checking for new stuff won't be possible<br>
You can change everything that has been done in `aliases` from within `personal_aliases` so you can:
*   Remove vars, aliases and functions with respectively `unset SOMEVAR`, `unalias somealias` and `unset -f somefunction`
*   Add or overwrite variables with `SOMEVAR=some_new_value`<br>(If you use github and/or gitlab you'll already want to overwrite `GITHUBUSER` and/or `GITLABUSER`)
*   Add or overwrite aliases with `alias somealias='some_new_command'`
*   Add or overwrite functions with `function somefunction() { some; new; code; }`

## Checking for new aliases and functions

*   From time to time see what has been changed: `git fetch --all ; git diff upstream/master`
*   Use `personal_aliases` to unset new things that you don't like. Do **not** change the file `aliases` manually...
*   Run `git merge upstream/master` to update the `aliases` file

## Suggesting new aliases and functions to the world

*   Create a branch for a pullrequest: `git checkout -b pr1`
*   Add your new stuff correctly (see below) to `aliases` and run:<br>`git commit -v -a m "names of the aliases and functions" && git push --set-upstream origin`
*   Also add your new stuff to `personal_aliases` so that you don't have to wait until the pull request has been accepted
*   Put the branch online on your fork: `git push --set-upstream origin pr1`
*   Press *Compare and send pull request* on github
*   Switch back to your own branch: `git checkout master`.
 
After the pull request has been close/merged you can remove the `pr1` branch on github and on your system.<br>
You can use `git branch -D pr1` on your system and the webbased interface on github.<br>
If you want to send extra pr's before your others have been closed/merged use the names `pr2`, `pr3`, ...

### Adding aliases and functions correctly

Please make sure to mention:
*   What your aliases and functions do
*   What arguments can/should be given (if this is the case)
*   The shells(s) that you've tested them in
*   Extra software needed (if this is the case)
*   Anything the user should be careful for (if this is the case)

If you are not 100% sure that your aliases and functions will all be added send them as seperate pull-requests.

## Gitlab users

Everything in this readme still holds, but:
*   You have to replace *github* by *gitlab* everywhere
*   The button *Compare and send pull request* is named *Create merge request*
