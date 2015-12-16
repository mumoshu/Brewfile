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

[Configure IntelliJ IDEA for more performance](https://www.jetbrains.com/idea/help/tuning-intellij-idea.html
):

```
$ cat ~/Library/Preferences/IntelliJIdea15/idea.vmoptions
-Xms128m
-Xmx2048m
-XX:MaxPermSize=350m
-XX:ReservedCodeCacheSize=240m
```
[Configure SBT for more performance](http://stackoverflow.com/a/14561346):

```
$ cat /usr/local/etc/sbtops
*snip*
# set memory options
#
#-mem   <integer>
-J-Xms512M
-J-Xmx3536M
-J-Xss1M
-J-XX:+CMSClassUnloadingEnabled
-J-XX:+UseConcMarkSweepGC
-J-XX:MaxPermSize=724M
-J-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005
*snip*
```

```

Install aws-shell:

(See https://github.com/Homebrew/homebrew/blob/master/share/doc/homebrew/Homebrew-and-Python.md#note-on-pip-install---user)

```
$ pip install --user --install-option="--prefix=" aws-shell
$ ls ~/Library/Python/2.7/bin/aws-shell
```
