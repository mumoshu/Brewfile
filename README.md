My Brewfile managed by [homebrew-file](https://github.com/rcmdnk/homebrew-file).

Once my Mac is replaced or recovered, run:

```
# Install Homebrew
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
# Install homebrew-file
$ curl -fsSL https://raw.github.com/rcmdnk/homebrew-file/install/install.sh |sh
```

Add the following code to my .bash_profile:

```
if [ -f $(brew --prefix)/etc/brew-wrap ];then
  source $(brew --prefix)/etc/brew-wrap
fi

if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi

test -f ~/.bashrc && . ~/.bashrc
```

Add the following code to my .bashrc:

```
eval "$(direnv hook bash)"
```

Configure SSH keys and verify connectivity to GitHub:

```
$ ssh git@github.com
```

Install all the apps:

```
$ brew file set_repo -r git@github.com:mumoshu/Brewfile
$ brew file update
```
