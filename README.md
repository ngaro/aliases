# Shell aliases and functions
A list of aliases and functions that you can use in bash, zsh, ...

## Suggested installation

*   Fork this repo and clone it on your system
*   Create a 2nd branch for yourself: `git checkout -b myownversion`
*   Change the file `aliases` to your likings and run `git commit -v -a -m "My aliases and functions"`
*   Place your version online: `git push --set-upstream origin myownversion`
*   Add my repo as upstream: `git remote add upstream https://github.com/ngaro/aliases.git`
*   Place the line `source /PATH_OF_THE_REPO/aliases` at the end of your `.bashrc` (or `.zshrc` when using zsh)

## Using the same aliases and functions on all your systems

*   Clone your repo: `git clone git@github.com:YOURGITUSERNAME/aliases.git`
*   Switch the branch to your own version of the aliases and functions: `git checkout myownversion`
*   Repeat the last 3 steps from *Suggested installation*

## Checking for new aliases and functions added by other users

*   From time to time run `git fetch --all ; git diff master upstream/master`
*   Add the ones you like to your own aliases file (see *Adding new aliases and functions only for yourself*)
*   Update your master branch: `git checkout master ; git merge upstream/master ; git checkout myownversion`

## Adding new aliases and functions

### Syntax
You can:
*   Turn off vars, aliases and functions with respectively `unset SOMEVAR`, `unalias somealias` and `unset -f somefunction`
*   Add or overwrite variables with `SOMEVAR=some_new_value`<br>2 Variables that you probably already want to change: `GITHUBUSER` and `GITLABUSER`
*   Add or overwrite aliases with `alias somealias='some_new_command'`
*   Add or overwrite functions with `function somefunction() { some; new; code; }`

### Adding them
*   Put them in your aliases file and run `git commit -v -a -m "Description of the changes" ; git push`
*   Run `git fetch --all ; git merge origin/myversion` on all your other systems

### Proposing them to other users

*   Create a branch for a pullrequest: `git checkout master ; git checkout -b pr1`
*   Describe the alias(es) correctly and run `git commit -v -a m "names of the aliases and functions" ; git push`<br>Make sure that you mention:
**   What your aliases and functions do
**   What arguments can/should be given to the alias (if this is the case)
**   The shells(s) that you've tested them in
**   Extra software needed (if this is the case)
**   Anything the user should be careful for (if this is the case)
*   Put the branch online: `git push --set-upstream origin pr1`
*   Press *Compare and send pull request* on github
*   Switch back to your own branch: `git checkout myversion`

If you want to send extra pr's before your others have been closed/merged, use the same procedure but use the names `pr2`, `pr3`, ...

If you are not 100% sure that your aliases and functions will all be added send them as seperate pull-requests.

### Gitlab users

Everything in this readme still holds, but:
*   You have to replace *github* by *gitlab* everywhere
*   The button *Compare and send pull request* is named *Create merge request*
